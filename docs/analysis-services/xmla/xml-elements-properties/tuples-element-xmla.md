---
title: Élément tuples (XMLA) | Documents Microsoft
ms.custom: ''
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- Tuples Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#Tuples
- microsoft.xml.analysis.tuples
- urn:schemas-microsoft-com:xml-analysis#Tuples
helpviewer_keywords:
- Tuples element
ms.assetid: 5494bbaa-c1aa-43fa-b3e0-83befb2bccdd
caps.latest.revision: 11
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 4eed093e987af9cb58497caa317f796aa4fcf8a6
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="tuples-element-xmla"></a>Élément Tuples (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Contient un ensemble de [Tuple](../../../analysis-services/xmla/xml-elements-properties/tuple-element-xmla.md) des objets pour un [axe](../../../analysis-services/xmla/xml-elements-properties/axis-element-xmla.md) élément qui utilise le [MDDataSet](../../../analysis-services/xmla/xml-data-types/mddataset-data-type-xmla.md) type de données retourné par la [Execute](../../../analysis-services/xmla/xml-elements-methods-execute.md) (méthode).  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Axis>  
   ...  
   <Tuples>  
      <Tuple>...</Tuple>  
   </Tuples>  
   ...  
</Axis>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Aucune|  
|Valeur par défaut|Aucune|  
|Cardinalité|0-1: élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Axe](../../../analysis-services/xmla/xml-elements-properties/axis-element-xmla.md)|  
|Éléments enfants|[Tuple](../../../analysis-services/xmla/xml-elements-properties/tuple-element-xmla.md)|  
  
## <a name="remarks"></a>Notes  
 Quand une application cliente définit la propriété **AxisFormat** avec la valeur *TupleFormat*, un axe est représenté comme un ensemble de tuples. Chaque élément **Axis** contient un élément **Tuples** qui représente l’ensemble de tuples sur l’axe en question. Chaque tuple est représenté à l’aide d’un élément **Tuple** qui contient des éléments [Member](../../../analysis-services/xmla/xml-elements-properties/member-element-xmla.md) de chaque hiérarchie sur l’axe.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant illustre la structure de la **Tuples** élément lorsqu’un client spécifie *TupleFormat* ou *CustomFormat* pour le **AxisFormat** XML for Analysis (XMLA) propriété les membres suivants de l’axe :  
  
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
 [Propriétés & #40 ; XMLA & #41 ;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
