---
title: Sys.dm_hadr_instance_node_map (Transact-SQL) | Documents Microsoft
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
- sys.sys.dm_hadr_instance_node_map_TSQL
- sys.sys.dm_hadr_instance_node_map
- sys.dm_hadr_instance_node_map_TSQL
- sys.dm_hadr_instance_node_map
dev_langs: TSQL
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
- Availability Groups [SQL Server], WSFC clusters
- sys.sys.dm_hadr_instance_node_map dynamic management view
ms.assetid: ccfaf62c-9f87-43cf-a5e7-8942e91dd041
caps.latest.revision: "9"
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: b600f8821e65745a64b0f7487e136b9d3031ede6
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmhadrinstancenodemap-transact-sql"></a>sys.dm_hadr_instance_node_map (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Pour chaque instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui héberge un réplica de disponibilité qui est joint à son groupe de disponibilité Always On, retourne le nom du nœud de Clustering de basculement Windows Server (WSFC) qui héberge l’instance de serveur. Cette vue de gestion dynamique permet les utilisations suivantes :  
  
-   Cette vue de gestion dynamique est utile pour détecter un groupe de disponibilité avec plusieurs réplicas de disponibilité hébergés sur le même nœud WSFC, ce qui correspond à une configuration non prise en charge qui peut se produire après un basculement FCI si le groupe de disponibilité n'est pas correctement configuré. Pour plus d’informations, consultez [Clustering de basculement et groupes de disponibilité Always On &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/failover-clustering-and-always-on-availability-groups-sql-server.md).  
  
-   Lorsque plusieurs instances de SQL Server sont hébergées sur le même nœud WSFC, la DLL de ressource utilise cette vue de gestion dynamique pour déterminer l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à laquelle se connecter.  
   
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**ag_resource_id**|**nvarchar (256)**|ID unique du groupe de disponibilité en tant que ressource dans le cluster WSFC.|  
|**nom_instance**|**nvarchar (256)**|Nom :*server*/*instance*, d’une instance de serveur qui héberge un réplica pour le groupe de disponibilité.|  
|**nom_nœud**|**nvarchar (256)**|Nom du nœud de cluster WSFC.|  
  
## <a name="permissions"></a>Permissions  
 requièrent l'autorisation VIEW SERVER STATE sur le serveur.  
  
## <a name="see-also"></a>Voir aussi  
 [Vues et fonctions de gestion dynamiques de groupes de disponibilité Always On &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/always-on-availability-groups-dynamic-management-views-functions.md)   
 [Affichages catalogue des groupes de disponibilité Always On &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/always-on-availability-groups-catalog-views-transact-sql.md)   
 [Surveiller des groupes de disponibilité &#40;Transact-SQL&#41;](../../database-engine/availability-groups/windows/monitor-availability-groups-transact-sql.md)   
 [Groupes de disponibilité Always On &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md)  
  
  
