---
title: IsInNode (DMX) | Documents Microsoft
ms.custom: 
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: IsInNode
dev_langs: DMX
helpviewer_keywords: IsInNode function
ms.assetid: 47b2114f-9ad6-45cc-9498-193ad6fa5288
caps.latest.revision: "29"
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: 895fe529a2fc67528d37b19202575aa0b9c14116
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="isinnode-dmx"></a>IsInNode (DMX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Indique si le nœud spécifié contient le cas courant.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
IsInNode(<NodeID>)  
```  
  
## <a name="return-type"></a>Type de retour  
 Type booléen  
  
## <a name="remarks"></a>Notes  
 **IsInNode** est utilisée uniquement dans [SELECT FROM &#60; modèle &#62;. CAS &#40; DMX &#41; ](../dmx/select-from-model-cases-dmx.md) et [SELECT FROM &#60; modèle &#62;. SAMPLE_CASES &#40; DMX &#41; ](../dmx/select-from-model-sample-cases-dmx.md) requêtes.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant retourne tous les cas qui ont été utilisés pour créer le modèle qui est associé au nœud spécifié dans la fonction IsInNode.  
  
```  
Select * from [TM Decision Tree].Cases  
WHERE IsInNode('0')  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence de fonction](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Fonctions &#40; DMX &#41;](../dmx/functions-dmx.md)   
 [Fonctions de prédiction générales &#40; DMX &#41;](../dmx/general-prediction-functions-dmx.md)  
  
  
