---
title: "Sauvegarder sur un support de sauvegarde miroir (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-backup-restore"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5fc43a5d-dfd6-4c53-a4ef-3c8da23ccc81
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 7
---
# Sauvegarder sur un support de sauvegarde miroir (Transact-SQL)
  Cette rubrique décrit comment utiliser l’instruction [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](../../t-sql/statements/backup-transact-sql.md) pour spécifier un support de sauvegarde mis en miroir lors de la sauvegarde d’une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Dans l'instruction BACKUP, spécifiez le premier miroir dans la clause TO. Spécifiez ensuite chaque miroir dans sa propre clause MIRROR TO. Les clauses TO et MIRROR TO doivent spécifier le même nombre et type d'unités de sauvegarde.  
  
## Exemple  
 L'exemple suivant crée le support de sauvegarde mis en miroir illustré dans la figure précédente et sauvegarde la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sur les deux miroirs.  
  
```  
BACKUP DATABASE AdventureWorks2012  
TO TAPE = '\\.\tape0', TAPE = '\\.\tape1'  
MIRROR TO TAPE = '\\.\tape2', TAPE = '\\.\tape3'  
WITH  
    FORMAT,  
    MEDIANAME = 'AdventureWorks2012Set1';  
GO  
```  
  
## Tâches associées  
 **Pour restaurer une sauvegarde miroir**  
  
-   [RESTORE &#40;Transact-SQL&#41;](../Topic/RESTORE%20\(Transact-SQL\).md)  
  
## Voir aussi  
 [BACKUP &#40;Transact-SQL&#41;](../../t-sql/statements/backup-transact-sql.md)   
 [Jeux de supports de sauvegarde en miroir &#40;SQL Server&#41;](../../relational-databases/backup-restore/mirrored-backup-media-sets-sql-server.md)  
  
  