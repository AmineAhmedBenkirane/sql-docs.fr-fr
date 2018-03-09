---
title: Sys.sysreferences (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.service: 
ms.component: system-compatibility-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.sysreferences
- sys.sysreferences_TSQL
- sysreferences
- sysreferences_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sysreferences compatibility view
- sysreferences system table
ms.assetid: 81276f13-202e-4e74-962d-46eb98c98d2e
caps.latest.revision: 
author: rothja
ms.author: jroth
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 920796ed0dd63b8961cf93449394723e5460ecb9
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2018
---
# <a name="syssysreferences-transact-sql"></a>sys.sysreferences (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

  Contient des mappages des définitions de contrainte FOREIGN KEY sur les colonnes référencées dans la base de données.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**constid**|**int**|ID de la contrainte FOREIGN KEY.|  
|**fkeyid**|**int**|ID de la table qui contient la référence.|  
|**rkeyid**|**int**|ID de la table référencée.|  
|**rkeyindid**|**smallint**|ID de l'index unique de la table référencée comprenant les colonnes clé référencées.|  
|**keycnt**|**smallint**|Nombre de colonnes dans la clé.|  
|**forkeys**|**varbinary(32)**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**refkeys**|**varbinary(32)**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**fkeydbid**|**smallint**|Réservé.|  
|**rkeydbid**|**smallint**|Réservé.|  
|**fkey1**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey2**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey3**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey4**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey5**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey6**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey7**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey8**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey9**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey10**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey11**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey12**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey13**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey14**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey15**|**smallint**|ID de la colonne qui contient la référence.|  
|**fkey16**|**smallint**|ID de la colonne qui contient la référence.|  
|**rkey1**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey2**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey3**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey4**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey5**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey6**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey7**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey8**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey9**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey10**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey11**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey12**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey13**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey14**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey15**|**smallint**|ID de colonne de la colonne référencée.|  
|**rkey16**|**smallint**|ID de colonne de la colonne référencée.|  
  
## <a name="see-also"></a>Voir aussi  
 [Mappage des Tables système pour les vues système &#40; Transact-SQL &#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Affichages de compatibilité &#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
