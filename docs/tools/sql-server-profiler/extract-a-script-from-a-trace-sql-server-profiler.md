---
title: "Extraire un Script à partir d’une Trace (SQL Server Profiler) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-non-specified
ms.service: 
ms.component: sql-server-profiler
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scripts [SQL Server], traces
- extracting script from trace [SQL Server]
ms.assetid: 431126a6-ff91-4818-8763-4442152bd571
caps.latest.revision: "20"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: d4449e7ba2193993b738850678bfd067f9780b3c
ms.sourcegitcommit: b2d8a2d95ffbb6f2f98692d7760cc5523151f99d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2017
---
# <a name="extract-a-script-from-a-trace-sql-server-profiler"></a>Extraire un script d'une trace (SQL Server Profiler)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]Cette rubrique explique comment extraire [!INCLUDE[tsql](../../includes/tsql-md.md)] événements d’une trace du fichier ou de table et les enregistrer en tant qu’un [!INCLUDE[tsql](../../includes/tsql-md.md)] fichier de script à l’aide de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].  
  
### <a name="to-extract-a-transact-sql-script-from-a-trace-file-or-table"></a>Pour extraire un script Transact-SQL à partir d'un fichier ou d'une table de trace  
  
1.  Ouvrez un fichier ou une table de trace contenant les événements [!INCLUDE[tsql](../../includes/tsql-md.md)] que vous voulez enregistrer sous forme de fichier de script [!INCLUDE[tsql](../../includes/tsql-md.md)]. Pour plus d’informations, consultez [Ouvrir un fichier de trace&#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) ou [Ouvrir une table de trace &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md).  
  
2.  Dans le menu **Fichier**, pointez sur **Exporter**, sur **Extraire les événements SQL Server**, puis cliquez sur **Extraire les événements Transact-SQL**.  
  
3.  Dans la boîte de dialogue **Enregistrer sous** , attribuez un nom au fichier [!INCLUDE[tsql](../../includes/tsql-md.md)] , puis cliquez sur **Enregistrer**.  
  
## <a name="see-also"></a>Voir aussi  
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
