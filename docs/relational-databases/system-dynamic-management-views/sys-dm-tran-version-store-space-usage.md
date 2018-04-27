---
title: Sys.dm_tran_version_store_space_usage (Transact-SQL) | Documents Microsoft
ms.custom: ''
ms.date: 04/24/2018
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: dmv's
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.dm_tran_version_store_space_usage_TSQL
- sys.dm_tran_version_store_space_usage
- dm_tran_version_store_space_usage
- dm_tran_version_store_space_usage_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_tran_version_store_space_usage dynamic management view
ms.assetid: 7ab44517-0351-4f91-bdd9-7cf940f03c51
caps.latest.revision: 10
author: savjani
ms.author: pariks
manager: ajayj
ms.workload: Inactive
monikerRange: '>= sql-server-2017 || = sqlallproducts-allversions'
ms.openlocfilehash: 1459dd2b98ed9579bc1939c60c1e74e14157d0b6
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="sysdmtranversionstorespaceusage-transact-sql"></a>Sys.dm_tran_version_store_space_usage (Transact-SQL)
[!INCLUDE[tsql-appliesto-2016sp2-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-2016sp2-asdb-xxxx-xxx-md.md)]

Retourne une table qui affiche l’espace total dans tempdb utilisé par les enregistrements de magasin de version pour chaque base de données. **Sys.dm_tran_version_store_space_usage** est efficace et pas coûteuses à exécuter, comme il ne pas parcourir les enregistrements de magasin de version individuelle et retourne agrégées magasin espace consommée dans tempdb par base de données.
  
Chaque enregistrement de version est stocké en tant que données binaires, ainsi que des informations de suivi ou d’état. À l'instar des enregistrements des tables de la base de données, ceux de la banque des versions sont stockés dans des pages de 8 192 octets. Si un enregistrement excède ces 8 192 octets, il est réparti sur deux enregistrements.  
  
Comme l'enregistrement avec contrôle de version est stocké sous forme binaire, cela ne pose pas de problème avec les différents classements des différentes bases de données. Utilisez **sys.dm_tran_version_store_space_usage** à surveiller et planifier la taille de tempdb basée sur l’utilisation de l’espace de magasin de version des bases de données dans une instance de SQL Server.
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**database_id**|**int**|ID de base de données de la base de données.|  
|**reserved_page_count**|**bigint**|Nombre total des pages réservées dans tempdb pour la version de stockage des enregistrements de la base de données.|  
|**reserved_space_kb**|**bigint**|Espace total utilisé en kilo-octets dans tempdb pour la version de stockage des enregistrements de la base de données.|  
  
## <a name="permissions"></a>Autorisations  
Sur [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)], nécessite `VIEW SERVER STATE` autorisation.   

## <a name="examples"></a>Exemples  
La requête suivante peut être utilisée pour déterminer l’espace utilisé dans tempdb, par la banque des versions de chaque base de données dans un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance. 
  
```sql  
SELECT 
  DB_NAME(database_id) as 'Database Name',
  reserved_page_count,
  reserved_space_kb 
FROM sys.dm_tran_version_store_space_usage;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
Database Name            reserved_page_count reserved_space_kb  
------------------------ -------------------- -----------  
msdb                      0                    0             
AdventureWorks2016        10                   80             
AdventureWorks2016DW      0                    0             
WideWorldImporters        20                   160             
```
 
## <a name="see-also"></a>Voir aussi  
 [Fonctions et vues de gestion dynamique &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Fonctions et vues de gestion dynamique relatives aux transactions &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/transaction-related-dynamic-management-views-and-functions-transact-sql.md)  
  
