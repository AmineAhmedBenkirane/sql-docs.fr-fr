---
title: "Élément de tuple (XMLA) | Documents Microsoft"
ms.custom: 
ms.date: 03/06/2017
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
apiname:
- Tuple Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- microsoft.xml.analysis.tuple
- urn:schemas-microsoft-com:xml-analysis#Tuple
- http://schemas.microsoft.com/analysisservices/2003/engine#Tuple
helpviewer_keywords:
- Tuple element
ms.assetid: d65aba10-55e1-49c1-81bc-0756c39c0da2
caps.latest.revision: 11
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 11a9d3b633e680154787615c04ee1f08b65b8139
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="tuple-element-xmla"></a>Élément Tuple (XMLA)
  Contient une collection d’éléments [Member](../../../analysis-services/xmla/xml-elements-properties/member-element-xmla.md) figurant dans l’élément [Tuples](../../../analysis-services/xmla/xml-elements-properties/tuples-element-xmla.md) parent.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Tuples>  
   <Tuple>  
      <Member>...</Member>  
   </Tuple>  
   ...  
</Tuples>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Aucune|  
|Valeur par défaut|Aucune|  
|Cardinalité|0-n : élément facultatif pouvant apparaître plusieurs fois.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Tuples](../../../analysis-services/xmla/xml-elements-properties/tuples-element-xmla.md)|  
|Éléments enfants|[Membre](../../../analysis-services/xmla/xml-elements-properties/member-element-xmla.md)|  
  
## <a name="remarks"></a>Notes  
 Quand une application cliente définit la propriété **AxisFormat** avec la valeur *TupleFormat*, un axe est représenté comme un ensemble de tuples. Chaque élément **Axis** contient un élément **Tuples** qui représente l’ensemble de tuples sur l’axe en question. Chaque tuple est représenté à l’aide d’un élément **Tuple** qui contient des éléments **Member** de chaque hiérarchie sur l’axe.  
  
## <a name="example"></a> Exemple  
 L’exemple suivant illustre la structure de l’élément **Tuple** quand un client spécifie *TupleFormat* ou *CustomFormat* pour la propriété XMLA **AxisFormat** d’après les membres suivants de l’axe :  
  
|||||  
|-|-|-|-|  
|Hiérarchie **Time**|1999|1999|2000|  
|Hiérarchie **Category**|Réel|Budget|Budget|  
  
```  
<Axes>  
   <Axis name="Axis0">  
      <Tuples>  
         <Tuple>  
            <Member Hierarchy="Time">  
               <UName>[Time].[1999]</UName>  
               ...  
            </Member>  
            <Member Hierarchy="Category">  
               <UName>[Scenario].[Actual]</UName>  
               ...  
            </Member>  
         </Tuple>  
         <Tuple>  
            <Member Hierarchy="Time">  
               <UName>[Time].[1999]</UName>  
               ...  
            </Member>  
            <Member Hierarchy="Category">  
               <UName>[Scenario].[Budget]</UName>  
               ...  
            </Member>  
         </Tuple>  
         <Tuple>  
            <Member Hierarchy="Time">  
               <UName>[Time].[2000]</UName>  
               ...  
            </Member>  
            <Member Hierarchy="Category">  
               <UName>[Scenario].[Budget]</UName>  
               ...  
            </Member>  
         </Tuple>  
      </Tuples>  
   </Axis>  
   ...  
</Axes>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  

