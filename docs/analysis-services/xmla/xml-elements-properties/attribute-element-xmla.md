---
title: "Attribut d’élément (XMLA) | Documents Microsoft"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Attribute Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#Attribute
- microsoft.xml.analysis.attribute
- urn:schemas-microsoft-com:xml-analysis#Attribute
helpviewer_keywords:
- Attribute element
ms.assetid: 0df9cf44-dc5f-4234-8a5a-daac8aabc0d6
caps.latest.revision: 17
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 2ac9985902b6e91fd2f69b2cc7b7ea3eec6cc79e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="attribute-element-xmla"></a>Élément Attribute (XMLA)
  Définit ou filtre un membre dans un attribut sur lequel un parent [insérer](../../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md), [mise à jour](../../../analysis-services/xmla/xml-elements-commands/update-element-xmla.md), ou [supprimer](../../../analysis-services/xmla/xml-elements-commands/drop-element-xmla.md) commande effectue.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Attributes>  
   ...  
   <Attribute>  
      <AttributeName>...</AttributeName>  
      <Keys>...</Keys>  
      <!-- The following elements are included only for attributes contained in the Attributes element of a parent Insert or Update command -->  
      <Name>...</Name>  
      <Translations>...</Translations>  
      <CustomRollup>...</CustomRollup>  
      <CustomRollupProperties>...</CustomRollupProperties>  
      <UnaryOperator>...</UnaryOperator>  
      <SkippedLevels>...</SkippedLevels>  
   </Attribute>  
   ...  
</Attributes>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Aucune|  
|Valeur par défaut|Aucune|  
|Cardinalité|1-1 : élément requis qui apparaît une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Attributs](../../../analysis-services/xmla/xml-elements-properties/attributes-element-xmla.md)|  
|Éléments enfants|Consultez le tableau ci-dessous.|  
  
|Ancêtre ou parent|Élément enfant|  
|------------------------|-------------------|  
|[DROP](../../../analysis-services/xmla/xml-elements-commands/drop-element-xmla.md), [où](../../../analysis-services/xmla/xml-elements-properties/where-element-xmla.md)|[AttributeName](../../../analysis-services/xmla/xml-elements-properties/attributename-element-xmla.md), [clés](../../../analysis-services/xmla/xml-elements-properties/keys-element-xmla.md)|  
|[Insérer](../../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md), [mise à jour](../../../analysis-services/xmla/xml-elements-commands/update-element-xmla.md)|[AttributeName](../../../analysis-services/xmla/xml-elements-properties/attributename-element-xmla.md), [CustomRollup](../../../analysis-services/xmla/xml-elements-properties/customrollup-element-xmla.md), [CustomRollupProperties](../../../analysis-services/xmla/xml-elements-properties/customrollupproperties-element-xmla.md), [clés](../../../analysis-services/xmla/xml-elements-properties/keys-element-xmla.md), [nom](../../../analysis-services/xmla/xml-elements-properties/name-element-xmla.md), [SkippedLevels](../../../analysis-services/xmla/xml-elements-properties/skippedlevels-element-xmla.md), [traductions](../../../analysis-services/xmla/xml-elements-properties/translations-element-xmla.md), [UnaryOperator](../../../analysis-services/xmla/xml-elements-properties/unaryoperator-element-xmla.md)|  
  
## <a name="remarks"></a>Notes  
 L'élément **Attribute** définit le membre d'attribut qui est inséré, mis à jour ou supprimé par la commande **Insert**, **Update**ou **Drop** , respectivement. Comme ces commandes ne peuvent fonctionner que sur les membres d’un attribut à la fois, le [attributs](../../../analysis-services/xmla/xml-elements-properties/attributes-element-xmla.md) collection de la **insérer**, **mise à jour**, et **supprimer** commandes peuvent contenir un seul **attribut** élément. Toutefois, la collection **Attributes** de l'élément **Where** pour les commandes **Drop** et **Update** peut contenir plusieurs éléments **Attribute** , afin que vous puissiez filtrer les attributs à supprimer ou mettre à jour dans une dimension accessible en écriture.  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)   
 [Dimensions activées en écriture](../../../analysis-services/multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md)  
  
  
