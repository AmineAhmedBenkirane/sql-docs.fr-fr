---
title: "Spécifier des réponses à un travail| Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: sql-non-specified
ms.service: 
ms.component: ssms-agent
ms.reviewer: 
ms.suite: sql
ms.technology: tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- jobs [SQL Server Agent], responses
- SQL Server Agent jobs, responses
- actions [SQL Server Agent jobs]
- responding to jobs
ms.assetid: 050242e1-9b79-4ade-91a9-580707b9d2d9
caps.latest.revision: "4"
author: stevestein
ms.author: sstein
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: a95f0e289dd73b2001b7cb60d7ef707f9a26fd15
ms.sourcegitcommit: b2d8a2d95ffbb6f2f98692d7760cc5523151f99d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2017
---
# <a name="specify-job-responses"></a>Spécifier des réponses à un travail
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)] Les réponses à un travail spécifient les actions que le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent réalisera après l’achèvement d’un travail. Les réponses à un travail garantissent que les administrateurs de base de données ont connaissance de l'achèvement des travaux et de leur fréquence d'exécution. Les réponses classiques à un travail peuvent être :  
  
-   Une notification de l’opérateur, à l’aide de l’e-mail, de la radiomessagerie ou d’un message **net send** .  
  
    Utilisez une de ces réponses à un travail si l'opérateur doit exécuter une action en conséquence. Par exemple, si un travail de sauvegarde se termine avec succès, l'opérateur doit être averti afin qu'il enlève la bande de sauvegarde et qu'il la mette en lieu sûr.  
  
-   L'écriture d'un message d'événement dans le journal des applications Windows.  
  
    Vous pouvez choisir d'utiliser cette réponse uniquement en cas d'échec des travaux.  
  
-   La suppression automatique du travail.  
  
    Utilisez cette réponse à un travail si vous êtes certain de ne plus avoir besoin d'exécuter ce travail à nouveau.  
  
## <a name="related-tasks"></a>Tâches associées  
  
|||  
|-|-|  
|**Description**|**Rubrique**|  
|Explique comment avertir un opérateur de l'état d'un travail.|[Notifier l’état d’un travail à un opérateur](../../ssms/agent/notify-an-operator-of-job-status.md)|  
|Explique comment écrire l'état du travail dans le journal des applications Windows.|[Écrire l'état du travail dans le journal des applications Windows](../../ssms/agent/write-the-job-status-to-the-windows-application-log.md)|  
  
## <a name="see-also"></a>Voir aussi  
[Surveiller et répondre aux événements](../../ssms/agent/monitor-and-respond-to-events.md)  
  
