---
title: "NS$&lt;nom du service&gt; propriétés (onglet Ouvrir une session) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e6816ec-d4c5-4429-8033-b97427584890
caps.latest.revision: 14
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 46e784c7a83044249dcaf9ddc696be51f5b383a0
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="nsltservice-namegt-properties-log-on-tab"></a>NS$&lt;nom du service&gt; propriétés (onglet Ouvrir une session)
  L'onglet **Ouvrir une session** de la boîte de dialogue **Propriétés de Notification Services** permet de spécifier le compte utilisé par le service [!INCLUDE[ssNS](../../includes/ssns-md.md)] , ainsi que de démarrer et d'arrêter ce service.  
  
## <a name="options"></a>Options  
 **Compte système local**  
 Spécifie un compte système local, qui ne requiert pas de mot de passe. Cependant, le compte système local peut limiter l'interaction du service avec les autres serveurs, en fonction des privilèges accordés au compte.  
  
 **Ce compte**  
 Spécifiez un compte d'utilisateur local ou de domaine qui utilise l'authentification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows. [!INCLUDE[msCoName](../../includes/msconame-md.md)]recommande d’utiliser un compte d’utilisateur de domaine doté d’autorisations minimales pour les services. Pour plus d'informations sur la sélection d'un compte, recherchez dans la documentation en ligne la rubrique « Configuration des comptes de services Windows ».  
  
 **Nom du compte**  
 Spécifie le nom de compte d'utilisateur local ou de domaine.  
  
 **Mot de passe**  
 Tapez le mot de passe du compte.  
  
 **Confirmer le mot de passe**  
 Tapez de nouveau le mot de passe du compte.  
  
 **Démarrer**  
 Démarrez le service.  
  
 **Arrêter**  
 Arrête le service.  
  
 **Suspendre**  
 Suspend le service.  
  
 **Reprendre**  
 Reprend un service suspendu.  
  
  

