---
title: Curseurs XTP SQL Server | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84bf4654-3ef7-4d7f-a269-c8bb4ed4acad
caps.latest.revision: 6
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: b2442e178c91d459356330fe7342eb1319ccb270
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="sql-server-xtp-cursors"></a>Curseurs XTP SQL Server
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  L’objet de performance des curseurs XTP SQL Server contient des compteurs liés aux curseurs du moteur OLTP en mémoire interne. Les curseurs constituent les blocs de construction de bas niveau que le moteur OLTP en mémoire utilise pour traiter les requêtes [!INCLUDE[tsql](../../includes/tsql-md.md)] . Par conséquent, vous ne pouvez pas les contrôler directement.  
  
 Ce tableau décrit les compteurs **Curseurs XTP SQL Server** .  
  
|Compteur|Description|  
|-------------|-----------------|  
|**Suppressions des curseurs par seconde**|Nombre de suppressions des curseurs (en moyenne), par seconde.|  
|**Insertions des curseurs par seconde**|Nombre d'insertions des curseurs (en moyenne), par seconde.|  
|**Analyses des curseurs démarrées par seconde**|Nombre d'analyses des curseurs démarrées (en moyenne), par seconde.|  
|**Violations de contrainte unique des curseurs par seconde**|Nombre de violations de contrainte unique (en moyenne), par seconde.|  
|**Mises à jour des curseurs par seconde**|Nombre de mises à jour des curseurs (en moyenne), par seconde.|  
|**Conflits d'écriture des curseurs par seconde**|Nombre de conflits d'écriture-écriture vers la même version de ligne (en moyenne), par seconde.|  
|**Nouvelles tentatives d'analyse d'angles inutilisés par seconde (sortie utilisateur)**|Nombre de tentatives d'analyse dues à des conflits d'écriture lors des nettoyages d'angles inutilisés indiqué par une analyse de table complète de l'utilisateur (en moyenne), par seconde. Il s'agit d'un compteur de très bas niveau, non destiné au client.|  
|**Lignes expirées supprimées par seconde**|Nombre de lignes expirées supprimées par les curseurs (en moyenne), par seconde.|  
|**Lignes expirées touchées par seconde**|Nombre de lignes expirées touchées par les curseurs (en moyenne), par seconde.|  
|**Lignes retournées par seconde**|Nombre de lignes retournées par les curseurs (en moyenne), par seconde.|  
|**Lignes touchées par seconde**|Nombre de lignes touchées par les curseurs (en moyenne), par seconde.|  
|**Lignes en cours de suppression, touchées par seconde**|Nombre de lignes expirant touchées par les curseurs (en moyenne), par seconde. Une ligne expire si la transaction qui l’a supprimée est toujours active (c’est-à-dire qu’elle n’a pas encore été validée ou annulée.)|  
  
## <a name="see-also"></a>Voir aussi  
 [SQL Server XTP &#40;OLTP en mémoire&#41;, compteurs de performances](../../relational-databases/performance-monitor/sql-server-xtp-in-memory-oltp-performance-counters.md)  
  
  

