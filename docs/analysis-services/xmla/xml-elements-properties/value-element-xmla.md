---
title: "Valeur d’élément (XMLA) | Documents Microsoft"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: xmla
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname: Value Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords:
- microsoft.xml.analysis.value
- urn:schemas-microsoft-com:xml-analysis#Value
- http://schemas.microsoft.com/analysisservices/2003/engine#Value
helpviewer_keywords: Value element
ms.assetid: f87ca7f8-d9fe-4730-a706-5d50fcfe21df
caps.latest.revision: "14"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: d0e3954de89983d545df118398398128568eff3f
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="value-element-xmla"></a>Élément Value (XMLA)
  Contient la valeur souhaitée d’un [attribut](../../../analysis-services/xmla/xml-elements-properties/attribute-element-xmla.md) élément à ajouter à un [insérer](../../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md) commande, ou un [cellule](../../../analysis-services/xmla/xml-elements-properties/cell-element-xmla.md) élément être mis à jour par une [UpdateCells](../../../analysis-services/xmla/xml-elements-commands/updatecells-element-xmla.md) commande.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Attribute> <!-- or Cell --!>  
   ...  
   <Value>...</Value>  
   ...  
</Attribute>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Tout|  
|Valeur par défaut|Aucune|  
|Cardinalité|1-1 : élément requis qui apparaît une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Attribut](../../../analysis-services/xmla/xml-elements-properties/attribute-element-xmla.md), [cellule](../../../analysis-services/xmla/xml-elements-properties/cell-element-xmla.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 Pour **attribut** éléments, le **valeur** élément contient la valeur souhaitée que doit posséder le membre après le **insérer** commande est validée. Pour plus d’informations sur l’insertion de membres, consultez [insertion, mise à jour et suppression de membres &#40; XMLA &#41; ](../../../analysis-services/multidimensional-models-scripting-language-assl-xmla/inserting-updating-and-dropping-members-xmla.md).  
  
 Pour **cellule** éléments, le **valeur** élément contient la valeur souhaitée que doit posséder la cellule après le **UpdateCells** commande est validée. La valeur réelle stockée dans la table d'écriture différée pour cette cellule correspond à la différence entre la valeur d'origine de la cellule et la valeur souhaitée de cette dernière.  
  
 Le type de données utilisé par cet élément doit correspondre au type de données de la cellule à mettre à jour.  
  
 Pour plus d’informations sur la mise à jour des cellules, consultez [Mise à jour de cellules &#40;XMLA&#41;](../../../analysis-services/multidimensional-models-scripting-language-assl-xmla/updating-cells-xmla.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Élément CellOrdinal &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/cellordinal-element-xmla.md)   
 [Insérer un élément &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md)   
 [Élément UpdateCells &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/updatecells-element-xmla.md)   
 [Propriétés &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
