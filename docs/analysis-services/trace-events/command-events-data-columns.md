---
title: Colonnes de données des événements de commande | Documents Microsoft
ms.custom: ''
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- Command Events event category
ms.assetid: 7169f1e2-c6be-4d8c-b147-25719b84bc2c
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a546ed5569d8d80c36d65f21eb3021b478831cfb
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="command-events-data-columns"></a>Colonnes de données des événements de commande
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  Le tableau ci-dessous répertorie les colonnes de données de chaque classe d'événements de la catégorie d'événement **Événements de commande** .  
  
 La catégorie d'événement **Événements de commande** contient les classes d'événements suivantes :  
  
-   [Command Begin](#bkmk_1)  
  
-   [Command End](#bkmk_2)  
  
 Les tableaux suivants répertorient les colonnes de données de chacune de ces classes d'événements.  
  
##  <a name="bkmk_1"></a> Classe Command Begin—Colonnes de données  
  
|Colonne de données|Description|  
|-----------------|-----------------|  
|ConnectionID|Contient l'ID de connexion unique associé à l'événement de commande.|  
|TextData|Contient les données texte associées à l'événement de commande.|  
|ServerName|Contient le nom de l'instance [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sur laquelle l'événement de commande s'est produit.|  
|CurrentTime|Contient l'heure actuelle de l'événement de commande.|  
|DatabaseName|Contient le nom de la base de données dans laquelle la commande est exécutée.|  
|EventSubclass|Contient la classe d'événements dans l'événement de commande. Valeurs prises en charge :<br /><br /> 0 : Create<br /><br /> 1 : Alter<br /><br /> 2 : Delete<br /><br /> 3 : Process<br /><br /> 4 : DesignAggregations<br /><br /> 5 : WBInsert<br /><br /> 6 : WBUpdate<br /><br /> 7 : WBDelete<br /><br /> 8 : Backup<br /><br /> 9 : Restore<br /><br /> 10 : MergePartitions<br /><br /> 11 : Subscribe<br /><br /> 12 : Batch<br /><br /> 13 : BeginTransaction<br /><br /> 14 : CommitTransaction<br /><br /> 15 : RollbackTransaction<br /><br /> 16 : GetTransactionState<br /><br /> 17 : Cancel<br /><br /> 18 : Synchronize<br /><br /> 19 : Import80MiningModels<br /><br /> 20 : Attach<br /><br /> 21 : Detach<br /><br /> 22 : SetAuthContext<br /><br /> 23 : ImageLoad<br /><br /> 24 : ImageSave<br /><br /> 10000 : Other|  
|NTUserName|Contient le nom d'utilisateur Windows associé à l'événement de commande. Le nom d'utilisateur a la forme canonique. engineering.microsoft.com/software/user, par exemple.|  
|RequestProperties|Contient les propriétés de demande XMLA (XML for Analysis) associées à l'événement de commande.|  
|SPID|Contient l’ID de processus serveur (SPID) qui identifie de manière unique la session utilisateur associée à l’événement de commande. Le SPID correspond directement au GUID de session utilisé par XMLA.|  
|StartTime|Contient l'heure de début (si disponible) de l'événement de commande.|  
|SessionType|Contient l'entité qui a provoqué l'opération.|  
|NTDomainName|Contient le compte de domaine Windows associé à l'événement d'autorisation de l'objet.|  
|ClientProcessID|Contient l'ID de processus client unique associé à l'événement de commande.|  
  
##  <a name="bkmk_2"></a> Classe Command End—Colonnes de données  
  
|Colonne de données|Description|  
|-----------------|-----------------|  
|ConnectionID|Contient l'ID de connexion unique associé à l'événement de commande.|  
|TextData|Contient les données texte associées à l'événement de commande.|  
|ServerName|Contient le nom de l'instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sur laquelle l'événement de commande s'est produit.|  
|CurrentTime|Contient l'heure actuelle de l'événement de commande. Pour le filtrage, les formats sont *YYYY*-*MM*-*DD* et *YYYY*-*MM*-*DD HH*:*MM*:*SS*.|  
|DatabaseName|Contient le nom de la base de données dans laquelle la commande est exécutée.|  
|Duration|Contient le délai approximatif entre l'événement de début de commande et de fin de commande.|  
|EndTime|Contient l'heure de fin de l'événement de commande. Pour le filtrage, les formats sont *YYYY*-*MM*-*DD* et *YYYY*-*MM*-*DD HH*:*MM*:*SS*.|  
|EventSubclass|Contient la classe d'événements dans l'événement de commande. Valeurs prises en charge :<br /><br /> 0 : Create<br /><br /> 1 : Alter<br /><br /> 2 : Delete<br /><br /> 3 : Process<br /><br /> 4 : DesignAggregations<br /><br /> 5 : WBInsert<br /><br /> 6 : WBUpdate<br /><br /> 7 : WBDelete<br /><br /> 8 : Backup<br /><br /> 9 : Restore<br /><br /> 10 : MergePartitions<br /><br /> 11 : Subscribe<br /><br /> 12 : Batch<br /><br /> 13 : BeginTransaction<br /><br /> 14 : CommitTransaction<br /><br /> 15 : RollbackTransaction<br /><br /> 16 : GetTransactionState<br /><br /> 17 : Cancel<br /><br /> 18 : Synchronize<br /><br /> 19 : Import80MiningModels<br /><br /> 20 : Attach<br /><br /> 21 : Detach<br /><br /> 22 : SetAuthContext<br /><br /> 23 : ImageLoad<br /><br /> 24 : ImageSave<br /><br /> 10000 : Other|  
|NTCanonicalUserName|Contient le nom d'utilisateur Windows associé à l'événement de commande. Le nom d'utilisateur a la forme canonique. engineering.microsoft.com/software/user, par exemple.|  
|NTUserName|Contient le compte d'utilisateur Windows associé à l'événement de commande.|  
|SPID|Contient l'ID de processus serveur (SPID) qui identifie de manière unique la session utilisateur associée à l'événement de commande. Le SPID correspond directement au GUID de session utilisé par XMLA.|  
|StartTime|Contient l'heure de début (si disponible) de l'événement de fin de commande.|  
|CPUTime|Contient le temps processeur (en millisecondes) utilisé par le processus entre l'événement de début de commande et l'événement de fin de commande.|  
|Erreur|Contient le numéro d'erreur de toute erreur associée à l'événement de commande.|  
|Severity|Contient le niveau de gravité d'une exception associée à l'événement de commande. Valeurs possibles :<br /><br /> 0 = Réussite<br /><br /> 1 = Informationnelle<br /><br /> 2 = Avertissement<br /><br /> 3 = Erreur|  
|Réussi|Contient la réussite ou l'échec de l'événement de commande. Valeurs possibles :<br /><br /> 0 = Échec<br /><br /> 1 = Réussite|  
|SessionType|Contient l'entité ayant provoqué l'opération associée à l'événement de commande.|  
|NTDomainName|Contient le compte de domaine Windows associé à l'événement de commande.|  
|ClientProcessID|Contient l'ID de processus client unique associé à l'événement de commande.|  
  
## <a name="see-also"></a>Voir aussi  
 [Catégorie d’événement événements commande](../../analysis-services/trace-events/command-events-event-category.md)  
  
  
