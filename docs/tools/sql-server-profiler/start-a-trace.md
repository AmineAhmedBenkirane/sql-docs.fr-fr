---
title: "Démarrer une Trace | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: sql-server-profiler
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server Profiler, stopping traces
- pausing traces
- Profiler [SQL Server Profiler], stopping traces
- Profiler [SQL Server Profiler], starting traces
- traces [SQL Server], starting
- SQL Server Profiler, pausing traces
- traces [SQL Server], stopping
- Profiler [SQL Server Profiler], pausing traces
- traces [SQL Server], pausing
- SQL Server Profiler, starting traces
- stopping traces
- starting traces
ms.assetid: aeeb38eb-229a-4c8b-ad66-57e9ce45fb6a
caps.latest.revision: "24"
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: ef0d4c1015fa70145f8539a4dd10f4f8f6ffc35b
ms.sourcegitcommit: b6116b434d737d661c09b78d0f798c652cf149f3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/17/2018
---
# <a name="start-a-trace"></a>Démarrer une trace
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]Après avoir défini une nouvelle trace ou créé un modèle à l’aide de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], vous pouvez démarrer, suspendre ou arrêter la capture des données à l’aide de la nouvelle définition de trace ou un modèle.  
  
## <a name="starting-a-trace"></a>Démarrage d’une trace  
 Lorsque vous démarrez une trace et que la source définie est une instance de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ou des [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crée une file d'attente qui fournit un espace de stockage temporaire pour les événements serveur capturés.  
  
 Lorsque vous utilisez le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pour accéder à Trace SQL, une nouvelle fenêtre de trace s'ouvre (si aucune n'est ouverte) au démarrage d'une trace et les données sont capturées immédiatement.  
  
 Lorsque vous utilisez des procédures stockées système [!INCLUDE[tsql](../../includes/tsql-md.md)] pour accéder à Trace SQL, vous devez démarrer une trace chaque fois qu'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] démarre pour capturer des données. Lorsqu’une trace est démarrée, vous pouvez modifier uniquement le nom de la trace.  
  
> [!NOTE]  
>  Lorsque vous utilisez des traces existantes, vous pouvez afficher les propriétés, mais pas les modifier. Pour modifier les propriétés, arrêtez ou suspendez la trace.  
  
## <a name="see-also"></a>Voir aussi  
 [Démarrer une Trace automatiquement après la connexion à un serveur & #40 ; SQL Server Profiler & #41 ;](../../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md)   
 [Suspendre une Trace & #40 ; SQL Server Profiler & #41 ;](../../tools/sql-server-profiler/pause-a-trace-sql-server-profiler.md)   
 [Arrêter une Trace & #40 ; SQL Server Profiler & #41 ;](../../tools/sql-server-profiler/stop-a-trace-sql-server-profiler.md)   
 [Effacer une fenêtre de Trace & #40 ; SQL Server Profiler & #41 ;](../../tools/sql-server-profiler/clear-a-trace-window-sql-server-profiler.md)   
 [Exécuter une trace après qu’elle a été suspendue ou arrêtée &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
  
