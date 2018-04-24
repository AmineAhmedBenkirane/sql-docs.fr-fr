---
title: MSSQLSERVER_1222 | Microsoft Docs
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
- 1222 (Database Engine error)
ms.assetid: c5b1c2f4-f591-4cc1-aa17-204636a27f29
caps.latest.revision: 20
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c52267e69318b7fba1b6a0edd2a416a3569c203e
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="mssqlserver1222"></a>MSSQLSERVER_1222
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|1222|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|LK_TIMEOUT|  
|Texte du message|Délai de requête de verrou dépassé.|  
  
## <a name="explanation"></a>Explication  
Une autre transaction a maintenu un verrou sur une ressource requise plus longtemps que cette requête pouvait attendre.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Effectuez les tâches ci-dessous pour atténuer le problème :  
  
1.  Localisez la transaction qui maintient le verrou sur la ressource requise, si possible. Utilisez les vues de gestion dynamique **sys.dm_os_waiting_tasks** et **sys.dm_tran_locks**.  
  
2.  Si la transaction continue à maintenir le verrou, mettez fin à cette transaction, le cas échéant.  
  
3.  Exécutez de nouveau la requête.  
  
Si cette erreur se produit fréquemment, modifiez le délai d'attente de verrouillage ou modifiez les transactions incriminées pour qu'elles maintiennent le verrou moins longtemps.  
  
