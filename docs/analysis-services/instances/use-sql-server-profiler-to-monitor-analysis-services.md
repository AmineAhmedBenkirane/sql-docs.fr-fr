---
title: Utiliser SQL Server Profiler pour surveiller Analysis Services | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server Profiler, Analysis Services
- monitoring Analysis Services [SQL Server]
- performance [Analysis Services], SQL Server Profiler
- Profiler [SQL Server Profiler], Analysis Services
ms.assetid: 8b77dafc-4584-4e93-8ad7-299304391bfd
caps.latest.revision: "35"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: On Demand
ms.openlocfilehash: 6924a034d191e0d7e9406d6515e9796517de0c21
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="use-sql-server-profiler-to-monitor-analysis-services"></a>Utiliser SQL Server Profiler pour contrôler Analysis Services
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)][!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] surveille les événements du moteur de processus, tels que le début d’un lot ou une transaction et il capture les données relatives à ces événements, ce qui vous permet de surveiller l’activité du serveur et de base de données (par exemple, les requêtes utilisateur ou activité de connexion). Vous pouvez capturer les données du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] dans une table ou un fichier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , en vue d'une analyse ultérieure, et relire les événements capturés sur la même instance d' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou sur une autre instance pour voir exactement ce qui s'est passé. Vous pouvez relire les événements en temps réel ou pas à pas. Il est également très utile d'exécuter sur la même machine les événements de trace et les compteurs de performances. SQL Profiler peut corréler les deux en fonction de l'heure et les afficher ensemble sur une même chronologie. Les événements de trace vous donneront plus de détails, tandis que les compteurs de performances vous fourniront une vue agrégée. Pour plus d’informations sur la création et l’exécution de traces, consultez [Créer des traces de SQL Server Profiler pour la relecture &#40;Analysis Services&#41;](../../analysis-services/instances/create-profiler-traces-for-replay-analysis-services.md).  
  
 Le tableau suivant décrit les rubriques de cette section.  
  
## <a name="in-this-section"></a>Dans cette section  
  
|Rubrique|Description|  
|-----------|-----------------|  
|[Introduction à la surveillance de Analysis Services à l'aide de SQL Server Profiler](../../analysis-services/instances/introduction-to-monitoring-analysis-services-with-sql-server-profiler.md)|Explique comment utiliser le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pour contrôler une instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .|  
|[Créer des traces de SQL Server Profiler pour la relecture &#40;Analysis Services&#41;](../../analysis-services/instances/create-profiler-traces-for-replay-analysis-services.md)|Indique les conditions requises pour créer une trace afin d'effectuer une relecture en utilisant le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].|  
|[Événements de trace Analysis Services](../../analysis-services/trace-events/analysis-services-trace-events.md)|Décrit les classes d'événements [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Ces classes d'événements sont associées aux actions générées par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et utilisées pour les relectures de traces.|  
  
## <a name="see-also"></a>Voir aussi  
 [Analyser une instance Analysis Services](../../analysis-services/instances/monitor-an-analysis-services-instance.md)  
  
  
