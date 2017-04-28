---
title: "Rechercher des problèmes de délai d’E/S dans le sous-système d’E/S disque | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 23863340-d8e0-48d6-928b-462745885d37
caps.latest.revision: 10
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: eaaf5e692a33c6f418d6a117b7f1231c20d2ba71
ms.lasthandoff: 04/11/2017

---
# <a name="check-disk-input-and-output-subsystem-for-io-delay-problems"></a>Rechercher des problèmes de délai d’E/S dans le sous-système d’E/S disque
  Cette règle recherche le message d'erreur 833 dans le journal des événements. Ce message indique que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a émis une demande de lecture ou d'écriture à partir du disque et que la demande a mis plus de 15 secondes à retourner un résultat. Cette erreur est signalée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et indique un problème avec le sous-système d'E/S disque. Des délais de cette importance peuvent sévèrement nuire aux performances de votre environnement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="best-practices-recommendations"></a>Meilleures pratiques recommandées  
 Essayez de résoudre le problème en recherchant dans le journal des événements système d'éventuels messages d'erreur liés au matériel. Examinez également les journaux spécifiques au matériel s'ils sont disponibles.  
  
 Utilisez l'Analyseur de performances pour consulter les compteurs suivants :  
  
-   Moy. disque s/transfert  
  
-   Longueur moyenne de la file d'attente du disque  
  
-   Longueur actuelle de la file d'attente du disque  
  
 Par exemple, la Moy. disque s/transfert sur un ordinateur exécutant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est généralement inférieure à 15 millisecondes. Si la valeur Moy. disque s/transfert augmente, cela indique que le sous-système d'E/S disque ne parvient pas parfaitement à suivre la demande d'E/S.  
  
## <a name="for-more-information"></a>Pour plus d'informations  
   
  
 [Article 897284 de la Base de connaissances Microsoft](http://go.microsoft.com/fwlink/?linkid=117743)  
  
 [SQL Server I/O Basics, Chapter 2 (en anglais)](http://go.microsoft.com/fwlink/?LinkId=69370)  
  
  

