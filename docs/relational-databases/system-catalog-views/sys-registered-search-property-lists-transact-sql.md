---
title: Sys.registered_search_property_lists (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- registered_search_property_lists_TSQL
- sys.registered_search_property_lists
- registered_search_property_lists
- sys.registered_search_property_lists_TSQL
dev_langs: TSQL
helpviewer_keywords:
- full-text search [SQL Server], search property lists
- sys.registered_search_property_lists catalog view
- search property lists [SQL Server], viewing
ms.assetid: 630d4caa-9bea-4cd3-a5b1-01098b0855fc
caps.latest.revision: "16"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: da4097d937e48a8e409059a11dc247e1557cfd26
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysregisteredsearchpropertylists-transact-sql"></a>sys.registered_search_property_lists (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Contient une ligne pour chaque liste de propriétés de recherche sur la base de données actuelle.  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**property_list_id**|**int**|ID de la liste de propriétés.|  
|**nom**|**sysname**|Nom de la liste de propriétés.|  
|**create_date**|**datetime**|Date de création de la liste de propriétés.|  
|**modify_date**|**datetime**|Date de dernière modification de la liste de propriétés au moyen d'une instruction ALTER.|  
|**principal_id**|**int**|Propriétaire de la liste de propriétés.|  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Rechercher les propriétés du document à l’aide des listes de propriétés de recherche](../../relational-databases/search/search-document-properties-with-search-property-lists.md).  
  
## <a name="permissions"></a>Permissions  
 La visibilité des métadonnées dans les listes de propriétés de recherche est limitée à celles dont vous êtes propriétaire ou sur lesquelles une autorisation REFERENCE vous a été accordée.  
  
> [!NOTE]  
>  Le propriétaire d'une liste de propriétés de recherche peut accorder des autorisations REFERENCE ou CONTROL dans la liste. Les utilisateurs disposant de l'autorisation CONTROL peuvent également accorder l'autorisation REFERENCE à d'autres utilisateurs.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant affiche l'ID et le nom des listes de propriétés de recherche dans la base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].  
  
```  
USE AdventureWorks2012;  
GO  
SELECT property_list_id, name FROM sys.registered_search_property_lists;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/alter-fulltext-index-transact-sql.md)   
 [sys.fulltext_indexes &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql.md)  
  
  
