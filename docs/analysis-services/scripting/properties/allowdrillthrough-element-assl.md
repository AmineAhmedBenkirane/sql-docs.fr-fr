---
title: "Élément AllowDrillThrough (ASSL) | Documents Microsoft"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: scripting
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname: AllowDrillThrough Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: AllowDrillThrough
helpviewer_keywords: AllowDrillThrough element
ms.assetid: 53c9e4a3-a376-447d-a13f-80d845cc9789
caps.latest.revision: "51"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 273c96e4406af12582dd3a8a459573539a357736
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="allowdrillthrough-element-assl"></a>Élément AllowDrillThrough (ASSL)
  Détermine si l'extraction est autorisée sur l'élément parent.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<MiningModel> <!-- or MiningModelPermission -->  
<!-- or MiningStructurePermission -->   ...  
   <AllowDrillThrough>...</AllowDrillThrough>  
   ...  
</MiningModel>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Booléen|  
|Valeur par défaut|**False**|  
|Cardinalité|0-1 : Élément facultatif qui peut se produire une seule fois seulement.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Élément MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md), [MiningModelPermission](../../../analysis-services/scripting/objects/miningmodelpermission-element-assl.md), [MiningStructurePermission](../../../analysis-services/scripting/objects/miningstructurepermission-element-assl.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 Les éléments qui correspondent aux parents de **AllowDrillThrough** dans le modèle d’objet objets AMO (Analysis Management) sont <xref:Microsoft.AnalysisServices.MiningModel>, <xref:Microsoft.AnalysisServices.MiningModelPermission>, et <xref:Microsoft.AnalysisServices.MiningStructurePermission>.  
  
## <a name="drillthrough-on-mining-structures"></a>Extraction sur des structures d'exploration de données  
 Dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], vous pouvez définir **AllowDrillthrough** autorisations pour les structures d’exploration de données, ainsi que les modèles d’exploration de données. Lorsque vous assignez cette autorisation à un rôle, tout membre de ce rôle peut interroger le modèle d'exploration de données et retourner les colonnes de la structure qui n'étaient pas incluses dans le modèle. Par exemple, vous créez un modèle qui utilise uniquement les colonnes : clé du client, revenus du client et achats du client. Si vous activez l'extraction sur le modèle, les utilisateurs peuvent retourner des informations dans d'autres colonnes de la structure d'exploration de données, telles que les adresses de messagerie ou les noms des clients.  
  
 Par conséquent, pour protéger les données sensibles, soyez prudent lorsque vous ajoutez des colonnes à la structure d'exploration de données. Également, accordez l'autorisation **AllowDrillthrough** sur une structure seulement lorsqu'elle est requise.  
  
 Pour procéder à l'extraction des colonnes de la structure, utilisez une requête avec l'une des syntaxes suivantes :  
  
 `SELECT * FROM <structure>.CASES`  
  
 ou  
  
 `SELECT StructureColumn('<structure-column-name>') FROM <model>.CASES`  
  
## <a name="see-also"></a>Voir aussi  
 [Élément role &#40; ASSL &#41;](../../../analysis-services/scripting/objects/role-element-assl.md)   
 [Propriétés &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
