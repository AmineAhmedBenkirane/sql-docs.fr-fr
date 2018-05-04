---
title: Bloquer l’élément (ASSL) | Documents Microsoft
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
- Block Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- Block
helpviewer_keywords:
- Block element
ms.assetid: f45c32ae-e4e0-465a-9564-9ccfb10a858f
caps.latest.revision: 37
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ec3d8d8616d6561e3b7d7e898e6c05d77839e34d
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="block-element-assl"></a>Élément Block (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Contient l’ensemble ou une partie du contenu binaire d’un [ClrAssemblyFile](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md) élément.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Blocks>  
   <Block>...</Block>  
</Blocks>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Base64Binary|  
|Valeur par défaut|Aucune|  
|Cardinalité|1-n : élément requis pouvant apparaître plusieurs fois.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Blocs](../../../analysis-services/scripting/collections/blocks-element-assl.md)|  
|Éléments enfants|Aucune|  
  
## <a name="see-also"></a>Voir aussi  
 [Assembly, élément & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/objects/assembly-element-assl.md)   
 [Type de données ClrAssembly &#40;ASSL&#41;](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md)   
 [Fichiers d’élément &#40;ASSL&#41;](../../../analysis-services/scripting/collections/files-element-assl.md)   
 [Élément File & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/objects/file-element-assl.md)   
 [Type de données ClrAssemblyFile & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md)   
 [Élément de données & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/objects/data-element-assl.md)   
 [Type de données DataBlock & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/data-type/datablock-data-type-assl.md)   
 [Objets & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  
