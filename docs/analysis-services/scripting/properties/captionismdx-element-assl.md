---
title: "Élément CaptionIsMdx (ASSL) | Documents Microsoft"
ms.custom: 
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname: CaptionIsMdx Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: CaptionIsMdx
helpviewer_keywords: CaptionIsMdx element
ms.assetid: 7569a75e-b3e0-4332-97d3-585abc546ada
caps.latest.revision: "36"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 0643c38f7cd44b0d84e89f5a2a51112620235cb7
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2017
---
# <a name="captionismdx-element-assl"></a>Élément CaptionIsMdx (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Définit si la légende pour le [Action](../../../analysis-services/scripting/objects/action-element-assl.md) élément est une expression MDX (Multidimensional Expressions).  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Action>  
   ...  
   <CaptionIsMdx>...</CaptionIsMdx>  
   ...  
</Action>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Booléen|  
|Valeur par défaut|**False**|  
|Cardinalité|0-1: élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Élément parent|[Action](../../../analysis-services/scripting/objects/action-element-assl.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 L’élément qui correspond au parent de **CaptionIsMdx** dans l’objet d’objets AMO (Analysis Management) est modèle <xref:Microsoft.AnalysisServices.Action>.  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
