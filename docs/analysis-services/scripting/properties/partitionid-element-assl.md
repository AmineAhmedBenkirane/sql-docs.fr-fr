---
title: Élément PartitionID (ASSL) | Documents Microsoft
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
- PartitionID Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- PartitionID element
ms.assetid: 95e59c73-5ca4-478e-898d-50ffa4bbe794
caps.latest.revision: 10
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2fe2e445656b3fdeb8c1d3a329956d34c33630ea
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="partitionid-element-assl"></a>Élément PartitionID (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Associe un [Partition](../../../analysis-services/scripting/objects/partition-element-assl.md) élément avec un élément parent, une liaison ou une liaison hors ligne.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<PartitionBinding>  
   ...  
   <PartitionID>...</PartitionID>  
   ...  
</PartitionBinding>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne|  
|Valeur par défaut|Aucune|  
|Cardinalité|1-1 : élément obligatoire qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Élément parent|[PartitionBinding](../../../analysis-services/scripting/data-type/partitionbinding-data-type-assl.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations sur les liaisons et les liaisons hors ligne, consultez [des Sources de données et des liaisons &#40;multidimensionnels SSAS&#41;](../../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
