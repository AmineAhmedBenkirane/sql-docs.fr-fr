---
title: Tendance d’élément (ASSL) | Documents Microsoft
ms.custom: ''
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- Trend Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- Trend
helpviewer_keywords:
- Trend element
ms.assetid: d1d92d10-a181-4402-aacb-c0b2adc96bba
caps.latest.revision: 34
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: dd6428e401874f9a1f93f7039bbe121d0761fc7b
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="trend-element-assl"></a>Élément Trend (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Contient une expression MDX (Multidimensional Expressions) qui retourne un indicateur de tendance pour un [Kpi](../../../analysis-services/scripting/objects/kpi-element-assl.md) élément.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Kpi>  
   ...  
   <Trend>...</Trend>  
   ...  
</Kpi>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne|  
|Valeur par défaut|Aucune|  
|Cardinalité|0-1: élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Élément parent|[Indicateur de performance clé](../../../analysis-services/scripting/objects/kpi-element-assl.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 L'élément **Trend** contient une expression MDX qui correspond à un nombre compris entre -1 et 1.  
  
 L’élément qui correspond au parent de **tendance** dans l’objet d’objets AMO (Analysis Management) est modèle <xref:Microsoft.AnalysisServices.Kpi>.  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
