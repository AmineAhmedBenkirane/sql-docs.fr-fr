---
title: MSSQLSERVER_3431 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: errors-events
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 3431 (Database Engine error)
ms.assetid: 9541217f-e5c6-4a12-a19a-006058f1d3f3
caps.latest.revision: 18
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: baae3acd554d490bb10e3f417bb9314d88c011a5
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="mssqlserver3431"></a>MSSQLSERVER_3431
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|3431|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|UNRESOLVED_XACT|  
|Texte du message|Impossible de récupérer la base de données '%.*ls' (ID de base de données %d) en raison de transactions externes non résolues. Les transactions MS DTC (Microsoft Distributed Transaction Coordinator) ont été préparées, mais MS DTC n'a pas réussi à déterminer la résolution. Pour corriger ce problème, réparez MS DTC, effectuez une restauration à partir d'une sauvegarde complète ou réparez la base de données.|  
  
## <a name="explanation"></a>Explication  
Une ou plusieurs transactions distribuées utilisant MS DTC ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator) étaient incomplètes lorsque la base de données a été fermée. La récupération de cette base de données a échoué car [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas terminer ou restaurer les transactions sans avoir plus d’informations de la part de MS DTC.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Pour récupérer cette base de données, vous devez d'abord résoudre le problème avec MS DTC. Pour analyser ce problème, examinez les journaux des événements Windows. Si vous ne parvenez pas à résoudre le problème avec MS DTC et à récupérer la base de données, restaurez une sauvegarde de la base de données.  
  
