---
title: MSSQLSERVER_41333 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: errors-events
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 41333 (Database Engine error)
ms.assetid: c3c3ae9a-1e4c-4de6-ba72-2f393375b053
caps.latest.revision: 7
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 5cc570e4313ffb253f244af9f7d8e3a314f767cd
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="mssqlserver41333"></a>MSSQLSERVER_41333
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|ID d'événement|41333|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|CROSS_CONTAINER_ISOLATION_FAILURE|  
|Texte du message|Les transactions suivantes doivent accéder aux tables optimisées en mémoire et aux procédures stockées compilées en mode natif selon isolement Snapshot : les transactions RepeatableRead, les transactions Serializable et les transactions qui accèdent aux tables qui ne sont pas optimisées en mémoire selon l'isolement RepeatableRead ou Serializable.|  
  
## <a name="explanation"></a>Explication  
Des restrictions s'appliquent à l'utilisateur pour des niveaux d'isolement plus élevés, entre des transactions sur disque et des transactions XTP.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Ne tentez pas des opérations de haut niveau d'isolement sur les tables optimisées en mémoire (et les procédures compilées en mode natif) et les tables sur disque.  
  
Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](~/relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md).  
  
## <a name="see-also"></a> Voir aussi  
[OLTP en mémoire &#40;Optimisation en mémoire&#41;](~/relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
