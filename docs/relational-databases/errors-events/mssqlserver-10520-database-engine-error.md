---
title: MSSQLSERVER_10520 | Microsoft Docs
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
- 10520 (Database Engine error)
ms.assetid: cc8799f1-5b90-4248-b209-e1d5087f9529
caps.latest.revision: 9
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 3da0820c4c9ae4c09e7efaea09bf4b3d75657ad5
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="mssqlserver10520"></a>MSSQLSERVER_10520
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|10520|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|PG_PARAM_NOT_ALLOWED|  
|Texte du message|Impossible de créer le repère de plan ’%.ls’, car @type a été spécifié comme ’%ls’ et une valeur autre que Null est spécifiée pour le paramètre ’%ls’. Ce type requiert une valeur Null pour le paramètre. Spécifiez la valeur Null pour le paramètre ou remplacez le type par un type qui autorise une valeur autre que Null pour le paramètre.|  
  
## <a name="explanation"></a>Explication  
Le type spécifié dans @type nécessite une valeur Null pour le paramètre spécifié, mais une valeur non Null a été fournie.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Spécifiez la valeur Null pour le paramètre ou remplacez le type par un type qui autorise une valeur autre que Null pour le paramètre.  
  
## <a name="see-also"></a> Voir aussi  
[sp_create_plan_guide &#40;Transact-SQL&#41;](~/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql.md)  
[Repères de plan](~/relational-databases/performance/plan-guides.md)  
  
