---
title: Valider tous les abonnements | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: sql13.rep.validate.allsubscriptions.f1
helpviewer_keywords: Validate All Subscriptions dialog box
ms.assetid: 32e31469-36e4-42d9-a57a-12388bfd229d
caps.latest.revision: "24"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 61f5ab9a4c112157cd1869c240ae73e5770ba1a0
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="validate-all-subscriptions"></a>Valider tous les abonnements
  La boîte de dialogue **Valider tous les abonnements** permet d'indiquer que tous les abonnements à une publication de fusion doivent être validés lors de la prochaine exécution de l'Agent de fusion de chaque abonnement. Le résultat de la validation figure dans le Moniteur de réplication. Pour plus d’informations, voir [Validate Data at the Subscriber](../../relational-databases/replication/validate-data-at-the-subscriber.md).  
  
 Vous pouvez également valider un seul abonnement en cliquant avec le bouton droit de la souris sur un abonnement dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , puis en choisissant **Valider l'abonnement**.  
  
## <a name="options"></a>Options  
 **Vérifier uniquement le nombre de lignes**  
 Sélectionnez cette option pour indiquer si la table au niveau de l'Abonné a le même nombre de lignes que la table sur le serveur de publication. Cette méthode ne valide pas le contenu des correspondances de lignes. La validation du nombre de lignes fournit une approche allégée de la validation qui vous permet de savoir qu'il existe des problèmes au niveau des données.  
  
 **Vérifier le nombre de lignes et comparer les totaux de contrôle pour vérifier les données de ligne**  
 Outre le comptage des lignes sur le serveur de publication et sur l'Abonné, une somme de contrôle de toutes les données est calculée à l'aide de l'algorithme de somme de contrôle binaire. Si le nombre de lignes est erroné, la somme de contrôle n'est pas effectuée. Cette option n'est pas valide pour [!INCLUDE[ssEW](../../includes/ssew-md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Valider des données répliquées](../../relational-databases/replication/validate-replicated-data.md)  
  
  
