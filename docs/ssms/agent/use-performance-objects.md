---
title: Utiliser des objets de performance | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssms-agent
ms.reviewer: 
ms.suite: sql
ms.technology: tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server Agent, monitoring
- SQL Server Agent service, monitoring
- SQL Server Agent service, performance objects
- SQL Server Agent, performance objects
- performance objects [SQL Server Agent]
- monitoring [SQL Server], SQL Server Agent
- monitoring [SQL Server Agent]
- performance counters [SQL Server], SQL Server Agent
- counters [SQL Server], SQL Server Agent
ms.assetid: 830b843a-6b2a-4620-a51b-98358e9fc54b
caps.latest.revision: "5"
author: stevestein
ms.author: sstein
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 34279a9ff92a6cda54ee76ebadad6bc9ed6ca5ef
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="use-performance-objects"></a>Utiliser des objets de performance
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent comprend des compteurs et des objets de performance qui permettent de surveiller le fonctionnement du service. Ces objets de performance vous permettent d'utiliser un outil Windows, en l'occurrence l'Analyseur de performances, pour identifier la tâche réalisée en arrière-plan par le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent. Par exemple, vous pouvez identifier le nombre de travaux actifs en cours d'exécution par le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent afin de déterminer ceux qui sont bloqués.  
  
Les compteurs et les objets de performance du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent sont disponibles pour chaque instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] installée sur un ordinateur. Un objet de performance est nommé en fonction de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] qu'il représente.  
  
Le tableau suivant décrit la dénomination des objets de performance du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent :  
  
|Type d’instance|Nom de l'objet|  
|-----------------|---------------|  
|Valeur par défaut|**SQLAgent:***objet*:*compteur*|  
|Nommé|**SQLAgent$**<br /> **&#42;nom_instance&#42; :***objet*:*compteur*|  
  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] comprend les objets de performance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent suivants.  
  
|Nom de l'objet|Description|  
|---------------|---------------|  
|[SQLAgent:Jobs](http://msdn.microsoft.com/en-us/225b5e2d-4a78-4178-b2b6-b419df83c4aa)|Informations de performance relatives aux travaux démarrés, aux taux de réussite et à l'état actuel|  
|[SQLAgent:JobSteps](http://msdn.microsoft.com/en-us/44f9983c-1753-4fe0-8475-973aa2460b3a)|Informations d'état relatives aux étapes de travail|  
|[SQLAgent:Alerts](http://msdn.microsoft.com/en-us/e5e37f74-ee88-46d0-ad8f-71fd1b1fa64a)|Informations relatives au nombre d'alertes et de notifications|  
|[SQLAgent:Statistics](http://msdn.microsoft.com/en-us/ebe92bfa-0721-48aa-9ba6-e7904ad265a1)|Informations générales sur les performances|  
  
## <a name="see-also"></a> Voir aussi  
[Surveiller et régler les performances](http://msdn.microsoft.com/en-us/87f23f03-0f19-4b2e-bfae-efa378f7a0d4)  
[Procédure : démarrer le Moniteur système (Windows)](http://msdn.microsoft.com/en-us/5e51bb79-5737-470b-9c47-fac330c001c5)  
  
