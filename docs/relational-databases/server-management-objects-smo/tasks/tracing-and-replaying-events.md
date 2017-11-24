---
title: "Traçage et relecture d’événements | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: smo
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- replaying events
- traces [SMO]
- events [SMO], replaying
- events [SMO], tracing
ms.assetid: f41b3f85-2f6c-4c3e-9776-8c73d2cc7a53
caps.latest.revision: "21"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: d3f21d2fb03590680afb0ceaf405448f6ad17761
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="tracing-and-replaying-events"></a>Événements de traçage et de relecture
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]Dans SMO, le **Trace** et **relecture** des objets dans le <xref:Microsoft.SqlServer.Management.Trace> espace de noms fournissent un accès par programmation à le [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] fonctionnalités, qui sont utilisée pour l’analyse d’une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]ou [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]. Vous pouvez capturer et enregistrer des données sur chaque événement dans un fichier ou dans une table en vue d'une analyse ultérieure. Par exemple, vous pouvez surveiller un environnement de production pour savoir quelles sont les procédures qui compromettent les performances en s'exécutant trop lentement.  
  
 Le **Trace** et **relecture** objets fournissent un ensemble d’objets qui peuvent être utilisés pour créer des traces sur une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Ces objets peuvent être utilisés au sein de vos propres applications pour créer manuellement des traces pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]. En outre, SMO **Trace** objets peuvent être utilisés pour lire des fichiers de Trace SQL et les tables qui ont été créés par l’analyse [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], ou l’enregistrement DTS.  
  
 Les objets SMO **Trace** vous permettent de réaliser les fonctions suivantes :  
  
-   Créer une trace.  
  
-   Définir des filtres sur la trace.  
  
-   Définir les événements qui sont tracés.  
  
-   Arrêter ou démarrer une trace.  
  
-   Lire des fichiers ou des tables de trace.  
  
-   Obtenir des informations sur les événements d'une trace.  
  
-   Obtenir des informations sur les filtres d'une trace.  
  
-   Manipuler des données de trace par programme.  
  
-   Écrire des fichiers ou des tables de trace.  
  
-   Relire des fichiers ou des tables de trace.  
  
 Les données de trace à partir de la **Trace** et **relecture** objets peuvent être utilisés par l’application SMO ou être examinées manuellement à l’aide de [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md). Les données de trace sont également compatibles avec le [Trace SQL](../../../relational-databases/sql-trace/sql-trace.md) de procédures stockées qui proposent également des fonctionnalités de suivi.  
  
 Les objets de trace SMO résident dans l'espace de noms <xref:Microsoft.SqlServer.Management.Trace>, qui requiert une référence au fichier Microsoft.SQLServer.ConnectionInfo.dll.  
  
 Le **Trace** et **relecture** objets nécessitent une [ServerConnection](https://msdn.microsoft.com/en-us/library/microsoft.sqlserver.management.common.serverconnection.aspx) <xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A> objet pour établir une connexion avec l’instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Le [ServerConnection](https://msdn.microsoft.com/en-us/library/microsoft.sqlserver.management.common.serverconnection.aspx) objet se trouve dans le [Microsoft.SqlServer.Management.Common](https://msdn.microsoft.com/en-us/library/microsoft.sqlserver.management.common) espace de noms, qui requiert une référence au fichier Microsoft.SQLServer.ConnectionInfo.dll.  
  
> [!NOTE]  
>  Les objets **Trace** et **Replay** ne sont pas pris en charge sur une plate-forme 64 bits.  
  
  
