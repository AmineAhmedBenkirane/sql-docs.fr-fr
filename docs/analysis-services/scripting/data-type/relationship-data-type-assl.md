---
title: "Type de données de relation (ASSL) | Documents Microsoft"
ms.custom: 
ms.date: 03/03/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
ms.assetid: 73d7c48d-d8e0-4119-849d-b5f912d449e4
caps.latest.revision: "5"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 4611e01a37b0bbc9856eb7dd268db614bf718357
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="relationship-data-type-assl"></a>Type de données de relation (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Définit un type de données primitif qui représente une relation dans une dimension.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Relationship>  
   <ID>...</ID>  
   <Visible>...</Visible>  
   <FromRelationshipEnd>...</FromRelationshipEnd>  
   <ToRelationshipEnd>...</ToRelationshipEnd>  
</Relationship>  
```  
  
## <a name="data-type-characteristics"></a>Caractéristiques du type de données  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Types de données de base|None|  
|Types de données dérivés|None|  
  
## <a name="data-type-relationships"></a>Relations du type de données  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|None|  
|Éléments enfants|[ID](../../../analysis-services/scripting/properties/id-element-assl.md), [Visible](../../../analysis-services/scripting/properties/visible-element-assl.md), [dimensionid](../../../analysis-services/scripting/data-type/relationshipend-data-type-assl.md), [ToRelationshipEnd](../../../analysis-services/scripting/data-type/relationshipend-data-type-assl.md)|  
|Éléments dérivés||  
  
## <a name="remarks"></a>Notes   
 L’élément correspondant dans le modèle d’objet objets AMO (Analysis Management) est <xref:Microsoft.AnalysisServices.Relationship>.  
  
## <a name="see-also"></a>Voir aussi  
 [Analysis Services script des Types de données XML Language &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
