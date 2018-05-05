---
title: Élément Filter (Binding) (ASSL) | Documents Microsoft
ms.custom: ''
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- Filter Element (Binding)
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- filter
helpviewer_keywords:
- Filter element
ms.assetid: 3d4cd169-2903-4266-8541-540ece424b7b
caps.latest.revision: 34
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7235255d7098c582c9a244569fe48375b2639a0c
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="filter-element-binding-assl"></a>Élément Filter (Binding) (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Contient une expression MDX (Multidimensional Expressions) qui filtre le contenu de l'élément parent.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<CubeDimensionBinding> <!-- or MeasureGroupBinding -->  
   ...  
   <Filter>...</Filter>  
   ...  
</CubeDimensionBinding>  
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
|Éléments parents|[CubeDimensionBinding](../../../analysis-services/scripting/data-type/cubedimensionbinding-data-type-assl.md), [MeasureGroupBinding](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-assl.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations sur la **liaison** type, y compris les tables de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objets ASSL (Scripting Language) de la **liaison** type et la hiérarchie d’héritage de **de liaison**  types, consultez [Type de données de liaison &#40;ASSL&#41;](../../../analysis-services/scripting/data-type/binding-data-type-assl.md).  
  
 Pour une vue d’ensemble des liaisons de données dans ASSL, consultez [des Sources de données et liaisons & #40 ; SSAS multidimensionnel & #41 ; ](../../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).  
  
 Les éléments qui correspondent aux parents de **filtre** dans le modèle d’objet objets AMO (Analysis Management) sont <xref:Microsoft.AnalysisServices.CubeDimensionBinding> et <xref:Microsoft.AnalysisServices.MeasureGroupBinding>.  
  
## <a name="see-also"></a>Voir aussi  
 [Type de liaison de données & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/data-type/binding-data-type-assl.md)   
 [Sources de données et des liaisons &#40;SSAS multidimensionnel&#41;](../../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md)   
 [Propriétés & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
