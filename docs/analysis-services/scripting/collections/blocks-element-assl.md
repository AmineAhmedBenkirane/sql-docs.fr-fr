---
title: Bloque l’élément (ASSL) | Documents Microsoft
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
- Blocks Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- Blocks
helpviewer_keywords:
- Blocks element
ms.assetid: d6fd4e6b-b5bd-43cd-9c28-48af57cf977c
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ae3ab1e76831f59dccc5c89c30553596977fe067
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="blocks-element-assl"></a>Élément Blocks (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Contient la collection de blocs de données binaires qui représentent le contenu binaire d’un [ClrAssemblyFile](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md) élément.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Data xsi:type="DataBlock">  
   ...  
   <Blocks>  
      <Block>...</Block>  
   </Blocks>  
   ...  
</File>  
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
|Éléments parents|[Données](../../../analysis-services/scripting/objects/data-element-assl.md) de type [DataBlock](../../../analysis-services/scripting/data-type/datablock-data-type-assl.md)|  
|Éléments enfants|[Bloc](../../../analysis-services/scripting/objects/block-element-assl.md)|  
  
## <a name="remarks"></a>Notes  
 L’élément qui correspond au parent de **blocs** dans l’objet d’objets AMO (Analysis Management) est modèle <xref:Microsoft.AnalysisServices.ClrAssemblyFile>.  
  
## <a name="see-also"></a>Voir aussi  
 [Assembly, élément & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/objects/assembly-element-assl.md)   
 [Type de données ClrAssembly &#40;ASSL&#41;](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md)   
 [Fichiers d’élément &#40;ASSL&#41;](../../../analysis-services/scripting/collections/files-element-assl.md)   
 [Élément File & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/objects/file-element-assl.md)   
 [Type de données ClrAssemblyFile & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md)   
 [Élément de données & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/objects/data-element-assl.md)   
 [Type de données DataBlock & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/data-type/datablock-data-type-assl.md)   
 [Élément Blocks](../../../analysis-services/scripting/collections/blocks-element-assl.md)   
 [Élément de bloc & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/objects/block-element-assl.md)   
 [Collections de & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/collections/collections-assl.md)  
  
  
