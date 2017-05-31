---
title: MSSQLSERVER_10538 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 10538 (Database Engine error)
ms.assetid: 284d19b4-4979-4cbe-a9be-ac1104433c69
caps.latest.revision: 10
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: fa1943af7087e3bc7205d62d978eeaedd677dc0f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/11/2017

---
# <a name="mssqlserver10538"></a>MSSQLSERVER_10538
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|10538|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|PG_INVALID_PLANGUIDE_HANDLE|  
|Texte du message|Impossible de trouver le repère de plan, car l'ID du repère de plan spécifié a la valeur Null ou n'est pas valide, ou vous n'avez pas d'autorisation sur l'objet référencé par le repère de plan. Vérifiez que l’ID du repère de plan est valide, que la session active est définie en fonction du contexte de base de données approprié et que vous disposez de l’autorisation ALTER ou de l’autorisation ALTER DATABASE sur l’objet référencé par le repère de plan.|  
  
## <a name="explanation"></a>Explication  
L'ID du repère de plan spécifié est Null ou n'est pas valide, ou vous n'avez pas d'autorisation sur l'objet référencé par le repère de plan.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Vérifiez que l'ID du repère de plan est valide, que la session active est définie en fonction du contexte de base de données approprié et que vous disposez de l'autorisation ALTER ou de l'autorisation ALTER DATABASE sur l'objet référencé par le repère de plan.  
  
## <a name="see-also"></a>Voir aussi  
[sp_create_plan_guide &#40;Transact-SQL&#41;](~/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql.md)  
[Repères de plan](~/relational-databases/performance/plan-guides.md)  
[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](~/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql.md)  
  

