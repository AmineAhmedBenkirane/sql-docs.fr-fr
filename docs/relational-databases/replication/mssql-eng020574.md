---
title: MSSQL_ENG020574 | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MSSQL_ENG02574 error
ms.assetid: 4e98f8de-287c-4090-81ee-dc8f80dfa6a1
caps.latest.revision: "11"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7ff57dd45db47b24ebefddec17179d68f5466821
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="mssqleng020574"></a>MSSQL_ENG020574
    
## <a name="message-details"></a>Détails du message  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|20574|  
|Source de l'événement|MSSQLSERVER|  
|Composant|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nom symbolique||  
|Texte du message|L'Abonné '%s' avec un abonnement à l'article '%s' de la publication '%s' n'a pas réussi la validation de données.|  
  
## <a name="explanation"></a>Explication  
 Lors de la validation des données de l'Abonné par rapport aux données du serveur de publication, les données ne correspondaient pas, par conséquent la validation a échoué. Pour plus d'informations sur la validation, consultez [Validate Replicated Data](../../relational-databases/replication/validate-replicated-data.md).  
  
## <a name="user-action"></a>Action de l'utilisateur  
 Nous vous recommandons d'effectuer les opérations suivantes :  
  
-   Déterminez la raison de l'échec de la validation.  
  
-   Corrigez le problème sous-jacent qui est à l'origine de cet échec.  
  
-   Établissez la convergence des données en réinitialisant l'abonnement ou en utilisant une autre méthode.  
  
## <a name="see-also"></a>Voir aussi  
 [Guide de référence des erreurs et des événements &#40;réplication&#41;](../../relational-databases/replication/errors-and-events-reference-replication.md)  
  
  
