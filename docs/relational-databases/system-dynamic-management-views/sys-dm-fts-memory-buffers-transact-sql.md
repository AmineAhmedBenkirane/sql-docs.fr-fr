---
title: Sys.dm_fts_memory_buffers (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/29/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.dm_fts_memory_buffers
- dm_fts_memory_buffers_TSQL
- dm_fts_memory_buffers
- sys.dm_fts_memory_buffers_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.dm_fts_memory_buffers dynamic management view
ms.assetid: 56895fe5-e8df-4d75-9adc-c1f7757cdef8
caps.latest.revision: "33"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 3708d5c98e8869e0a1d1a68fe2bc2df3376bcadf
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmftsmemorybuffers-transact-sql"></a>sys.dm_fts_memory_buffers (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retourne des informations sur les zones de mémoire tampon appartenant à un pool de mémoire spécifique et utilisées dans le cadre d'une analyse de texte intégral ou d'une plage d'analyses de texte intégral.  
  
> [!NOTE]
> La colonne suivante sera supprimée dans une future version de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **row_count**. Évitez d'employer cette colonne pour de nouvelles tâches de développement et pensez éventuellement à modifier les applications qui l'utilisent actuellement.  

  
|Colonne|Data type| Description|  
|------------|---------------|-----------------|  
|**pool_id**|**int**|ID du pool de mémoire alloué.<br /><br /> 0 = petites zones de mémoire tampon<br /><br /> 1 = grandes zones de mémoire tampon|  
|**memory_address**|**varbinary (8)**|Adresse de la zone de mémoire tampon allouée.|  
|**nom**|**nvarchar(4000)**|Nom de la zone de mémoire tampon partagée pour laquelle cette allocation a été effectuée.|  
|**is_free**|**bit**|État actuel de la zone de mémoire tampon.<br /><br /> 0 = libre<br /><br /> 1 = occupé|  
|**row_count**|**int**|Nombre de lignes que gère actuellement cette zone de mémoire tampon.|  
|**bytes_used**|**int**|Quantité, en octets, de mémoire utilisée dans cette zone de mémoire tampon.|  
|**percent_used**|**int**|Pourcentage de mémoire allouée utilisé.|  
  
## <a name="permissions"></a>Permissions  
Sur [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)], nécessite `VIEW SERVER STATE` autorisation.   
Sur [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] niveaux Premium, nécessite le `VIEW DATABASE STATE` autorisation dans la base de données. Sur [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] Standard et les niveaux de base, nécessite le **administrateur du serveur** ou **administrateur Active Directory de Azure** compte.  
 
## <a name="physical-joins"></a>Jointures physiques  
 ![Jointures significatives de cette vue de gestion dynamique](../../relational-databases/system-dynamic-management-views/media/join-dm-fts-memory-buffers-1.gif "jointures significatives de cette vue de gestion dynamique")  
  
## <a name="relationship-cardinalities"></a>Cardinalités de la relation  
  
|De|Pour|Relation|  
|----------|--------|------------------|  
|dm_fts_memory_buffers.pool_id|dm_fts_memory_pools.pool_id|Plusieurs-à-un|  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions et vues de gestion dynamique &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Recherche en texte intégral et fonctions et vues de gestion dynamique de la recherche sémantique &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/full-text-and-semantic-search-dynamic-management-views-functions.md)  
  
  

