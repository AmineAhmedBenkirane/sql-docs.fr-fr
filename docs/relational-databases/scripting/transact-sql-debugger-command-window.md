---
title: "Commande, fenêtre | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: ssms
ms.service: 
ms.component: scripting
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.CommandWindow
helpviewer_keywords: Command Window [Transact-SQL]
ms.assetid: e567ebf9-0793-451b-92c7-26193a02d9da
caps.latest.revision: "14"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 6563a23f56ea61258ad79c86f075ef12c5f8499e
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="transact-sql-debugger---command-window"></a>Débogueur Transact-SQL - Fenêtre Commande
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)] Utilisez la **Fenêtre Commande** pour exécuter des commandes, telles que les commandes de débogage et de modification, sur le code contenu dans la fenêtre de l’éditeur de requête du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] en cours de débogage. Vous devez être en mode débogage pour pouvoir utiliser la **Fenêtre Commande**. Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] prend en charge la plupart des commandes qui sont également prises en charge dans la fenêtre [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **Command** window. Pour plus d’informations, consultez [Fenêtre Commande de Visual Studio](http://go.microsoft.com/fwlink/?LinkId=112007).  
  
## <a name="task-list"></a>Liste des tâches  
 **Pour accéder à la Fenêtre Commande**  
  
-   Dans le menu **Déboguer** , cliquez sur **Démarrer le débogage**.  
  
 **Pour imprimer la valeur d'une variable**  
  
-   Dans la **fenêtre Commande**, tapez **Debug.Print \<nom_variable>**, puis appuyez sur Entrée.  
  
 **Pour afficher des informations sur le thread actuel**  
  
-   Dans la **Fenêtre Commande**, tapez **Debug.ListThread**et appuyez sur Entrée.  
  
 **Pour ajouter une variable à la fenêtre Espion express**  
  
-   Dans la **fenêtre Commande**, tapez **Debug.QuickWatch \<nom_variable>**, puis appuyez sur Entrée.  
  
## <a name="see-also"></a>Voir aussi  
 [Débogueur Transact-SQL](../../relational-databases/scripting/transact-sql-debugger.md)  
  
  
