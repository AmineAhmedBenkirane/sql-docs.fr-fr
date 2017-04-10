---
title: "Restaurer une base de donn&#233;es jusqu&#39;au point d&#39;&#233;chec en mode de r&#233;cup&#233;ration compl&#232;te (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-backup-restore"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "point de défaillance [SQL Server]"
  - "restauration des bases de données [SQL Server], point de défaillance"
  - "restaurations des bases de données [SQL Server], point de défaillance"
ms.assetid: 04106e18-bbf7-4a5e-a2e1-3d65319814d5
caps.latest.revision: 37
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
---
# Restaurer une base de donn&#233;es jusqu&#39;au point d&#39;&#233;chec en mode de r&#233;cup&#233;ration compl&#232;te (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Cette rubrique explique comment restaurer jusqu'au point d'échec. Cette rubrique s'applique uniquement aux bases de données employant les modes de restauration complète ou de récupération utilisant les journaux de transactions.  
  
### Pour restaurer jusqu'au point d'échec  
  
1.  Sauvegardez la fin du journal en exécutant l’instruction [BACKUP](../../t-sql/statements/backup-transact-sql.md) de base suivante :  
  
    ```  
    BACKUP LOG <database_name> TO <backup_device>   
       WITH NORECOVERY, NO_TRUNCATE;  
    ```  
  
2.  Restaurez une sauvegarde de base de données complète en exécutant l’instruction [RESTORE DATABASE](../Topic/RESTORE%20\(Transact-SQL\).md) de base suivante :  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
3.  Restaurez, éventuellement, une sauvegarde de base de données différentielle en exécutant l'instruction de base suivante RESTORE DATABASE :  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
4.  Appliquez chaque journal des transactions, y compris la sauvegarde de la fin du journal que vous avez créée à l'étape 1, en spécifiant WITH NORECOVERY dans l'instruction RESTORE LOG :  
  
    ```  
    RESTORE LOG <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
5.  Récupérez la base de données en exécutant l'instruction RESTORE DATABASE suivante :  
  
    ```  
    RESTORE DATABASE <database_name>   
       WITH RECOVERY;  
    ```  
  
## Exemple  
 Avant de pouvoir exécuter cet exemple, vous devez terminer les préparations suivantes :  
  
1.  Le mode de récupération par défaut de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] est le mode de récupération simple. Étant donné que ce mode de récupération ne prend pas en charge la restauration jusqu’au point de défaillance, définissez [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] pour utiliser le mode de restauration complète en exécutant l’instruction [ALTER DATABASE](../../t-sql/statements/alter-database-transact-sql.md) suivante :  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
    ```  
  
2.  Créez une sauvegarde de base de données complète à l'aide de l'instruction suivante BACKUP :  
  
    ```  
    BACKUP DATABASE AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Data.bck';  
    ```  
  
3.  Créez une sauvegarde de routine des journaux :  
  
    ```  
    BACKUP LOG AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Log.bck';  
    ```  
  
 L'exemple suivant restaure les sauvegardes créées précédemment, après la création d'une sauvegarde de la fin du journal de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]. (Cette étape suppose que le disque du journal est accessible).  
  
 Commencez par créer une sauvegarde de la fin du journal de la base de données qui capture le journal actif et laisse la base de données à l'état de restauration. Puis, l'exemple restaure la sauvegarde de base de données, applique la sauvegarde de routine des journaux créée précédemment et applique la sauvegarde de la fin du journal. Enfin, l'exemple récupère la base de données dans une étape séparée.  
  
> [!NOTE]  
>  Le comportement par défaut consiste à récupérer une base de données en même temps que l'instruction qui restaure la sauvegarde finale.  
  
```  
/* Example of restoring a to the point of failure */  
-- Step 1: Create a tail-log backup by using WITH NORECOVERY.  
BACKUP LOG AdventureWorks2012  
   TO DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 2: Restore the full database backup.  
RESTORE DATABASE AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Data.bck'  
   WITH NORECOVERY;  
GO  
-- Step 3: Restore the first transaction log backup.  
RESTORE LOG AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 4: Restore the tail-log backup.  
RESTORE LOG AdventureWorks2012  
   FROM  DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 5: Recover the database.  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
## Voir aussi  
 [BACKUP &#40;Transact-SQL&#41;](../../t-sql/statements/backup-transact-sql.md)   
 [RESTORE &#40;Transact-SQL&#41;](../Topic/RESTORE%20\(Transact-SQL\).md)  
  
  