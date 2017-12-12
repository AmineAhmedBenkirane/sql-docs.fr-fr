---
title: "Implémenter des travaux | Microsoft Docs"
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
- jobs [SQL Server Agent]
- SQL Server Agent jobs
- SQL Server Agent jobs, about jobs
- jobs [SQL Server Agent], about jobs
ms.assetid: 69e06724-25c7-4fb3-8a5b-3d4596f21756
caps.latest.revision: "4"
author: stevestein
ms.author: sstein
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 2c24813e306a43cf1adce27f71afe7c209194d53
ms.sourcegitcommit: b2d8a2d95ffbb6f2f98692d7760cc5523151f99d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2017
---
# <a name="implement-jobs"></a>Implémenter des travaux
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)] Vous pouvez utiliser les travaux de [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent pour automatiser les tâches d’administration régulières et les exécuter de façon récurrente, dans le but de rendre l’administration plus efficace.  
  
Un travail est constitué d'une série d'opérations spécifiques exécutées de manière séquentielle par [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent. Un travail peut effectuer une grande variété d'activités, y compris l'exécution de scripts [!INCLUDE[tsql](../../includes/tsql_md.md)] , d'applications de ligne de commande, de scripts Microsoft ActiveX, de packages Integration Services, de commandes et de requêtes Analysis Services ou de tâches de réplication. Les travaux peuvent exécuter des tâches répétitives ou des tâches planifiables ; en outre, ils peuvent notifier leur état automatiquement aux utilisateurs en générant des alertes, ce qui simplifie grandement l'administration de [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] .  
  
Vous pouvez exécuter un travail manuellement ou le configurer de manière à ce qu'il s'exécute en fonction d'une planification ou en réponse à des alertes.  
  
## <a name="related-tasks"></a>Tâches associées  
  
|||  
|-|-|  
|**Description**|**Rubrique**|  
|Contient des informations sur la création de travaux et l'affectation de propriétés.|[Créer des travaux](../../ssms/agent/create-jobs.md)|  
|Contient des informations sur l'organisation des travaux en catégories.|[Organiser les travaux](../../ssms/agent/organize-jobs.md)|  
|Contient des informations relatives aux différents types d'étapes de travail que vous pouvez gérer et à la procédure à suivre à cet effet.|[Gérer les étapes de travail](../../ssms/agent/manage-job-steps.md)|  
|Contient des informations relatives à la planification du démarrage de l'exécution des travaux et à leur fréquence d'exécution.|[Créer des planifications et les attacher à des travaux](../../ssms/agent/create-and-attach-schedules-to-jobs.md)|  
|Contient des informations relatives à l'exécution manuelle des travaux (sans planification).|[Exécuter des travaux](../../ssms/agent/run-jobs.md)|  
|Contient des informations relatives à la configuration du comportement de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] par rapport aux travaux. Par exemple, vous pouvez configurer [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent de manière à notifier aux administrateurs l'achèvement des travaux.|[Spécifier des réponses à un travail](../../ssms/agent/specify-job-responses.md)|  
|Contient des informations relatives à la visualisation des travaux existants, à leur historique une fois exécutés et à leur modification.|[Afficher ou modifier les travaux](../../ssms/agent/view-or-modify-jobs.md)|  
|Contient des informations sur la suppression de travaux.|[Supprimer des travaux](../../ssms/agent/delete-jobs.md)|  
  
## <a name="see-also"></a>Voir aussi  
[Implémenter la sécurité de l'Agent SQL Server](../../ssms/agent/implement-sql-server-agent-security.md)  
  
