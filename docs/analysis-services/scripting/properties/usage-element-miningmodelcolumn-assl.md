---
title: "Élément usage (MiningModelColumn) (ASSL) | Documents Microsoft"
ms.custom: 
ms.date: 03/17/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: Usage Element (MiningModelColumn)
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: Usage
helpviewer_keywords: Usage element
ms.assetid: 435a857e-37a9-434e-9de1-354f1ff2993f
caps.latest.revision: "34"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: a0e49b1156817f720b0c7db3205a8d1697ae6b8f
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="usage-element-miningmodelcolumn-assl"></a>Élément Usage (MiningModelColumn) (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Décrit comment la colonne associée dans le parent [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) est utilisé.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<MiningModelColumn>  
   ...  
   <Usage>...</Usage>  
   ...  
</MiningModelColumn>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne (énumération)|  
|Valeur par défaut|None|  
|Cardinalité|0-1 : élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Élément parent|[MiningModelColumn](../../../analysis-services/scripting/data-type/miningmodelcolumn-data-type-assl.md)|  
|Éléments enfants|None|  
  
## <a name="remarks"></a>Notes   
 La valeur de cet élément est limitée à l'une des chaînes répertoriées dans le tableau suivant.  
  
|Valeur|Description|  
|-----------|-----------------|  
|*Clé*|La colonne est une colonne clé.|  
|*Entrée*|La colonne est une colonne d'entrée.|  
|*Predict*|La colonne est une colonne de prévision.|  
|*PredictOnly*|La colonne est uniquement une colonne de prévision.|  
|*Aucun*|La colonne n'est pas utilisée par le modèle.<br /><br /> **\*\*Avertissement \* \***  lorsque la valeur de l’utilisation est « None », Analysis Services n’envoie pas n’importe quelle valeur au serveur par défaut ; par conséquent, l’attribut d’utilisation n’est pas inclus dans la demande/réponse.|  
  
 L’énumération qui correspond aux valeurs autorisées pour **utilisation** dans l’objet d’objets AMO (Analysis Management) est modèle <xref:Microsoft.AnalysisServices.MiningModelColumnUsages>.  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
