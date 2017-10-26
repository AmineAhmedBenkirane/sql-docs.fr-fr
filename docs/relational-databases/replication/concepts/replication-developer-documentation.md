---
title: "Documentation pour le développeur de réplication | Microsoft Docs"
ms.custom:
- rickbyh
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- developer's guide [SQL Server replication]
- programming [SQL Server replication]
- replication [SQL Server], development
ms.assetid: 7ee134ae-1cab-4a35-8017-8ac6d8fc64b6
caps.latest.revision: 40
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: b44693e1193670ee6b8f50f6fd7bd8a94181e2be
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="replication-developer-documentation"></a>Documentation pour le développeur de réplication
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  La possibilité de configurer, de gérer et d'analyser par programme une topologie de réplication entraîne la simplification des tâches de réplication répétitives et l'amélioration de l'expérience utilisateur pour vos applications basées sur la réplication. Grâce à la programmation de la réplication, les utilisateurs finaux peuvent bénéficier de fonctionnalités de réplication personnalisées sans avoir à connaître les procédures stockées de réplication et les fichiers exécutables de l'Agent de réplication. Ils n'ont pas non plus besoin d'utiliser l'interface utilisateur pour la réplication implémentée par [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].  
  
 Un accès par programme aux services de réplication peut être utile pour vos applications dans les situations suivantes :  
  
-   Ajout de fonctionnalités de réplication à une application existante pour utilisateur final, telles que la synchronisation d'un abonnement par extraction de données lorsque l'utilisateur clique sur un bouton.  
  
-   Création d'une interface utilisateur Web pour administrer la réplication à distance.  
  
-   Création d'une interface utilisateur personnalisée qui expose uniquement une partie des fonctionnalités d'administration (pour administrer à distance plusieurs topologies de réplication à partir d'un même emplacement) ou qui associe des fonctionnalités d'administration et de synchronisation.  
  
-   Amélioration d'un outil d'analyse existant en intégrant la possibilité d'analyser l'état d'une publication, d'un abonnement ou au niveau du serveur de distribution.  
  
-   Création d'une application personnalisée pour administrer ou synchroniser des abonnements sur un serveur de publication Oracle.  
  
-   Écriture de règles d'entreprise personnalisées qui sont exécutées lors de la synchronisation d'un abonnement de fusion.  
  
-   Génération de scripts [!INCLUDE[tsql](../../../includes/tsql-md.md)] pouvant être exécutés à plusieurs reprises lors de la configuration de nouveaux abonnés.  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vous permet non seulement de contrôler par programme les agents de réplication, mais aussi d'administrer et d'analyser par programme une topologie de réplication. Pour en savoir plus sur la programmation de la réplication, consultez [Concepts de programmation en matière de réplication](../../../relational-databases/replication/concepts/replication-programming-concepts.md).  
  
## <a name="in-this-section"></a>Dans cette section  
 [Concepts de programmation en matière de réplication](../../../relational-databases/replication/concepts/replication-programming-concepts.md)  
 Décrit les étapes de planification permettant de développer une application qui utilise la réplication.  
  
 [Concepts liés aux procédures stockées système de réplication](../../../relational-databases/replication/concepts/replication-system-stored-procedures-concepts.md)  
 Décrit comment les procédures stockées système peuvent être utilisées pour assurer un accès par programme dans une topologie de réplication.  
  
 [Concepts liés à Replication Management Objects](../../../relational-databases/replication/concepts/replication-management-objects-concepts.md)  
 Explique les concepts relatifs à l'utilisation de Replication Management Objects. Il s'agit d'un assembly de code managé qui encapsule les fonctionnalités de réplication pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].   
  
 [Concepts des exécutables de l’agent de réplication](../../../relational-databases/replication/concepts/replication-agent-executables-concepts.md)  
 Décrit l'utilisation des fichiers exécutables de l'Agent de réplication.  
  
 [Guide du développeur : rubriques Procédure &#40;réplication&#41;](../../../relational-databases/replication/concepts/developer-s-guide-how-to-topics-replication.md)  
 Fournit la liste des rubriques Procédure liées à la réplication.  
  
  

