---
title: Utilisation (DMX) | Documents Microsoft
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- DMX
helpviewer_keywords:
- column usage [DMX]
- Data Mining Extensions [Analysis Services], column usage types
- DMX [Analysis Services], column usage types
ms.assetid: 6d7ae72a-f5b5-4744-a3a2-46ccd6432c1a
caps.latest.revision: 31
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 2acfde9b8d7c9d13fc626b006116e9b3760fd432
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="usage-dmx"></a>Utilisation (DMX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Lorsque vous utilisez des Extensions DMX (Data Mining) pour définir un nouveau modèle d’exploration de données dans [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], vous devez spécifier la façon dont l’algorithme d’exploration de données qui génère le modèle utilisera chaque colonne. Vous pouvez spécifier une colonne comme étant l'un des types suivants :  
  
-   **Clé**  
  
-   **Séquence de touches**  
  
-   **Temps clé**  
  
-   **Prédire**  
  
-   **PredictOnly**  
  
 En langage DMX, les colonnes non spécifiées sont considérées comme des colonnes d'entrée.  
  
 Pour traiter correctement un modèle, l'algorithme doit savoir quelle est la colonne clé qui identifie de manière unique chaque ligne, quelle est la colonne cible pour la création des prédictions si vous créez un modèle prévisible et quelles colonnes utiliser comme colonnes d'entrée pour créer les relations qui prévoient la colonne cible.  
  
 Colonnes qui sont spécifiées en tant que le **Predict** type sont utilisées en tant que colonnes d’entrée et de sortie. Colonnes qui sont spécifiées en tant que **PredictOnly** sont uniquement utilisées comme colonnes de sortie. Il est possible que des algorithmes spécifiques considèrent les colonnes de type Predict différemment.  
  
 Pour plus d’informations sur la colonne de l’utilisation de types que [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] prend en charge, consultez [colonnes du modèle d’exploration de données](../analysis-services/data-mining/mining-model-columns.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Algorithmes d’exploration de données &#40; Analysis Services - Exploration de données &#41;](../analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence](../dmx/data-mining-extensions-dmx-reference.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Éléments de syntaxe](../dmx/data-mining-extensions-dmx-syntax-elements.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence de fonction](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence des opérateurs](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence des instructions](../dmx/data-mining-extensions-dmx-statements.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Conventions de syntaxe](../dmx/data-mining-extensions-dmx-syntax-conventions.md)   
 [Fonctions de prédiction générales &#40; DMX &#41;](../dmx/general-prediction-functions-dmx.md)   
 [Structure et utilisation des requêtes de prédiction DMX](../dmx/structure-and-usage-of-dmx-prediction-queries.md)   
 [Présentation de l’instruction DMX Select](../dmx/understanding-the-dmx-select-statement.md)  
  
  

