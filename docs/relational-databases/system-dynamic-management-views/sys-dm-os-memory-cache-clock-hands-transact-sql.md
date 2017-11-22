---
title: Sys.dm_os_memory_cache_clock_hands (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 08/18/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.dm_os_memory_cache_clock_hands_TSQL
- dm_os_memory_cache_clock_hands
- dm_os_memory_cache_clock_hands_TSQL
- sys.dm_os_memory_cache_clock_hands
dev_langs: TSQL
helpviewer_keywords: sys.dm_os_memory_cache_clock_hands dynamic management view
ms.assetid: 0660eddc-691c-425f-9d43-71151d644de7
caps.latest.revision: "37"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 32ac57b5da2720b8ba3c874d604b5f65ec8da308
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmosmemorycacheclockhands-transact-sql"></a>sys.dm_os_memory_cache_clock_hands (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retourne le statut de chaque aiguille d'une horloge de cache spécifique.  
  
> [!NOTE]  
>  Pour appeler cette de [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], utilisez le nom **sys.dm_pdw_nodes_os_memory_cache_clock_hands**.  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**cache_address**|**varbinary (8)**|Adresse du cache associé à l'horloge. N'accepte pas la valeur NULL.|  
|**nom**|**nvarchar (256)**|Nom du cache. N'accepte pas la valeur NULL.|  
|**type**|**nvarchar (60)**|Type de cache. Il peut exister plusieurs caches du même type. N'accepte pas la valeur NULL.|  
|**clock_hand**|**nvarchar (60)**|Type d'aiguille. Il s’agit d’une des opérations suivantes :<br /><br /> External<br /><br /> Interne<br /><br /> N'accepte pas la valeur NULL.|  
|**clock_status**|**nvarchar (60)**|Statut de l'horloge. Il s’agit d’une des opérations suivantes :<br /><br /> Suspendu<br /><br /> Exécution en cours<br /><br /> N'accepte pas la valeur NULL.|  
|**rounds_count**|**bigint**|Nombre de balayages effectués sur le cache pour supprimer des entrées. N'accepte pas la valeur NULL.|  
|**removed_all_rounds_count**|**bigint**|Nombre d'entrées supprimées par tous les balayages. N'accepte pas la valeur NULL.|  
|**updated_last_round_count**|**bigint**|Nombre d'entrées mises à jour lors du dernier balayage. N'accepte pas la valeur NULL.|  
|**removed_last_round_count**|**bigint**|Nombre d'entrées supprimées lors du dernier balayage. N'accepte pas la valeur NULL.|  
|**last_tick_time**|**bigint**|Heure, en millisecondes, du dernier mouvement de l'aiguille de l'horloge. N'accepte pas la valeur NULL.|  
|**round_start_time**|**bigint**|Heure, en millisecondes, du balayage précédent. N'accepte pas la valeur NULL.|  
|**last_round_start_time**|**bigint**|Durée totale, en millisecondes, du précédent cycle d'horloge. N'accepte pas la valeur NULL.|  
|**pdw_node_id**|**int**|**S’applique aux**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)],[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> L’identificateur du nœud qui se trouve sur cette distribution.|  
  
## <a name="permissions"></a>Permissions  
Sur [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)], nécessite `VIEW SERVER STATE` autorisation.   
Sur [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] niveaux Premium, nécessite le `VIEW DATABASE STATE` autorisation dans la base de données. Sur [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] Standard et les niveaux de base, nécessite le **administrateur du serveur** ou **administrateur Active Directory de Azure** compte.    
  
## <a name="remarks"></a>Notes  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stocke des informations en mémoire dans une structure appelée un cache mémoire. Les informations stockées dans le cache peuvent être des données, des entrées d'index, des plans de procédures compilées et divers autres types d'informations [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Pour éviter d'avoir à recréer ces informations, celles-ci sont conservées aussi longtemps que possible dans le cache mémoire et sont généralement supprimées du cache lorsqu'elles sont trop anciennes pour être utiles ou lorsqu'il est nécessaire de libérer l'espace mémoire pour stocker de nouvelles informations. Le processus de suppression des anciennes informations s'appelle un balayage mémoire. Le balayage mémoire est une activité fréquente, mais pas continue. Un algorithme d'horloge contrôle le balayage du cache mémoire. Chaque horloge peut contrôler plusieurs balayages mémoire, qui sont appelés des aiguilles. L'aiguille de l'horloge du cache mémoire correspond à l'emplacement actuel de l'une des aiguilles d'un balayage mémoire.  
  
## <a name="see-also"></a>Voir aussi  


 [Système d’exploitation de serveur SQL relatives des vues de gestion dynamique &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sql-server-operating-system-related-dynamic-management-views-transact-sql.md)  
  
  


