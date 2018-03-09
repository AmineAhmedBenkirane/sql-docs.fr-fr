---
title: "Exécution de Transactions dans ADOMD.NET | Documents Microsoft"
ms.custom: 
ms.date: 02/14/2018
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- transactions [ADOMD.NET]
- ADOMD.NET, transactions
- AdomdTransaction object
ms.assetid: 7978c28b-c255-43c0-ad05-f38604d4d8fe
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 76964d9623a5ca477e2cc718d71739f4c69cdb1b
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2018
---
# <a name="connections-in-adomdnet---performing-transactions"></a>Connexions dans ADOMD.NET - exécution de Transactions
  Dans ADOMD.NET, l'objet <xref:Microsoft.AnalysisServices.AdomdClient.AdomdTransaction> permet de gérer le contexte de transaction pour un objet <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection> donné. Ces fonctionnalités vous permettent d'exécuter plusieurs commandes dans le même contexte. Chaque commande lit les mêmes données sans que les données lues ne soient modifiées entre chaque exécution de commande.  
  
> [!NOTE]  
>  Le <xref:Microsoft.AnalysisServices.AdomdClient.AdomdTransaction> classe est l’implémentation de la **System.Data.IDbTransaction** interface, une partie de la [!INCLUDE[msCoName](../../includes/msconame-md.md)] bibliothèque de classes .NET Framework et implémentée par tous les fournisseurs de données .NET Framework qui prennent en charge des transactions.  
  
 L'objet <xref:Microsoft.AnalysisServices.AdomdClient.AdomdTransaction> ne prend en charge que les transactions validées en lecture, dans lesquelles les verrous partagés sont maintenus pendant la lecture des données afin d'éviter des lectures erronées.  
  
 L'objet <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection> est utilisée pour démarrer la transaction. Pour utiliser la transaction, des commandes sont ensuite exécutées sur la connexion qui a démarré la transaction. Une fois que vous avez terminé la transaction, vous pouvez soit l'annuler, soit la valider.  
  
## <a name="starting-a-transaction"></a>Démarrage d'une transaction  
 Vous pouvez créer une instance d'un objet <xref:Microsoft.AnalysisServices.AdomdClient.AdomdTransaction> en appelant la méthode <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.BeginTransaction%2A> de l'objet <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>. L'exemple suivant montre comment créer une instance de l'objet <xref:Microsoft.AnalysisServices.AdomdClient.AdomdTransaction> :  
  
```  
Dim objTransaction As AdomdTransaction = objConnection.BeginTransaction()  
AdomdTransaction objTransaction = objConnection.BeginTransaction();  
```  
  
## <a name="rolling-back-a-transaction"></a>Annulation d'une transaction  
 Pour annuler une transaction incomplète existante, vous devez appeler la méthode <xref:Microsoft.AnalysisServices.AdomdClient.AdomdTransaction.Rollback%2A> de l'objet <xref:Microsoft.AnalysisServices.AdomdClient.AdomdTransaction>. Si vous appelez cette méthode pour une transaction complète existante, une exception est levée.  
  
## <a name="committing-a-transaction"></a>Validation d'une transaction  
 Après avoir appelé la méthode <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.BeginTransaction%2A> pour démarrer une transaction, vous pouvez terminer la transaction en appelant la méthode <xref:Microsoft.AnalysisServices.AdomdClient.AdomdTransaction.Commit%2A> de l'objet <xref:Microsoft.AnalysisServices.AdomdClient.AdomdTransaction>. Si cette méthode est appelée pour une transaction complète existante, une exception est levée.  
  
## <a name="see-also"></a>Voir aussi  
 [Établissement de connexions dans ADOMD.NET](../../analysis-services/multidimensional-models-adomd-net-client/connections-in-adomd-net.md)   
 [Programmation du client ADOMD.NET](../../analysis-services/multidimensional-models-adomd-net-client/adomd-net-client-programming.md)  
  
  
