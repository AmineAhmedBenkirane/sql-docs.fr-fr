---
title: Sys.trace_columns (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
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
- sys.trace_columns
- trace_columns
- trace_columns_TSQL
- sys.trace_columns_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.trace_columns catalog view
ms.assetid: 5c48eb09-9e9b-45dd-b151-ca39b026ece5
caps.latest.revision: "23"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7405b51d9071238a237a11ef7c0ceef78e2e7119
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/27/2017
---
# <a name="systracecolumns-transact-sql"></a>sys.trace_columns (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Le **sys.trace_columns** affichage catalogue contient une liste de toutes les colonnes d’événements de trace. Ces colonnes ne changent pas pour une version donnée de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].  
  
 Pour obtenir une liste complète des événements de trace pris en charge, consultez [SQL Server Event Class Reference](../../relational-databases/event-classes/sql-server-event-class-reference.md).  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Utilisez plutôt les affichages catalogue des événements étendus.  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**trace_column_id**|**smallint**|ID unique de cette colonne.|  
|**nom**|**nvarchar (128)**|Nom unique de cette colonne. Ce paramètre n'est pas localisé.|  
|**TYPE_NAME**|**nvarchar (128)**|Nom de type de données de cette colonne.|  
|**max_size**|**int**|Taille de données maximale de cette colonne en octets.|  
|**is_filterable**|**bit**|Indique si la colonne peut être utilisée dans la spécification de filtre.<br /><br /> 0 = faux<br /><br /> 1 = vrai|  
|**is_repeatable**|**bit**|Indique si la colonne peut être référencée dans les données de « colonne répétée ».<br /><br /> 0 = faux<br /><br /> 1 = vrai|  
|**is_repeated_base**|**bit**|Indique si cette colonne est utilisée en tant que clé unique pour référencer des données répétées.<br /><br /> 0 = faux<br /><br /> 1 = vrai|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Pour plus d'informations, consultez [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Affichages catalogue d’objets &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Sys.traces &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-traces-transact-sql.md)   
 [Sys.trace_categories &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-trace-categories-transact-sql.md)   
 [Sys.trace_events &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-trace-events-transact-sql.md)   
 [Sys.trace_event_bindings &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-trace-event-bindings-transact-sql.md)   
 [Sys.trace_subclass_values &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-trace-subclass-values-transact-sql.md)  
  
  
