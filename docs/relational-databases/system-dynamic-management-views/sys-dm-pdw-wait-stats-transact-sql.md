---
title: Sys.dm_pdw_wait_stats (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: 
ms.prod_service: sql-data-warehouse, pdw
ms.reviewer: 
ms.service: sql-data-warehouse
ms.component: dmv's
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: TSQL
ms.assetid: cfb8d905-c34f-44de-9574-dde81e170916
caps.latest.revision: "7"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c2a567c103a0a2b3f3dac24accd8099d2bd85e80
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmpdwwaitstats-transact-sql"></a>Sys.dm_pdw_wait_stats (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  Contient des informations relatives à la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] état du système d’exploitation associées aux instances en cours d’exécution sur les différents nœuds. Pour obtenir la liste des types d’attentes et leur description, consultez [sys.dm_os_wait_stats](http://msdn.microsoft.com/en-us/library/ms179984\(v=sql.120\).aspx).  
  
|Nom de la colonne|Type de données| Description|Plage|  
|-----------------|---------------|-----------------|-----------|  
|**pdw_node_id**|**int**|ID du nœud que cette entrée fait référence.||  
|**wait_name**|**nvarchar(255)**|Nom du type d'attente.||  
|**max_wait_time**|**bigint**|Délai d’attente maximal de ce type d’attente.||  
|**request_count**|**bigint**|Nombre d’attentes de cette attente en attente de type.||  
|**signal_time**|**bigint**|Différence entre le moment où le thread qui attend a été signalé et le moment où il a commencé à s'exécuter.||  
|**completed_count**|**bigint**|Nombre d’attentes de ce type effectuées depuis le dernier serveur de redémarrer.||  
|**temps_attente**|**bigint**|Temps d’attente total pour ce type d’attente dans millisecons. Temps inclusif de signal_time.||  
  
## <a name="see-also"></a>Voir aussi  
 [Entrepôt de données SQL et les vues de gestion dynamique de l’entrepôt de données en parallèle &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)   
 [Sys.dm_pdw_waits &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-waits-transact-sql.md)  
  
  
