---
title: "Modifier une trace existante (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- traces [SQL Server], modifying
- modifying traces
ms.assetid: 8792b43f-2510-44e3-9239-e73ad8227b89
caps.latest.revision: "18"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 39445d105c94fde05a297013583182265eef4d7b
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="modify-an-existing-trace-transact-sql"></a>Modifier une trace existante (Transact-SQL)
  Cette rubrique décrit l'utilisation de procédures stockées pour modifier une trace existante.  
  
### <a name="to-modify-an-existing-trace"></a>Pour modifier une trace existante  
  
1.  Si la trace est déjà en cours d’exécution, exécutez **sp_trace_setstatus** en spécifiant **@status = 0** pour l’arrêter.  
  
2.  Pour modifier des événements de trace, exécutez **sp_trace_setevent** en spécifiant les modifications à l’aide des paramètres. Dans l'ordre, les paramètres sont les suivants :  
  
    -   **@traceid** (ID de la trace)  
  
    -   **@eventid** (ID d’événement)  
  
    -   **@columnid** (ID de la colonne)  
  
    -   **@on** (ON)  
  
     Lorsque vous modifiez le paramètre **@on** , pensez à son interaction avec le paramètre **@columnid** :  
  
    |ON|ID de la colonne|Résultat|  
    |--------|---------------|------------|  
    |ON (**1**)|NULL|Événement activé. Toutes les colonnes sont effacées.|  
    ||NOT NULL|La colonne est activée pour l'événement spécifié.|  
    |OFF (**0**)|NULL|Événement désactivé. Toutes les colonnes sont effacées.|  
    ||NOT NULL|La colonne est désactivée pour l'événement spécifié.|  
  
> [!IMPORTANT]  
>  Contrairement aux procédures stockées standard, les paramètres de toutes les procédures stockées [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] (**sp_trace_*xx***) sont de type strict et ne prennent pas en charge la conversion automatique de type de données. Si ces paramètres ne sont pas appelés à l'aide des types de données appropriés pour les paramètres d'entrée tels qu'ils sont spécifiés dans la description de l'argument, la procédure stockée retourne une erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [sp_trace_setevent &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)   
 [sp_trace_setstatus &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql.md)   
 [Procédures stockées système &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Procédures stockées de SQL Server Profiler &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql.md)  
  
  
