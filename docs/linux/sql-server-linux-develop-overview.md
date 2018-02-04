---
title: "Développer des applications pour SQL Server sur Linux | Documents Microsoft"
description: 
author: rothja
ms.author: jroth
manager: craigg
ms.date: 11/17/2017
ms.topic: article
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: sql-linux
ms.suite: sql
ms.technology: database-engine
ms.assetid: 758cb738-b018-465b-9ab0-59a24b892e66
ms.workload: On Demand
ms.openlocfilehash: 9bfd1b4f30593fa6ae4d17ec92bfa0047ea751bc
ms.sourcegitcommit: b4fd145c27bc60a94e9ee6cf749ce75420562e6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-get-started-developing-applications-for-sql-server-on-linux"></a>Pour commencer à développer des applications pour SQL Server sur Linux

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-linuxonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-linuxonly.md)]

Vous pouvez créer des applications qui se connectent à et utilisent SQL Server 2017 sur Linux à partir de divers langages de programmation, tels que c#, Java, Node.js, PHP, Python, Ruby et C++. Vous pouvez également utiliser les infrastructures web les plus courants et les structures relationnelles mappage ORM (Object).

> [!VIDEO https://channel9.msdn.com/events/Connect/2017/T153/player]

> [!TIP]
> Ces mêmes options de développement vous permettent également à la cible SQL Server sur d’autres plateformes. Les applications peuvent cibler SQL Server exécuté localement ou dans le cloud, Linux, Windows ou Docker sur macOS. Ou bien, vous pouvez cibler des base de données SQL Azure et Azure SQL Data Warehouse.

## <a name="try-the-tutorials"></a>Essayez les didacticiels

La meilleure prise en main et de générer des applications avec SQL Server consiste à essayer par vous-même.

- Accédez à [prise en main des didacticiels](http://aka.ms/sqldev).
- Sélectionnez votre plateforme de développement et de langue.
- Essayez les exemples de code.

> [!TIP]
> Si vous souhaitez développer pour 2017 du serveur SQL sur Docker, examinons la **macOS** didacticiels.

## <a name="create-new-applications"></a>Créer des applications

Si vous créez une nouvelle application, examinons une liste de la [les bibliothèques de connectivité](sql-server-linux-develop-connectivity-libraries.md) pour obtenir un résumé des connecteurs et des infrastructures connues disponibles pour les différents langages de programmation.

## <a name="use-existing-applications"></a>Utiliser des applications existantes

Si vous avez une application de base de données existante, vous pouvez simplement modifier sa chaîne de connexion à la cible SQL Server 2017 sur Linux. Veillez à en savoir plus sur les [problèmes connus](sql-server-linux-release-notes.md) en 2017 du serveur SQL sur Linux.

## <a name="use-existing-sql-tools-on-windows-with-sql-server-on-linux"></a>Utilisez les outils SQL existants sur Windows avec SQL Server sur Linux

Outils actuellement exécutés sur Windows tels que SSMS, SSDT et PowerShell, fonctionnent également avec 2017 du serveur SQL sur Linux. Bien qu’elles ne fonctionneront pas en mode natif sur Linux, vous pouvez toujours gérer des instances distantes de SQL Server sur Linux. 

Consultez les rubriques suivantes pour plus d’informations :

- [SQL Server Management Studio (SSMS)](sql-server-linux-develop-use-ssms.md)
- [SQL Server Data Tools (SSDT)](sql-server-linux-develop-use-ssdt.md)
- [SQL PowerShell](sql-server-linux-manage-powershell.md)

> [!Note] 
> Assurez-vous que vous utilisez les dernières versions de ces outils pour une expérience optimale.

## <a name="use-new-sql-tools-for-linux"></a>Utiliser les nouveaux outils SQL pour Linux

Vous pouvez utiliser la nouvelle [mssql extension](https://aka.ms/mssql-marketplace) pour [Visual Studio Code](https://code.visualstudio.com) sur Linux, Mac OS et Windows. Pour une procédure pas à pas détaillées, consultez le didacticiel suivant :

- [Utilisez Visual Studio Code](sql-server-linux-develop-use-vscode.md)

Vous pouvez également utiliser les nouveaux outils de ligne de commande qui sont natifs pour Linux. Ces outils sont les suivantes :

- [sqlcmd](../tools/sqlcmd-utility.md)
- [bcp](sql-server-linux-migrate-bcp.md)
- [mssql-conf](sql-server-linux-configure-mssql-conf.md)

## <a name="next-steps"></a>Étapes suivantes

Pour commencer, installez SQL Server sur Linux à l’aide d’un des Démarrages rapides suivants :

- [Installer sur Red Hat Enterprise Linux](quickstart-install-connect-red-hat.md)
- [Installer sur SUSE Linux Enterprise Server](quickstart-install-connect-suse.md)
- [Installer sur Ubuntu](quickstart-install-connect-ubuntu.md)
- [Exécutez sur Docker](quickstart-install-connect-ubuntu.md)
