---
title: IsDescendant (DMX) | Documents Microsoft
ms.custom: ''
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: data-mining
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- IsDescendant
dev_langs:
- DMX
helpviewer_keywords:
- IsDescendant function
ms.assetid: d9fe7446-edb5-487b-8ea6-c9efaccf6d90
caps.latest.revision: 29
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: 179a9f3f04db55cffb74f6417c3339ceeb20aa11
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="isdescendant-dmx"></a>IsDescendant (DMX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Indique si le nœud actuel provient du nœud spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
IsDescendant(<NodeID>)  
```  
  
## <a name="return-type"></a>Type de retour  
 Type booléen  
  
## <a name="remarks"></a>Notes   
 **IsDescendant** est utilisée uniquement dans [SELECT FROM &#60; modèle &#62;. CONTENU &#40; DMX &#41; ](../dmx/select-from-model-content-dmx.md) et [SELECT FROM &#60; modèle &#62;. DIMENSION_CONTENT &#40; DMX &#41; ](../dmx/select-from-model-dimension-content-dmx.md) requêtes.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant retourne tous les cas qui descendent du nœud spécifié dans la fonction IsDescendant.  
  
```  
SELECT * FROM [TM Decision Tree].CONTENT  
WHERE IsDescendant('00000000100')  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence de fonction](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Fonctions &#40; DMX &#41;](../dmx/functions-dmx.md)   
 [Fonctions de prédiction générales &#40; DMX &#41;](../dmx/general-prediction-functions-dmx.md)  
  
  
