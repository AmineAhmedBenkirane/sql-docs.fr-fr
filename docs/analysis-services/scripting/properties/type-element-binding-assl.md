---
title: Type d’élément (Binding) (ASSL) | Documents Microsoft
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
- Type Element (Binding)
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- TYPE
helpviewer_keywords:
- Type element
ms.assetid: b5f5c485-dc83-4d66-a8d2-e96e96d068f9
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: c37eaed200b5f9be4d7ef39599bd2a02ce7b2e58
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="type-element-binding-assl"></a>Élément Type (Binding) (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Contient le type de la liaison de l’attribut.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<AttributeBinding> <!-- or CubeAttributeBinding -->  
   ...  
   <Type>...</Type>  
   ...  
</AttributeBinding>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne (énumération)|  
|Valeur par défaut|None|  
|Cardinalité|1-1 : élément requis qui apparaît une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[AttributeBinding](../../../analysis-services/scripting/data-type/attributebinding-data-type-assl.md), [CubeAttributeBinding](../../../analysis-services/scripting/data-type/cubeattributebinding-data-type-assl.md)|  
|Éléments enfants|None|  
  
## <a name="remarks"></a>Notes   
 La valeur de cet élément est limitée à l'une des chaînes répertoriées dans le tableau suivant.  
  
|Valeur|Description|  
|-----------|-----------------|  
|*Tous*|Tous les niveaux|  
|*Clé*|Clés de membre|  
|*Nom*|Nom de membre|  
|*Value*|Valeur de membre|  
|*Traduction*|Traductions de membre|  
|*UnaryOperator*|Opérateurs unaires|  
|*SkippedLevels*|Niveaux ignorés|  
|*CustomRollup*|Formules de cumul personnalisées|  
|*CustomRollupProperties*|Propriétés de cumul personnalisées|  
  
 Les éléments qui correspondent aux parents de **Type** dans le modèle d’objet objets AMO (Analysis Management) sont <xref:Microsoft.AnalysisServices.AttributeBinding> et <xref:Microsoft.AnalysisServices.CubeAttributeBinding>.  
  
## <a name="see-also"></a>Voir aussi  
 [Type de liaison de données &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/binding-data-type-assl.md)   
 [Propriétés &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
