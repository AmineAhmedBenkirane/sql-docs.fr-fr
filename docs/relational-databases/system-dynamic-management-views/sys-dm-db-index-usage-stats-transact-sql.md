---
title: Sys.dm_db_index_usage_stats (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/20/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dm_db_index_usage_stats_TSQL
- sys.dm_db_index_usage_stats
- sys.dm_db_index_usage_stats_TSQL
- dm_db_index_usage_stats
dev_langs: TSQL
helpviewer_keywords: sys.dm_db_index_usage_stats dynamic management view
ms.assetid: d06a001f-0f72-4679-bc2f-66fff7958b86
caps.latest.revision: "35"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 1bd4812468ea0c17458f2b32b653ebcbf161c1ab
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmdbindexusagestats-transact-sql"></a>sys.dm_db_index_usage_stats (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Renvoie le nombre des différents types d'opérations d'index et l'heure d'exécution de chaque opération dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 Dans [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)], les vues de gestion dynamique ne peuvent pas exposer des informations qui ont un impact sur la relation contenant-contenu de la base de données, ou exposer des informations concernant d'autres bases de données auxquelles l'utilisateur a accès. Pour éviter d'exposer ces informations, chaque ligne contenant des données qui n'appartient pas au locataire connecté est filtrée.  
  
> [!NOTE]  
>  **Sys.dm_db_index_usage_stats** ne retourne pas d’informations sur les index optimisés en mémoire. Pour plus d’informations sur l’utilisation d’index optimisé en mémoire, consultez [sys.dm_db_xtp_index_stats &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-db-xtp-index-stats-transact-sql.md).  
  
> [!NOTE]  
>  Pour appeler cette de [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], utilisez le nom **sys.dm_pdw_nodes_db_index_usage_stats**.  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**database_id**|**smallint**|ID de la base de données sur laquelle la table ou la vue est définie.|  
|**object_id**|**int**|ID de la table ou de la vue sur laquelle l'index est défini.|  
|**index_id**|**int**|Identificateur de l'index.|  
|**user_seeks**|**bigint**|Nombre de recherches par requête utilisateur.|  
|**user_scans**|**bigint**|Nombre d'analyses par requête utilisateur. Il s’agit d’analyses qui n’utilisent pas le prédicat de « recherche ».|  
|**user_lookups**|**bigint**|Nombre de recherches de signets par les requêtes utilisateur.|  
|**user_updates**|**bigint**|Nombre de mises à jour par requête utilisateur. Il s’agit de Insert, Delete et des mises à jour qui représente le nombre d’opérations n'effectuées pas les lignes réelles affectées. Par exemple, si vous supprimez les 1000 lignes dans une seule instruction, ce nombre s’incrémente de 1|  
|**last_user_seek**|**datetime**|Heure de la dernière recherche utilisateur.|  
|**last_user_scan**|**datetime**|Heure de la dernière analyse utilisateur.|  
|**last_user_lookup**|**datetime**|Heure de la dernière recherche utilisateur.|  
|**last_user_update**|**datetime**|Heure de la dernière mise à jour utilisateur.|  
|**system_seeks**|**bigint**|Nombre de recherches par requête système.|  
|**system_scans**|**bigint**|Nombre d'analyses par requête système.|  
|**system_lookups**|**bigint**|Nombre de recherches par requête système.|  
|**system_updates**|**bigint**|Nombre de mises à jour par requête système.|  
|**last_system_seek**|**datetime**|Heure de la dernière recherche système.|  
|**last_system_scan**|**datetime**|Heure de la dernière analyse système.|  
|**last_system_lookup**|**datetime**|Heure de la dernière recherche système.|  
|**last_system_update**|**datetime**|Heure de la dernière mise à jour système.|  
|pdw_node_id|**int**|**S’applique aux**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)],[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> L’identificateur du nœud qui se trouve sur cette distribution.|  
  
## <a name="remarks"></a>Notes  
 Chaque recherche, analyse ou mise à jour individuelle sur l'index spécifié par l'exécution d'une requête, est comptée comme utilisation de cet index et augmente d'une unité le compteur correspondant dans cette vue. Les informations sont renvoyées pour les opérations générées par des requêtes soumises par l'utilisateur et pour les opérations générées par des requêtes internes, telles que des analyses pour le recueil de statistiques.  
  
 Le **user_updates** compteur indique le niveau de maintenance de l’index dû à insérer, mettre à jour ou supprimer des opérations sur la table ou la vue sous-jacente. Vous pouvez utiliser cette vue pour déterminer les index qui ne sont que peu utilisés par vos applications. Vous pouvez également l'utiliser pour déterminer les index qui entraînent une surcharge à cause des traitements de maintenance. Vous envisagerez peut-être de supprimer les index qui entraînent une surcharge de maintenance mais qui ne sont pas utilisés pour des requêtes, ou peu fréquemment.  
  
 Les compteurs sont initialisés à zéro au démarrage du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER). En outre, si une base de données est détachée ou arrêtée (par exemple parce qu'AUTO_CLOSE a la valeur ON), toutes les lignes associées à la base de données sont supprimées.  
  
 Quand un index est utilisé, une ligne est ajoutée à **sys.dm_db_index_usage_stats** si une ligne n’existe pas déjà pour l’index. Quand la ligne est ajoutée, ses compteurs sont à zéro.  
  
 Au cours de la mise à niveau vers [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], ou [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], entrées de sys.dm_db_index_usage_stats sont supprimées. À partir de [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)], les entrées sont conservées comme elles l’étaient avant [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].  
  
## <a name="permissions"></a>Permissions  
Sur [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)], nécessite `VIEW SERVER STATE` autorisation.   
Sur [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] niveaux Premium, nécessite le `VIEW DATABASE STATE` autorisation dans la base de données. Sur [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] Standard et les niveaux de base, nécessite le **administrateur du serveur** ou **administrateur Active Directory de Azure** compte.  
  
## <a name="see-also"></a>Voir aussi  

 [Index liés les fonctions et vues de gestion dynamique &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/index-related-dynamic-management-views-and-functions-transact-sql.md)   
 [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql.md)   
 [Sys.dm_db_index_operational_stats &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-index-operational-stats-transact-sql.md)   
 [sys.indexes &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-indexes-transact-sql.md)   
 [Sys.Objects &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md)   
 [Surveiller et régler les performances](../../relational-databases/performance/monitor-and-tune-for-performance.md)  
  
  


