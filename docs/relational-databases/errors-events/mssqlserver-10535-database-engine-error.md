---
title: MSSQLSERVER_10535 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 10535 (Database Engine error)
ms.assetid: 478fd978-11d9-4155-8329-f599fdbec14b
caps.latest.revision: 9
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 4ba53cf6d726ee80d2a3604ccc66f36212d48f47
ms.lasthandoff: 04/11/2017

---
# <a name="mssqlserver10535"></a>MSSQLSERVER_10535
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|10535|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|PG_NO_PLAN|  
|Texte du message|Impossible de créer le repère de plan '%.*ls', car aucun plan n'a été trouvé dans le cache du plan qui correspond au handle de plan spécifié. Indiquez un handle de plan mis en cache. Pour obtenir la liste des handles de plan mis en cache, interrogez la vue de gestion dynamique sys.dm_exec_query_stats.|  
  
## <a name="explanation"></a>Explication  
Aucun plan correspondant au handle de plan spécifié n'a été trouvé dans le cache du plan.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Indiquez un handle de plan mis en cache. Pour obtenir la liste des handles de plan mis en cache, interrogez la vue de gestion dynamique sys.dm_exec_query_stats.  
  
## <a name="see-also"></a>Voir aussi  
[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](~/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql.md)  
[sys.dm_exec_query_stats &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql.md)  
  

