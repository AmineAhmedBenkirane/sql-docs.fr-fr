---
title: PredictVariance (DMX) | Documents Microsoft
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
f1_keywords: PredictVariance
dev_langs: DMX
helpviewer_keywords: PredictVariance function
ms.assetid: 3c535237-083a-4102-bdfe-9f3c929e7b2c
caps.latest.revision: "34"
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: db699ed158838f0d259d5aaf6fdf163542b94d65
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="predictvariance-dmx"></a>PredictVariance (DMX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Retourne la variance d'une colonne spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
PredictVariance(<scalar column reference>)  
```  
  
## <a name="applies-to"></a>S'applique à  
 Colonne scalaire  
  
## <a name="return-type"></a>Type de retour  
 Une valeur scalaire du type spécifié par  *\<référence de colonne scalaire >*.  
  
## <a name="remarks"></a>Notes  
 Si la référence de colonne est discrète, la fonction **PredictVariance** retourne 0 car la variance ne peut être calculée à partir de valeurs discrètes.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant utilise une prédiction de jointure naturelle pour déterminer si un individu peut se révéler un acheteur potentiel de bicyclette selon le modèle d'exploration de données Arbre de décision TM et pour définir la variance de cette prévision.  
  
```  
SELECT  
  [Bike Buyer],  
  PredictVariance([Bike Buyer]) AS [Variance]  
FROM  
  [TM Decision Tree]  
NATURAL PREDICTION JOIN  
(SELECT 28 AS [Age],  
  '2-5 Miles' AS [Commute Distance],  
  'Graduate Degree' AS [Education],  
  0 AS [Number Cars Owned],  
  0 AS [Number Children At Home]) AS t  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence de fonction](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Fonctions &#40; DMX &#41;](../dmx/functions-dmx.md)   
 [Fonctions de prédiction générales &#40; DMX &#41;](../dmx/general-prediction-functions-dmx.md)  
  
  
