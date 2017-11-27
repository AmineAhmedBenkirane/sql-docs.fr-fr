---
title: Sys.assembly_types (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- assembly_types
- sys.assembly_types
- sys.assembly_types_TSQL
- assembly_types_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.assembly_types catalog view
ms.assetid: 35f0384f-7a6d-41b1-9461-f1406d68f317
caps.latest.revision: "22"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 211cb9f89fe2e84b6a8a21dd8268551df6a2e97c
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysassemblytypes-transact-sql"></a>sys.assembly_types (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

  Contient une ligne pour chaque type défini par l'utilisateur et par un assembly CLR. Les éléments suivants **sys.assembly_types** apparaissent dans la liste des colonnes héritées (consultez [sys.types &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/sys-types-transact-sql.md)) après **rule_object_id**.  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**assembly_id**|**int**|ID de l'assembly à partir duquel ce type est créé.|  
|**assembly_class**|**sysname**|Nom de la classe dans l'assembly qui définit ce type.|  
|**is_binary_ordered**|**bit**|Trier les octets de ce type revient à trier les opérateurs de comparaison sur ce même type.|  
|**is_fixed_length**|**bit**|La longueur du type est toujours identique à max_length.|  
|**prog_id**|**nvarchar (40)**|ProgID du type exposé à COM.|  
|**assembly_qualified_name**|**nvarchar(4000)**|Nom du type qualifié de l'assembly. Le formatage du nom est tel qu'il peut être transmis à Type.GetType().|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Pour plus d'informations, consultez [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Affichages catalogue &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Affichages catalogue &#40; de Types scalaires Transact-SQL &#41;](../../relational-databases/system-catalog-views/scalar-types-catalog-views-transact-sql.md)  
  
  
