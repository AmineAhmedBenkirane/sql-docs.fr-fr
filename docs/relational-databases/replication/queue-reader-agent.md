---
title: "Agent de lecture de la file d’attente | Microsoft Docs"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.monitor.queuereaderagent.f1
helpviewer_keywords:
- Queue Reader Agent dialog box
ms.assetid: f02d24b6-dcb5-4126-b56e-fab41cfe4337
caps.latest.revision: 18
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 25110b487226028d9d24c6709e59cd2643fb4aac
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="queue-reader-agent"></a>Agent de lecture de la file d'attente
  La boîte de dialogue **Agent de lecture de la file d'attente** affiche des informations détaillées sur l'Agent de lecture de la file d'attente, y compris l'état, l'historique, des messages d'information et d'éventuels messages d'erreur.  
  
## <a name="options"></a>Options  
 Dans le menu **Affichage** , sélectionnez les sessions de l'Agent de lecture de la file d'attente à afficher. Sélectionnez ensuite une session particulière dans la grille étiquetée **Sessions de l'Agent de lecture de la file d'attente**. Des informations détaillées sur cette session s'affichent dans la grille étiquetée **Actions dans la session sélectionnée**. Si la session sélectionnée s'est terminée sur une erreur, la zone de texte étiquetée **Détails de l'erreur ou message de la session sélectionnée** s'affiche également.  
  
 **Affichage**  
 Sélectionnez les sessions de l'Agent de lecture de la file d'attente à afficher. L'Agent de lecture de la file d'attente s'exécute généralement en permanence : il se peut donc qu'il n'y ait qu'une session à afficher.  
  
 **État**  
 État de l'Agent de lecture de la file d'attente. La liste ci-dessous indique les valeurs d'état possibles :  
  
-   Erreur  
  
-   Nouvelle tentative de la commande qui a échoué  
  
-   Non exécuté  
  
-   Exécution en cours  
  
 **Start Time**  
 Heure d'ouverture de la session.  
  
 **Heure de fin**  
 Heure de fin de la session. Si l'agent ne s'est pas arrêté, ce champ est vide.  
  
 **Duration**  
 Durée d'exécution de l'Agent de lecture de la file d'attente dans cette session. Cette durée représente le temps écoulé si l'agent est en cours d'exécution et le temps total de la session si l'agent de la session s'est terminé.  
  
 **Message d'erreur**  
 Si une session s'est terminée sur une erreur, ce champ affiche le dernier message d'erreur enregistré par l'Agent de lecture de la file d'attente. Dans le cas contraire, ce champ est vide.  
  
 **Message d'action**  
 Tous les messages d'information ou d'erreur que l'Agent de lecture de la file d'attente a enregistrés pendant la session sélectionnée.  
  
 **Heure de l'action**  
 Heure à laquelle l'action décrite dans la colonne **Message d'action** s'est déroulée.  
  
 **Détails de l'erreur ou message de la session sélectionnée**  
 S'affiche uniquement si la session sélectionnée affiche une valeur **Erreur** dans la colonne **État** . La zone de texte affiche des informations d'erreur détaillées, ainsi que la commande émise au moment de l'erreur. Elle comporte également des liens vers des informations supplémentaires à propos de l'erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [Démarrer le moniteur de réplication](../../relational-databases/replication/monitor/start-the-replication-monitor.md)   
 [Afficher des informations et effectuer des tâches pour les agents associés à une publication &#40;moniteur de réplication&#41;](../../relational-databases/replication/monitor/view-information-and-perform-tasks-for-publication-agents.md)   
 [Surveillance de la réplication](../../relational-databases/replication/monitor/monitoring-replication-overview.md)   
 [Replication Agents Overview](../../relational-databases/replication/agents/replication-agents-overview.md)  
  
  
