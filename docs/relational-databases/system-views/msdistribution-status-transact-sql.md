---
title: MSdistribution_status (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSdistribution_status_TSQL
- MSdistribution_status
dev_langs:
- TSQL
helpviewer_keywords:
- MSdistribution_status view
ms.assetid: 90d447de-3a4a-4f3e-aeab-e8fff6348361
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: ed7e4fc9889d940ca5ae787bd5a66953b0bad45f
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
# <a name="msdistributionstatus-transact-sql"></a>MSdistribution_status (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Le **MSdistribution_status** vue présente des informations supplémentaires sur les commandes d’état dans la base de données de distribution. Cette vue est stockée dans la base de données de distribution.  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**article_id**|**int**|Identifie un article.|  
|**agent_id**|**int**|Identifie un Agent de réplication.|  
|**UndelivCmdsInDistDB**|**int**|Nombre de commandes en attente de remise aux Abonnés.|  
|**DelivCmdsInDistDB**|**int**|Nombre de commandes remises aux Abonnés.|  
  
## <a name="see-also"></a>Voir aussi  
 [Tables de réplication &#40; Transact-SQL &#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Vues de réplication &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
