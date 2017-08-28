---
title: "Utilisez SSMS pour gérer SQL Server sur Linux | Documents Microsoft"
description: 
author: sanagama
ms.author: sanagama
manager: jhubbard
ms.date: 08/23/2017
ms.topic: article
ms.prod: sql-linux
ms.technology: database-engine
ms.assetid: b2fcf858-21c3-462a-8d49-50c85647d092
ms.custom: H1Hack27Feb2017
ms.translationtype: MT
ms.sourcegitcommit: 21f0cfd102a6fcc44dfc9151750f1b3c936aa053
ms.openlocfilehash: 1f8fe782aa69f462366130418fce84a2654de3cf
ms.contentlocale: fr-fr
ms.lasthandoff: 08/28/2017

---
# <a name="use-sql-server-management-studio-on-windows-to-manage-sql-server-on-linux"></a>Utilisez SQL Server Management Studio sur Windows pour gérer SQL Server sur Linux

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

Cette rubrique présente les [SQL Server Management Studio (SSMS)](https://msdn.microsoft.com/en-us/library/hh213248.aspx) et présente quelques tâches courantes. SSMS est une application Windows, par conséquent, utilisez SSMS lorsque vous disposez d’un ordinateur Windows qui peut se connecter à une instance distante de SQL Server sur Linux.

[SQL Server Management Studio (SSMS)](https://msdn.microsoft.com/en-us/library/hh213248.aspx) fait partie d’une suite d’outils SQL des offres Microsoft gratuitement pour vos besoins de développement et de gestion. SSMS est un environnement intégré pour accéder à configurer, gérer, administrer et développer tous les composants de SQL Server exécuté localement ou dans le cloud, Linux, Windows ou Docker sur macOS et de la base de données SQL Azure et Azure SQL Data Warehouse. SSMS associe un groupe d’outils graphiques avec un nombre d’éditeurs de script performants pour permettre aux développeurs et aux administrateurs de tous les niveaux de compétence accès à SQL Server.

SSMS offre un large éventail de fonctionnalités de développement et de gestion pour SQL Server, notamment pour :

- configurer, surveiller et administrer unique ou plusieurs instances de SQL Server
- déployer, surveiller et mettre à niveau les composants de la couche données tels que des entrepôts de données et les bases de données
- sauvegarde et restauration des bases de données
- générer et exécuter des scripts et des requêtes T-SQL et afficher les résultats
- générer des scripts T-SQL pour les objets de base de données
- afficher et modifier des données dans les bases de données
- concevoir visuellement des requêtes T-SQL et les objets de base de données tels que des procédures stockées, tables et vues

Consultez [utilisez SQL Server Management Studio](https://msdn.microsoft.com/en-us/library/ms174173.aspx) pour plus d’informations.

## <a name="install-the-newest-version-of-sql-server-management-studio-ssms"></a>Installer la version la plus récente de SQL Server Management Studio (SSMS)

Lorsque vous travaillez avec SQL Server, vous devez toujours utiliser la dernière version de SQL Server Management Studio (SSMS). La dernière version de SSMS est continuellement mis à jour et optimisées et est actuellement compatible avec SQL Server 2017 Linux on. Pour télécharger et installer la version la plus récente, consultez [télécharger SQL Server Management Studio](https://msdn.microsoft.com/library/mt238290.aspx). Pour rester à jour, la dernière version de SSMS vous invite lorsqu’il existe une nouvelle version disponible en téléchargement. 

## <a name="before-you-begin"></a>Avant de commencer
- Consultez [SSMS d’utilisation de Windows pour se connecter à SQL Server sur Linux](sql-server-linux-develop-use-ssms.md) pour savoir comment vous connecter et interroger à l’aide de SSMS
- Lecture la [problèmes connus](sql-server-linux-release-notes.md) pour SQL Server 2017 RC2 sur Linux

## <a name="create-and-manage-databases"></a>Créer et gérer des bases de données
Tout en étant connecté à la *master* base de données, vous pouvez créer des bases de données sur le serveur et modifier ou supprimer des bases de données existantes. Les étapes suivantes décrivent comment effectuer plusieurs tâches courantes de gestion de base de données au moyen de Management Studio. Pour effectuer ces tâches, vérifiez que vous êtes connecté à la *master* base de données avec la connexion du principal au niveau du serveur que vous avez créé lorsque vous configurez SQL Server 2017 RC2 sur Linux.

### <a name="create-a-new-database"></a>Créer une base de données

1. Démarrez SSMS, puis connectez-vous à votre serveur dans SQL Server 2017 RC2 sur Linux

2. Dans l’Explorateur d’objets, cliquez sur le *bases de données* dossier, puis cliquez sur * Nouvelle base de données... »

3. Dans le *nouvelle base de données* boîte de dialogue, entrez un nom pour votre nouvelle base de données, puis cliquez sur *OK*

La nouvelle base de données est correctement créé dans votre serveur. Si vous préférez créer une nouvelle base de données à l’aide de T-SQL, consultez [créer une base de données (SQL Server Transact-SQL)](https://msdn.microsoft.com/en-us/library/ms176061.aspx).

### <a name="drop-a-database"></a>Supprimer une base de données

1. Démarrez SSMS, puis connectez-vous à votre serveur dans SQL Server 2017 RC2 sur Linux

2. Dans l’Explorateur d’objets, développez le *bases de données* dossier pour afficher la liste de la base de données sur le serveur.

3. Dans l’Explorateur d’objets, avec le bouton droit sur la base de données que vous souhaitez supprimer, puis cliquez sur *supprimer*

4. Dans le *supprimer un objet* boîte de dialogue, vérifiez *fermer les connexions existantes* puis cliquez sur *OK*

La base de données est correctement supprimée de votre serveur. Si vous souhaitez supprimer une base de données à l’aide de T-SQL, consultez [supprimer une base de données (SQL Server Transact-SQL)](https://msdn.microsoft.com/en-us/library/ms178613.aspx).

## <a name="use-activity-monitor-to-see-information-about-sql-server-activity"></a>Moniteur d’activité permet d’afficher des informations sur l’activité de SQL Server

Le [moniteur d’activité](https://msdn.microsoft.com/en-us/library/hh212951.aspx) outil est intégré dans SQL Server Management Studio (SSMS) et affiche des informations sur les processus SQL Server et la façon dont ces processus affectent l’instance actuelle de SQL Server.

1. Démarrez SSMS, puis connectez-vous à votre serveur dans SQL Server 2017 RC2 sur Linux

2. Dans l’Explorateur d’objets, cliquez sur le *server* nœud, puis cliquez sur *moniteur d’activité*

Moniteur d’activité affiche les volets extensibles et réductibles avec des informations sur les éléments suivants :
- Vue d'ensemble
- Processus
- Attentes de ressources
- Fichier de données d’e/s
- Requêtes coûteuses récentes
- Requêtes coûteuses actives

Lorsqu’un volet est développé, le moniteur d’activité interroge l’instance pour plus d’informations. Lorsqu'un volet est réduit, toutes les activités d'interrogation cessent pour ce volet. Vous pouvez développer un ou plusieurs volets en même temps pour afficher différents types d’activité sur l’instance.

## <a name="see-also"></a>Voir aussi
- [Utiliser SQL Server Management Studio](https://msdn.microsoft.com/en-us/library/ms174173.aspx)
- [Exporter et importer une base de données avec SSMS](sql-server-linux-migrate-ssms.md)
- [Didacticiel : SQL Server Management Studio](https://msdn.microsoft.com/en-us/library/bb934498.aspx)
- [Didacticiel : écriture d'instructions Transact-SQL](https://msdn.microsoft.com/en-us/library/ms365303.aspx)
- [Analyse des performances et surveillance de l'activité du serveur](https://msdn.microsoft.com/en-us/library/ms191511.aspx)

