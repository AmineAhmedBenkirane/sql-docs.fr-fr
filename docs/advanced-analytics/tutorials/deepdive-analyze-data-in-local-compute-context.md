---
title: "Analyser les données dans le contexte de calcul Local | Documents Microsoft"
ms.custom: 
ms.date: 05/18/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology: r-services
ms.tgt_pltfrm: 
ms.topic: article
applies_to: SQL Server 2016
dev_langs: R
ms.assetid: 787bb526-4a13-40fa-9343-75d3bf5ba6a2
caps.latest.revision: "13"
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 514cc855af010347006054ad30fc5e5c36b16322
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="analyze-data-in-local-compute-context-data-science-deep-dive"></a>Analyser les données dans le contexte de calcul Local (présentation approfondie science des données)

Bien qu’il peut être plus rapide d’exécuter du code R complex en utilisant le contexte de serveur, il est parfois simplement plus pratique d’obtenir vos données de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et de les analyser sur votre station de travail privée.

Dans cette section, vous allez découvrir comment rebasculer vers un contexte de calcul local et déplacer des données entre des contextes pour optimiser les performances.

## <a name="create-a-local-summary"></a>Créer un résumé local

1. Modifiez le contexte de calcul pour effectuer tout votre travail localement.
  
    ```R
    rxSetComputeContext ("local")
    ```
  
2. Lors de l’extraction de données à partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous pouvez souvent obtenir de meilleures performances en augmentant le nombre de lignes extraites pour chaque lecture.  Pour ce faire, augmentez la valeur du paramètre *rowsPerRead* sur la source de données.
  
    ```R
    sqlServerDS1 <- RxSqlServerData(
       connectionString = sqlConnString,
       table = sqlFraudTable,
       colInfo = ccColInfo,
       rowsPerRead = 10000)
    ```
  
    Auparavant, la valeur de *rowsPerRead* était 5000.
  
3. À présent, appelez **rxSummary** dans la nouvelle source de données.
  
    ```R
    rxSummary(formula = ~gender + balance + numTrans + numIntlTrans + creditLine, data = sqlServerDS1)
    ```
  
    Les résultats réels doivent être le même que lorsque vous exécutez rxSummary dans le contexte de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ordinateur.  Toutefois, l’opération peut être plus rapide ou plus lente. Cela dépend en grande partie de votre connexion à la base de données, car les données sont transférées vers votre ordinateur local pour analyse.


## <a name="next--step"></a>Étape suivante

[Déplacement des données entre SQL Server et le fichier XDF](../../advanced-analytics/tutorials/deepdive-move-data-between-sql-server-and-xdf-file.md)

## <a name="previous-step"></a>Étape précédente

[Effectuer une analyse de segmentation à l’aide de rxDataStep](../../advanced-analytics/tutorials/deepdive-perform-chunking-analysis-using-rxdatastep.md)


