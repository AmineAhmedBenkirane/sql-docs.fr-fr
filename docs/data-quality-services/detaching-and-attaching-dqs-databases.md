---
title: "Attachement et d&#233;tachement de bases de donn&#233;es&#160;DQS | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "data-quality-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 830e33bc-dd15-4f8e-a4ac-d8634b78fe45
caps.latest.revision: 9
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 9
---
# Attachement et d&#233;tachement de bases de donn&#233;es&#160;DQS
  Cette rubrique explique comment attacher et détacher les bases de données DQS.  
  
##  <a name="BeforeYouBegin"></a> Avant de commencer  
  
###  <a name="Limitations"></a> Limitations et restrictions  
 Pour obtenir la liste des limitations et restrictions, consultez [détachement de la base de données et attacher & #40 ; SQL Server & #41 ;](../relational-databases/databases/database-detach-and-attach-sql-server.md).  
  
###  <a name="Prerequisites"></a> Configuration requise  
  
-   Vérifiez qu'aucune activité ou aucun processus n'est en cours d'exécution dans DQS. Pour ce faire, utilisez l'écran **Analyse des activités** . Pour plus d'informations sur l'utilisation de cet écran, consultez [Monitor DQS Activities](../data-quality-services/monitor-dqs-activities.md).  
  
-   Assurez-vous qu'aucun utilisateur n'est connecté au [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].  
  
###  <a name="Security"></a> Sécurité  
  
####  <a name="Permissions"></a> Autorisations  
  
-   Votre compte d'utilisateur Windows doit être membre du rôle serveur fixe db_owner dans l'instance SQL Server pour pouvoir détacher des bases de données DQS.  
  
-   Votre compte d'utilisateur Windows doit disposer d'une autorisation CREATE DATABASE, CREATE ANY DATABASE ou ALTER ANY DATABASE pour pouvoir attacher une base de données.  
  
-   Vous devez disposer du rôle dqs_administrator sur la base de données DQS_MAIN pour mettre fin à toutes les activités en cours d'exécution ou arrêter tous les processus en cours d'exécution dans DQS.  
  
##  <a name="Detach"></a> Détacher des bases de données DQS  
 Lorsque vous détachez une base de données DQS à l'aide de SQL Server Management Studio, les fichiers détachés restent sur votre ordinateur et peuvent être rattachés à la même instance de SQL Server ou être déplacés vers un autre serveur et être attachés à cet endroit. Les fichiers de base de données DQS sont généralement disponibles à l’emplacement suivant sur votre ordinateur Data Quality Services : C:\Program Files\Microsoft SQL Server\MSSQL13.*\< Nom_instance >*\MSSQL\DATA.  
  
1.  Démarrez Microsoft SQL Server Management Studio et connectez-vous à l'instance de SQL Server appropriée.  
  
2.  Dans l'Explorateur d'objets, développez le nœud **Bases de données** .  
  
3.  Avec le bouton droit le **DQS_MAIN** de base de données, pointez sur **tâches**, puis cliquez sur **détachement**. La boîte de dialogue **Détacher la base de données** apparaît.  
  
4.  Activez la case à cocher sous la **Supprimer** colonne, puis cliquez sur **OK** pour détacher la base de données DQS_MAIN.  
  
5.  Répétez les étapes 3 et 4 avec les bases de données DQS_PROJECTS et DQS_STAGING_DATA afin de les détacher.  
  
 Vous pouvez également détacher les bases de données DQS à l'aide d'instructions Transact-SQL avec la procédure stockée sp_detach_db. Pour plus d’informations sur le détachement de bases de données à l’aide d’instructions Transact-SQL, consultez la page [à l’aide de Transact-SQL](../relational-databases/databases/detach-a-database.md#TsqlProcedure) dans [détacher une base de données](../relational-databases/databases/detach-a-database.md).  
  
##  <a name="Attach"></a> Attacher des bases de données DQS  
 Utilisez les instructions suivantes pour attacher une base de données DQS à la même instance SQL Server (depuis laquelle vous avez procédé au détachement) ou à une autre instance de SQL Server où [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] est installé.  
  
1.  Démarrez Microsoft SQL Server Management Studio et connectez-vous à l'instance de SQL Server appropriée.  
  
2.  Dans l’Explorateur d’objets, cliquez sur **bases de données**, puis cliquez sur **Attach**. La boîte de dialogue **Attacher des bases de données** apparaît.  
  
3.  Pour spécifier la base de données à attacher, cliquez sur **Ajouter**. La boîte de dialogue **Rechercher les fichiers de base de données** apparaît.  
  
4.  Sélectionnez l'unité de disque contenant la base de données et développez l'arborescence du répertoire pour rechercher et sélectionner le fichier .mdf de la base de données. Par exemple, pour la base de données DQS_MAIN :  
  
    ```  
    C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\DQS_MAIN.mdf  
    ```  
  
5.  Le **Détails de la base de données** volet (inférieur) affiche les noms des fichiers à attacher. Pour vérifier ou modifier le chemin d’accès d’un fichier, cliquez sur le **Parcourir** bouton (...).  
  
6.  Cliquez sur **OK** pour attacher la base de données DQS_MAIN.  
  
7.  Répétez les étapes 2 à 6 pour les bases de données DQS_PROJECTS et DQS_STAGING_DATA afin de les attacher.  
  
8.  Vous devez également exécuter les instructions Transact-SQL à l'étape suivante après la restauration de la base de données DQS_MAIN ; sinon, un message d'erreur s'affiche lorsque vous tentez de vous connecter à Data Quality Server à l'aide de l'application Data Quality Client et que vous ne pouvez pas vous connecter. Toutefois, vous n'avez pas besoin de suivre les étapes 9 et 10 si vous venez d'attacher la base de données DQS_PROJECTS ou DQS_STAGING_DATA, et non DQS_MAIN.  
  
     Pour exécuter les instructions Transact-SQL, dans l’Explorateur d’objets, cliquez sur le serveur, puis cliquez sur **nouvelle requête**.  
  
9. Dans la fenêtre Éditeur de requête, copiez les instructions SQL suivantes :  
  
    ```  
    ALTER DATABASE [DQS_MAIN] SET TRUSTWORTHY ON;  
    EXEC sp_configure 'clr enabled', 1;  
    RECONFIGURE WITH OVERRIDE  
    ALTER DATABASE [DQS_MAIN] SET ENABLE_BROKER  
    ALTER AUTHORIZATION ON DATABASE::[DQS_MAIN] TO [##MS_dqs_db_owner_login##]  
    ALTER AUTHORIZATION ON DATABASE::[DQS_PROJECTS] TO [##MS_dqs_db_owner_login##]  
  
    ```  
  
10. Appuyez sur F5 pour exécuter les instructions. Consultez le volet de résultats pour vérifier que les instructions ont été correctement exécutées. Vous verrez le message suivant : `Configuration option 'clr enabled' changed from 1 to 1. Run the RECONFIGURE statement to install.`  
  
11. Connectez-vous à Data Quality Server à l'aide de l'application Data Quality Client afin de vérifier que vous pouvez vous connecter correctement.  
  
 Vous pouvez également attacher des bases de données DQS à l'aide d'instructions Transact-SQL. Pour plus d’informations sur l’attachement de bases de données à l’aide d’instructions Transact-SQL, consultez la page [à l’aide de Transact-SQL](../relational-databases/databases/attach-a-database.md#TsqlProcedure) dans [attacher une base de données](../relational-databases/databases/attach-a-database.md).  
  
## Voir aussi  
 [Gérer des bases de données DQS](../data-quality-services/manage-dqs-databases.md)  
  
  