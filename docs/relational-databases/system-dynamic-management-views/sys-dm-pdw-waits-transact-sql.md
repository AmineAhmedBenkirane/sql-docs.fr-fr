---
title: Sys.dm_pdw_waits (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/07/2017
ms.prod: 
ms.prod_service: sql-data-warehouse, pdw
ms.service: sql-data-warehouse
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: TSQL
ms.assetid: 5130e498-1c77-4ae3-a80b-9aae396494e9
caps.latest.revision: "7"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 14a9dec8435f3acdaadce93198d957deff2c02dd
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmpdwwaits-transact-sql"></a>Sys.dm_pdw_waits (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  Contient plus d’informations sur tous les attendez États rencontrées pendant l’exécution d’une demande ou de requête, y compris les verrous, attend sur les files d’attente de transmission et ainsi de suite.  
  
|Nom de la colonne|Type de données| Description|Plage|  
|-----------------|---------------|-----------------|-----------|  
|wait_id|**bigint**|Id numérique unique associé à l’état d’attente.<br /><br /> Clé pour cette vue.|Le point d’entrée unique pour toutes les attentes dans le système.|  
|session_id|**nvarchar(32)**|ID de la session à laquelle l’état d’attente s’est produite.|Consultez session_id dans [sys.dm_pdw_exec_sessions &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-sessions-transact-sql.md).|  
|Type|**nvarchar(255)**|Type d’attente de que cette entrée représente.|[!INCLUDE[ssInfoNA](../../includes/ssinfona-md.md)]|  
|object_type|**nvarchar(255)**|Type d’objet affecté par l’attente.|[!INCLUDE[ssInfoNA](../../includes/ssinfona-md.md)]|  
|object_name|**nvarchar (386)**|Nom ou le GUID de l’objet spécifié qui a été affectée par l’attente.||  
|request_id|**nvarchar(32)**|ID de la demande sur laquelle l’état d’attente s’est produite.|Consultez request_id dans [sys.dm_pdw_exec_requests &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql.md).|  
|request_time|**datetime**|Heure à laquelle l’état d’attente a été demandée.||  
|acquire_time|**datetime**|Heure à laquelle le verrou ou la ressource a été acquis.||  
|state|**nvarchar(50)**|État de l’état d’attente.|[!INCLUDE[ssInfoNA](../../includes/ssinfona-md.md)]|  
|priority|**int**|Priorité de l’élément en attente.|[!INCLUDE[ssInfoNA](../../includes/ssinfona-md.md)]|  
  
## <a name="see-also"></a>Voir aussi  
 [Entrepôt de données SQL et les vues de gestion dynamique de l’entrepôt de données en parallèle &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)   
 [Sys.dm_pdw_wait_stats &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-wait-stats-transact-sql.md)  
  
  
