---
title: Sys.dm_hadr_name_id_map (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 06/10/2016
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
- sys.dm_hadr_name_id_map
- sys.dm_hadr_name_id_map_TSQL
- dm_hadr_name_id_map
- dm_hadr_name_id_map_TSQL
dev_langs: TSQL
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
- sys.dm_hadr_name_id_map dynamic management view
ms.assetid: e07bb8a9-37de-4a39-a257-950d7c3ae8fb
caps.latest.revision: "8"
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 320d4856d0358612d462ef14c5559346624fe619
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmhadrnameidmap-transact-sql"></a>sys.dm_hadr_name_id_map (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Montre le mappage des groupes de disponibilité Always On que l’instance actuelle de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a joint à trois identificateurs uniques : une disponibilité, ID de groupe, un ID de ressource WSFC et un ID de groupe WSFC. L'objectif de ce mappage est de gérer le scénario dans lequel la ressource/le groupe WSFC est renommé.  
   
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**ag_name**|**nvarchar (256)**|Nom du groupe de disponibilité. Il s’agit d’un nom spécifié par l’utilisateur qui doit être unique au sein du cluster du Cluster de basculement Windows Server (WSFC).|  
|**ag_id**|**uniqueidentifier**|Identificateur unique (GUID) du groupe de disponibilité.|  
|**ag_resource_id**|**nvarchar (256)**|ID unique du groupe de disponibilité en tant que ressource dans le cluster WSFC.|  
|**ag_group_id**|**nvarchar (256)**|Identificateur unique du groupe WSFC du groupe de disponibilité.|  
  
## <a name="permissions"></a>Permissions  
 requièrent l'autorisation VIEW SERVER STATE sur le serveur.  
  
## <a name="see-also"></a>Voir aussi  
 [Vues et fonctions de gestion dynamiques de groupes de disponibilité Always On &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/always-on-availability-groups-dynamic-management-views-functions.md)   
 [Affichages catalogue des groupes de disponibilité Always On &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/always-on-availability-groups-catalog-views-transact-sql.md)   
 [Surveiller des groupes de disponibilité &#40;Transact-SQL&#41;](../../database-engine/availability-groups/windows/monitor-availability-groups-transact-sql.md)   
 [Groupes de disponibilité Always On &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md)  
  
  
