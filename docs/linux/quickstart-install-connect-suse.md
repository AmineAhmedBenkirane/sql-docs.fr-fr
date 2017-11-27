---
title: Prise en main 2017 du serveur SQL sur SUSE Linux Enterprise Server | Documents Microsoft
description: "Ce didacticiel de démarrage rapide montre comment installer SQL Server 2017 sur SUSE Linux Enterprise Server puis créer et interroger une base de données avec sqlcmd."
author: rothja
ms.author: jroth
manager: jhubbard
ms.date: 10/02/2017
ms.topic: article
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: linux
ms.suite: sql
ms.custom: 
ms.technology: database-engine
ms.assetid: 31ddfb80-f75c-4f51-8540-de6213cb68b8
ms.workload: On Demand
ms.openlocfilehash: c69d708c793b2a7a3513a5885d84f7f534e03e6b
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="install-sql-server-and-create-a-database-on-suse-linux-enterprise-server"></a>Installer SQL Server et de créer une base de données sur SUSE Linux Enterprise Server

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

Dans ce didacticiel de démarrage rapide, vous d’abord installez SQL Server 2017 sur SUSE Linux Enterprise Server (SLES) v12 SP2. Se connecter avec **sqlcmd** à créer votre première base de données et exécuter des requêtes.

> [!TIP]
> Ce didacticiel nécessite l’entrée d’utilisateur et une connexion internet. Si vous êtes intéressé par le [sans assistance](sql-server-linux-setup.md#unattended) ou [hors connexion](sql-server-linux-setup.md#offline) procédures d’installation, consultez [aide à l’Installation de SQL Server sur Linux](sql-server-linux-setup.md).

## <a name="prerequisites"></a>Conditions préalables

Vous devez disposer d’un ordinateur de SP2 SLES v12 avec **au moins 3,25 Go** de mémoire. Le système de fichiers doit être **XFS** ou **EXT4**. Autres systèmes de fichiers, tel que **BTRFS**, non pris en charge.

Pour installer SUSE Linux Enterprise Server sur votre propre ordinateur, accédez à [https://www.suse.com/products/server](https://www.suse.com/products/server). Vous pouvez également créer des machines virtuelles SLES dans Azure. Consultez [créer et gérer des machines virtuelles Linux avec l’interface CLI Azure](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-manage-vm)et utiliser `--image SLES` dans l’appel à `az vm create`.

> [!NOTE]
> À ce stade, le [sous-système Windows pour Linux](https://msdn.microsoft.com/commandline/wsl/about) pour Windows 10 n’est pas prise en charge comme cible d’installation.

Pour les autres exigences système, consultez [configuration système requise pour SQL Server sur Linux](sql-server-linux-setup.md#system).

## <a id="install"></a>Installation de SQL Server

Pour configurer SQL Server sur SLES, exécutez les commandes suivantes dans un Terminal Server pour installer le **mssql-serveur** package :

> [!IMPORTANT]
> Si vous avez déjà installé un CTP ou la version RC de SQL Server 2017, vous devez d’abord supprimer l’ancien référentiel avant d’inscrire un des référentiels de la disponibilité générale. Pour plus d’informations, consultez [modifier les référentiels à partir du référentiel d’aperçu dans le référentiel GA](sql-server-linux-change-repo.md).

1. Téléchargez le fichier de configuration de Microsoft SQL Server SLES référentiel :

   ```bash
   sudo zypper addrepo -fc https://packages.microsoft.com/config/sles/12/mssql-server-2017.repo
   sudo zypper --gpg-auto-import-keys refresh
   ```

   > [!NOTE]
   > Il s’agit de l’espace de stockage de mise à jour Cumulative (CU). Pour plus d’informations sur les options de votre référentiel et leurs différences, consultez [modifier les référentiels sources](sql-server-linux-setup.md#repositories).

1. Exécutez les commandes suivantes pour installer SQL Server :

   ```bash
   sudo zypper install -y mssql-server
   ```

1. Après la fin de l’installation package, exécutez **le programme d’installation de mssql-conf** et suivez les invites pour définir le mot de passe SA et choisissez votre édition.

   ```bash
   sudo /opt/mssql/bin/mssql-conf setup
   ```

   > [!TIP]
   > Si vous essayez de SQL Server 2017 dans ce didacticiel, les éditions suivantes sont concédés sous licence librement : Evaluation, Developer et Express.

   > [!NOTE]
   > Veillez à spécifier un mot de passe fort pour le compte d’administrateur système (Minimum longueur 8 caractères, y compris les majuscules et minuscules, chiffres en base 10 et/ou des symboles non alphanumériques).

1. Une fois la configuration terminée, vérifiez que le service est en cours d’exécution :

   ```bash
   systemctl status mssql-server
   ```

1. Si vous envisagez de vous connecter à distance, vous devrez peut-être également ouvrir le port TCP du serveur SQL (1433 par défaut) sur votre pare-feu. Si vous utilisez le pare-feu SuSE, vous devez modifier le **/etc/sysconfig/SuSEfirewall2** fichier de configuration. Modifier la **FW_SERVICES_EXT_TCP** entrée à inclure le numéro de port SQL Server.

   ```
   FW_SERVICES_EXT_TCP="1433"
   ```

À ce stade, SQL Server est en cours d’exécution sur votre ordinateur SLES et est prêt à utiliser.

## <a id="tools"></a>Installer les outils de ligne de commande SQL Server

Pour créer une base de données, vous devez vous connecter avec un outil qui peut exécuter des instructions Transact-SQL sur le serveur SQL Server. Les étapes suivantes installer les outils de ligne de commande de SQL Server : [sqlcmd](../tools/sqlcmd-utility.md) et [bcp](../tools/bcp-utility.md).

1. Ajoutez le référentiel Microsoft SQL Server à Zypper.

   ```bash
   sudo zypper addrepo -fc https://packages.microsoft.com/config/sles/12/prod.repo 
   sudo zypper --gpg-auto-import-keys refresh
   ```

1. Installer **mssql-tools** avec le kit du développeur unixODBC.

   ```bash
   sudo zypper install -y mssql-tools unixODBC-devel
   ```

1. Pour plus de commodité, ajoutez `/opt/mssql-tools/bin/` à votre **chemin d’accès** variable d’environnement. Cela vous permet d’exécuter les outils sans spécifier le chemin d’accès complet. Exécutez les commandes suivantes pour modifier la **chemin d’accès** des sessions de connexion et des sessions/non-connexion interactive :

   ```bash
   echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bash_profile
   echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bashrc
   source ~/.bashrc
   ```

> [!TIP]
> **SQLCMD** est le seul outil pour la connexion à SQL Server pour exécuter des requêtes et d’effectuer les tâches de gestion et de développement. Incluent d’autres outils [SQL Server Management Studio](sql-server-linux-develop-use-ssms.md) et [Visual Studio Code](sql-server-linux-develop-use-vscode.md).

[!INCLUDE [Connect, create, and query data](../includes/sql-linux-quickstart-connect-query.md)]
