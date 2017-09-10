---
title: DROP STATISTICS (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/22/2016
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DROP STATISTICS
- DROP_STATISTICS_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- removing statistics
- column statistics [SQL Server]
- DROP STATISTICS statement
- deleting statistics
- dropping statistics
- table statistics [SQL Server]
- statistical information [SQL Server], removing
ms.assetid: 222806b7-4e45-445b-8cd0-bd5461f3ca4a
caps.latest.revision: 41
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 39d639b9d2ea2fc43cfd8389113ae7dad5611cc1
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="drop-statistics-transact-sql"></a>DROP STATISTICS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Supprime les statistiques de plusieurs collections dans les tables spécifiées dans la base de données active.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-- Syntax for SQL Server and Azure SQL Database  
  
DROP STATISTICS table.statistics_name | view.statistics_name [ ,...n ]  
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
DROP STATISTICS [ schema_name . ] table_name.statistics_name   
[;]  
```  
  
## <a name="arguments"></a>Arguments  
 *table* | *affichage*  
 Nom de la table cible ou de la vue indexée dans laquelle figurent les statistiques à supprimer. Les noms de table et de vue doivent respecter les règles de [des identificateurs de base de données](../../relational-databases/databases/database-identifiers.md). Vous n'êtes pas obligé de spécifier le nom du propriétaire de la table ou de la vue.  
  
 *statistics_name*  
 Nom du groupe de statistiques à supprimer. Les noms de statistiques doivent respecter les règles applicables aux identificateurs.  
  
## <a name="remarks"></a>Notes  
 Soyez prudent lorsque vous supprimez des statistiques. En effet, vous risquez d'affecter le plan d'exécution choisi par l'optimiseur de requête.  
  
 Les statistiques sur les index ne peuvent pas être supprimées à l'aide de DROP STATISTICS. Les statistiques sont conservées aussi longtemps que l'index existe.  
  
 Pour plus d’informations sur l’affichage des statistiques, consultez [DBCC SHOW_STATISTICS &#40; Transact-SQL &#41; ](../../t-sql/database-console-commands/dbcc-show-statistics-transact-sql.md).  
  
## <a name="permissions"></a>Permissions  
 Nécessite une autorisation ALTER sur la table ou la vue.  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-dropping-statistics-from-a-table"></a>A. Effacement des statistiques d’une table  
 L'exemple suivant supprime les groupes de statistiques (collections) de deux tables. Le groupe de statistiques (collection) `VendorCredit` de la table `Vendor` et le groupe de statistiques (collection) `CustomerTotal` de la table `SalesOrderHeader` sont supprimés.  
  
```  
-- Create the statistics groups.  
USE AdventureWorks2012;  
GO  
CREATE STATISTICS VendorCredit  
    ON Purchasing.Vendor (Name, CreditRating)  
    WITH SAMPLE 50 PERCENT  
CREATE STATISTICS CustomerTotal  
    ON Sales.SalesOrderHeader (CustomerID, TotalDue)  
    WITH FULLSCAN;  
GO  
DROP STATISTICS Purchasing.Vendor.VendorCredit, Sales.SalesOrderHeader.CustomerTotal;  
  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemples : [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="b-dropping-statistics-from-a-table"></a>B. Effacement des statistiques d’une table  
 Les exemples suivants supprimer la `CustomerStats1` statistiques de table `Customer`.  
  
```  
DROP STATISTICS Customer.CustomerStats1;  
DROP STATISTICS dbo.Customer.CustomerStats1;  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [ALTER DATABASE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql.md)   
 [CREATE INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/create-index-transact-sql.md)   
 [CREATE STATISTICS &#40;Transact-SQL&#41;](../../t-sql/statements/create-statistics-transact-sql.md)   
 [sys.stats &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-stats-transact-sql.md)   
 [Sys.stats_columns &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-stats-columns-transact-sql.md)   
 [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-show-statistics-transact-sql.md)   
 [sp_autostats &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-autostats-transact-sql.md)   
 [sp_createstats &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-createstats-transact-sql.md)   
 [UPDATE STATISTICS &#40;Transact-SQL&#41;](../../t-sql/statements/update-statistics-transact-sql.md)   
 [EVENTDATA &#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)   
 [USE &#40;Transact-SQL&#41;](../../t-sql/language-elements/use-transact-sql.md)  
  
  



