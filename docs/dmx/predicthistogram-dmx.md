---
title: PredictHistogram (DMX) | Documents Microsoft
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
f1_keywords:
- PredictHistogram
dev_langs:
- DMX
helpviewer_keywords:
- PredictHistogram function
ms.assetid: 85ffc542-96e7-4f58-aaa3-34d76befcedf
caps.latest.revision: 34
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: e2e0d45b8169d567bbdc69a916f242b2707f6570
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="predicthistogram-dmx"></a>PredictHistogram (DMX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retourne une table qui représente un histogramme de la prévision d'une colonne donnée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
PredictHistogram(<scalar column reference> | <cluster column reference>)  
```  
  
## <a name="applies-to"></a>S'applique à  
 Référence de colonne scalaire ou référence de colonne de cluster. Peut être utilisée avec tous les types d'algorithmes, à l'exception de l'algorithme [!INCLUDE[msCoName](../includes/msconame-md.md)] Association.  
  
## <a name="return-type"></a>Type de retour  
 Table.  
  
## <a name="remarks"></a>Notes  
 Un histogramme génère des colonnes statistiques. La structure de colonne de l’histogramme retourné dépend du type de référence de colonne qui est utilisée avec la **PredictHistogram** (fonction).  
  
## <a name="scalar-columns"></a>Colonnes scalaires  
 Pour un \<référence de colonne scalaire >, l’histogramme qui le **PredictHistogram** retours de fonction comprend des colonnes suivantes :  
  
-   La valeur actuellement en cours de prévision  
  
-   **$Support**  
  
-   **$Probability**  
  
-   **$ProbabilityVariance**  
  
     [!INCLUDE[msCoName](../includes/msconame-md.md)]algorithmes d’exploration de données ne gèrent pas **$ProbabilityVariance**. Cette colonne contient toujours 0 pour les algorithmes [!INCLUDE[msCoName](../includes/msconame-md.md)].  
  
-   **$ProbabilityStdev**  
  
     [!INCLUDE[msCoName](../includes/msconame-md.md)]algorithmes d’exploration de données ne gèrent pas **$ProbabilityStdev**. Cette colonne contient toujours 0 pour les algorithmes [!INCLUDE[msCoName](../includes/msconame-md.md)].  
  
-   **$AdjustedProbability**  
  
     Le **$AdjustedProbability** colonne est un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] extension pour le [!INCLUDE[msCoName](../includes/msconame-md.md)] OLE DB pour l’exploration de données.  
  
## <a name="cluster-columns"></a>Colonnes de cluster  
 L’histogramme qui le **PredictHistogram** fonction retourne pour un \<référence de colonne de cluster > comporte les colonnes suivantes :  
  
-   **$Cluster** (représente le nom du cluster)  
  
-   **$Distance**  
  
-   **$Probability**  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant retourne l'état prévisible de la colonne Bike Buyer (Acheteur de bicyclette) dans une requête singleton. La requête retourne également les États les plus probables deux premiers de l’attribut Bike Buyer, selon la probabilité ajustée obtenue à l’aide de la **PredictHistogram** (fonction).  
  
```  
SELECT  
  [TM Decision Tree].[Bike Buyer],  
  TopCount(PredictHistogram([Bike Buyer]),$AdjustedProbability,3)  
From  
  [TM Decision Tree]  
NATURAL PREDICTION JOIN  
(SELECT 28 AS [Age],  
  '2-5 Miles' AS [Commute Distance],  
  'Graduate Degree' AS [Education],  
  0 AS [Number Cars Owned],  
  0 AS [Number Children At Home]) AS t  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Cluster &#40; DMX &#41;](../dmx/cluster-dmx.md)   
 [ClusterProbability &#40; DMX &#41;](../dmx/clusterprobability-dmx.md)   
 [PredictAdjustedProbability &#40; DMX &#41;](../dmx/predictadjustedprobability-dmx.md)   
 [PredictProbability &#40; DMX &#41;](../dmx/predictprobability-dmx.md)   
 [PredictStdev &#40; DMX &#41;](../dmx/predictstdev-dmx.md)   
 [PredictSupport &#40; DMX &#41;](../dmx/predictsupport-dmx.md)   
 [PredictVariance &#40; DMX &#41;](../dmx/predictvariance-dmx.md)   
 [Algorithmes d’exploration de données &#40; Analysis Services - Exploration de données &#41;](../analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence de fonction](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Fonctions &#40; DMX &#41;](../dmx/functions-dmx.md)   
 [Fonctions de prédiction générales &#40; DMX &#41;](../dmx/general-prediction-functions-dmx.md)  
  
  

