---
title: Supprimer une trace (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- traces [SQL Server], deleting
- removing traces
- deleting traces
ms.assetid: a5502814-b281-42dd-b885-5c9368025ae6
caps.latest.revision: 22
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 5d9eb3c4aeafab2fb6337da5d0bb24c3f4d3b8f7
ms.contentlocale: fr-fr
ms.lasthandoff: 04/11/2017

---
# <a name="delete-a-trace-transact-sql"></a>Supprimer une trace (Transact-SQL)
  Cette rubrique explique comment utiliser des procédures stockées pour supprimer une trace.  
  
 Pour obtenir un exemple d’utilisation de procédures stockées de trace, consultez [Créer une trace &#40;Transact-SQL&#41;](../../relational-databases/sql-trace/create-a-trace-transact-sql.md).  
  
### <a name="to-delete-a-trace"></a>Pour supprimer une trace  
  
1.  Exécutez **sp_trace_setstatus** en spécifiant **@status= 0** pour arrêter la trace.  
  
2.  Exécutez **sp_trace_setstatus** en spécifiant **@status= 2** pour fermer la trace et supprimer du serveur les informations la concernant.  
  
> [!NOTE]  
>  Une trace doit d'abord être arrêtée avant d'être fermée.  
  
## <a name="see-also"></a>Voir aussi  
 [sp_trace_setstatus &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql.md)   
 [Procédures stockées système &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Procédures stockées de SQL Server Profiler &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql.md)  
  
  
