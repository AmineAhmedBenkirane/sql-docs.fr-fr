---
title: "Le réplica de disponibilité n’est pas joint | Microsoft Docs"
ms.custom: 
ms.date: 05/17/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: availability-groups
ms.reviewer: 
ms.suite: sql
ms.technology: dbe-high-availability
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: sql13.swb.agdashboard.arp4joined.issues.f1
helpviewer_keywords: Availability Groups [SQL Server], policies
ms.assetid: 9c0d10b1-9e12-430c-83b9-ca2bd0a3afc4
caps.latest.revision: "15"
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 0b9ef6b8e69d81f55b9fcdea5f585bd0c4663e8d
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="availability-replica-is-not-joined"></a>Le réplica de disponibilité n'est pas joint
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## <a name="introduction"></a>Introduction  
  
|||  
|-|-|  
|**Nom de la stratégie**|État de jointure du réplica de disponibilité|  
|**Problème**|Le réplica de disponibilité n'est pas joint.|  
|**Catégorie**|**Avertissement**|  
|**Facette**|Réplica de disponibilité|  
  
## <a name="description"></a>Description  
 Cette stratégie vérifie l'état de jointure du réplica de disponibilité. La stratégie se trouve dans un état défectueux lorsque le réplica de disponibilité est ajouté au groupe de disponibilité, mais n'est pas joint correctement. Autrement, l'état de la stratégie est sain.  
  
> [!NOTE]  
>  Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], les informations sur les causes et les solutions possibles sont situées sous [Le réplica de disponibilité n’est pas joint](http://go.microsoft.com/fwlink/p/?LinkId=220859) sur TechNet Wiki.  
  
## <a name="possible-causes"></a>Causes possibles  
 Le réplica secondaire n'est pas joint au groupe de disponibilité. Pour qu'un réplica de disponibilité soit correctement joint au groupe de disponibilité, l'état de jointure doit être une instance autonome jointe (1) ou un cluster de basculement joint (2).  
  
## <a name="possible-solution"></a>Solution possible  
 Utilisez Transact-SQL, PowerShell ou SQL Server Management Studio pour joindre le réplica secondaire au groupe de disponibilité. Pour plus d’informations sur la jointure des réplicas secondaires aux groupes de disponibilité, consultez [Jointure d’un réplica secondaire à un groupe de disponibilité (SQL Server)](http://msdn.microsoft.com/library/ff878473\(SQL.110\).aspx).  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble des groupes de disponibilité Always On &#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
