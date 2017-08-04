---
title: Types (DMX) de contenu | Documents Microsoft
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
- Data Mining Extensions [Analysis Services], content types
- content types [DMX]
- DMX [Analysis Services], content types
ms.assetid: ab9dd887-df8d-4878-96b0-635881892573
caps.latest.revision: 29
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 33af21a44066e96223bbfc07e39f4718edf87fc2
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="content-types-dmx"></a>Types de contenu (DMX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Pour fonctionner correctement, les algorithmes d'exploration de données ont besoin, outre le type de données, d'autres informations telles que le type de contenu.  Le type de contenu permet à l'algorithme de déterminer la manière d'utiliser les données de la colonne.  
  
 Chaque algorithme prend en charge des types de contenu spécifiques. Par exemple, l'algorithme [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes ne peut pas utiliser des colonnes continues. Pour utiliser une colonne continue dans un modèle [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes, vous devez discrétiser les données de la colonne. Certains algorithmes nécessitent certains types de contenu afin de fonctionner correctement. Par exemple, l'algorithme [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series nécessite une colonne temps clé pour identifier la durée de la collecte des données.  
  
 Pour une description complète du contenu types que [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] prend en charge, consultez [des Types de contenu &#40; exploration de données &#41;](../analysis-services/data-mining/content-types-data-mining.md).  
  
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
  
  

