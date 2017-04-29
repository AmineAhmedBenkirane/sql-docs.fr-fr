---
title: MSSQLSERVER_8966 | Microsoft Docs
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
- 8966 (Database Engine error)
ms.assetid: 6b1150fd-9dfd-4df9-8f08-8eca237667db
caps.latest.revision: 17
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 4c93290eaf142f7048458d9e4a18d12bc70e028b
ms.lasthandoff: 04/11/2017

---
# <a name="mssqlserver8966"></a>MSSQLSERVER_8966
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|8966|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|DBCC3_FAILED_TO_READ_AND_LATCH_PAGE|  
|Texte du message|Impossible de lire et de verrouiller la page P_ID avec le type de verrou TYPE. Échec de OPERATION.|  
  
## <a name="explanation"></a>Explication  
La lecture de la page a échoué ou un verrou n'a pas pu être pris en compte sur une page PFS ou GAM. Le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut contenir des messages relatifs au dépassement de délai d’attente de verrous ou d’autres messages associés.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Vérifiez les éventuels messages associés dans le journal des erreurs SQL et résolvez ces erreurs.  
  

