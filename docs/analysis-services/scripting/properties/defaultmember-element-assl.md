---
title: "Élément DefaultMember (ASSL) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- DefaultMember Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- DefaultMember
helpviewer_keywords:
- DefaultMember element
ms.assetid: db4eea9f-f7cf-40de-abd0-b62014e7ec2d
caps.latest.revision: 38
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 411fbf97001ee719e144edfdd6de685e984da021
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="defaultmember-element-assl"></a>Élément DefaultMember (ASSL)
  Contient une expression MDX (Multidimensional Expressions) qui identifie le membre par défaut de l'élément parent.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<AttributePermission> <!-- or DimensionAttribute, ManyToManyMeasureGroupDimension, PerspectiveAttribute -->  
      ...  
   <DefaultMember>...</DefaultMember>  
      ...  
</AttributePermission>  
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
|Élément parent|[AttributePermission](../../../analysis-services/scripting/objects/attributepermission-element-assl.md), [DimensionAttribute](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md), [ManyToManyMeasureGroupDimension](../../../analysis-services/scripting/data-type/manytomanymeasuregroupdimension-data-type-assl.md), [PerspectiveAttribute](../../../analysis-services/scripting/data-type/perspectiveattribute-data-type-assl.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 L'élément **DefaultMember** définit le membre par défaut de l'élément parent. Si **DefaultMember** n’est pas spécifié ou est défini sur une chaîne vide, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] choisit un membre à utiliser en tant que le membre par défaut.  
  
 Pour les éléments **ManyToManyMeasureGroupDimension** , l'élément **DefaultMember** contient une expression MDX qui spécifie un membre dans la dimension identifiée dans l'élément **CubeDimensionID** de **ManyToManyMeasureGroupDimension**. L’expression MDX est semblable à la [StrToMember](../../../mdx/strtomember-mdx.md) fonction MDX avec le mot clé CONSTRAINED, dans la mesure où il ne peut pas inclure de fonctions MDX ou définies par l’utilisateur.  
  
 Pour plus d’informations sur les membres par défaut, consultez [Définir un membre par défaut](../../../analysis-services/multidimensional-models/attribute-properties-define-a-default-member.md).  
  
 Les éléments qui correspondent aux parents de **DefaultMember** dans le modèle d’objet objets AMO (Analysis Management) sont <xref:Microsoft.AnalysisServices.AttributePermission>, <xref:Microsoft.AnalysisServices.DimensionAttribute>, et <xref:Microsoft.AnalysisServices.PerspectiveAttribute>.  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
