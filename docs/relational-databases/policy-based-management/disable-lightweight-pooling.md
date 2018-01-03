---
title: "Désactiver le regroupement léger | Microsoft Docs"
ms.custom: 
ms.date: 08/09/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: performance-monitor
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Best Practices [Database Engine]
ms.assetid: 481bb43d-6fe5-497c-9096-971fb6bf733b
caps.latest.revision: "13"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 641090022517c5bae1cb0a3040de9216c9dd36a1
ms.sourcegitcommit: 2208a909ab09af3b79c62e04d3360d4d9ed970a7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2018
---
# <a name="disable-lightweight-pooling"></a>Désactiver le regroupement léger
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)] Cette règle vérifie que le regroupement léger est désactivé sur le serveur. Si la valeur 1 est affectée à l'option Regroupement léger, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bascule sur la planification en mode fibre. Le mode fibre est utile dans certaines situations, lorsque le basculement de contexte des travailleurs UMS est le principal goulot d'étranglement au niveau des performances. Dans la mesure où cette situation est inhabituelle, le mode fibre améliore rarement les performances ou l'évolutivité sur le système classique.  
  
## <a name="best-practices-recommendations"></a>Meilleures pratiques recommandées  
 L'option Regroupement léger ne doit être activée qu'après un test approfondi, une fois toutes les autres options de réglage des performances évaluées et lorsque le basculement de contexte est un problème connu dans votre environnement.  
  
 Nous vous déconseillons d'utiliser la planification en mode fibre pour les opérations courantes. En effet, elle peut dégrader les performances en ne permettant pas au basculement de contexte d'offrir ses avantages habituels et certains composants de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui utilisent le stockage TSL (Thread Stockage Local) ou des objets détenus par des threads, tels que des mutex (un type d'objet noyau Win32), ne peuvent pas fonctionner correctement en mode fibre.  
  
 Pour supprimer le regroupement léger, exécutez l’instruction suivante, puis redémarrez le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].  
  
```sql  
sp_configure 'show advanced options', 1;  
GO  
sp_configure 'lightweight pooling', 0;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="for-more-information"></a>Pour plus d'informations  
 [Regroupement léger (option de configuration de serveur)](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md)  
  
## <a name="see-also"></a> Voir aussi  
 [Contrôler et appliquer les meilleures pratiques à l'aide de la Gestion basée sur des stratégies](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
