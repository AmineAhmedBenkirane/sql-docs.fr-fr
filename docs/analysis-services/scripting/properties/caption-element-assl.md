---
title: "Caption, élément (ASSL) | Documents Microsoft"
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
apiname: Caption Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: Caption
helpviewer_keywords: Caption element
ms.assetid: ed2be851-0ddc-4fa5-8aee-b2acb2e6d25e
caps.latest.revision: "36"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: b40ed163c4b41e4a36b9e19ab825f16208fd8895
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2017
---
# <a name="caption-element-assl"></a>Élément Caption (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Contient la légende de l’élément parent associé.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Action> <!-- or Translation -->  
   ...  
  <Caption>...</Caption>  
   ...  
</Action>  
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
|Élément parent|[Action](../../../analysis-services/scripting/objects/action-element-assl.md), [traduction](../../../analysis-services/scripting/objects/translation-element-assl.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 Les éléments qui correspondent aux parents de **légende** dans le modèle d’objet objets AMO (Analysis Management) sont <xref:Microsoft.AnalysisServices.Action> et <xref:Microsoft.AnalysisServices.Translation>.  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
