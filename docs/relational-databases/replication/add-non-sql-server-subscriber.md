---
title: "Ajouter un Abonné non-SQL Server | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: sql13.rep.newsubwizard.addnonsqlsubscriber.f1
ms.assetid: 21beeaa0-4b9e-48da-be63-1b9ff14e03d2
caps.latest.revision: "11"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 46c2d0a3fcd7422543c5fe9561afdb83b9e5ea1f
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="add-non-sql-server-subscriber"></a>Ajouter un Abonné non-SQL Server
  La réplication prend en charge la création d'abonnement par envoi de données (push) à des publications d'instantané et transactionnelles pour les abonnés Oracle et IBM DB2.  
  
## <a name="options"></a>Options  
 **Type d'Abonné à ajouter**  
 Sélectionnez un abonné Oracle ou IBM DB2. Pour plus d’informations sur la prise en charge de ces Abonnés, consultez [Abonnés non-SQL Server](../../relational-databases/replication/non-sql/non-sql-server-subscribers.md).  
  
 **Nom de la source des données**  
 Nom utilisé pour localiser la base de données sur un réseau. La réplication produit une chaîne de connexion pour la base de données en utilisant le nom de la source de données, combiné à la connexion, au mot de passe et à toute autre option spécifiée dans la page **Sécurité de l'Agent de distribution** de cet Assistant.  
  
> [!NOTE]  
>  Le nom de la source de données et la chaîne de connexion ne sont pas validés par [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tant que l’Agent de distribution n’a pas tenté d’initialiser l’abonnement.  
  
## <a name="see-also"></a>Voir aussi  
 [Créer un abonnement pour un abonné non-SQL Server](../../relational-databases/replication/create-a-subscription-for-a-non-sql-server-subscriber.md)   
 [Abonnés non-SQL Server](../../relational-databases/replication/non-sql/non-sql-server-subscribers.md)   
 [S’abonner à des publications](../../relational-databases/replication/subscribe-to-publications.md)  
  
  
