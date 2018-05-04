---
title: Sys.CHECK_CONSTRAINTS (Transact-SQL) | Documents Microsoft
ms.custom: ''
ms.date: 06/28/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.service: ''
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.check_constraints
- sys.check_constraints_TSQL
- check_constraints_TSQL
- check_constraints
dev_langs:
- TSQL
helpviewer_keywords:
- sys.check_constraints catalog view
ms.assetid: 940ebc5e-44ba-4dae-8b29-da94f2d1d6c4
caps.latest.revision: 32
author: edmacauley
ms.author: edmaca
manager: craigg
monikerRange: = azuresqldb-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 43ccc527143be26d4cee4d2e4ce55e8fb37d3abb
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="syscheckconstraints-transact-sql"></a>sys.check_constraints (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Contient une ligne pour chaque objet qui est une contrainte de validation avec **sys.objects.type** = « C ».  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**\<Colonnes héritent de sys.objects >**||Pour obtenir la liste des colonnes qui hérite de cette vue, consultez [sys.objects &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md).|  
|**is_disabled**|**bit**|La contrainte CHECK est désactivée.|  
|**is_not_for_replication**|**bit**|La contrainte CHECK a été créée avec l'option NOT FOR REPLICATION.|  
|**is_not_trusted**|**bit**|La contrainte CHECK n'a pas été vérifiée par le système pour toutes les lignes.|  
|**parent_column_id**|**int**|0 indique une contrainte CHECK de niveau table.<br /><br /> Une valeur autre que zéro indique qu'il s'agit d'une contrainte CHECK de niveau colonne définie sur la colonne contenant la valeur d'ID spécifiée.|  
|**Définition**|**nvarchar(max)**|Expression SQL qui définit cette contrainte CHECK.|  
|**uses_database_collation**|**bit**|1 = La définition de contrainte dépend du classement par défaut de la base de données pour une évaluation correcte ; sinon, la valeur est 0. Une telle dépendance évite la modification du classement par défaut de la base de données.|  
|**is_system_named**|**bit**|1 = Le nom a été généré par le système.<br /><br /> 0 = Le nom a été fourni par l'utilisateur.|  
  
## <a name="permissions"></a>Autorisations  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Pour plus d'informations, consultez [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Vues de catalogue d’objets &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Affichages catalogue &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
