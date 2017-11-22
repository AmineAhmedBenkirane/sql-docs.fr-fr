---
title: "Élément ReadDefinition (ASSL) | Documents Microsoft"
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
apiname: ReadDefinition Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: ReadDefinition
helpviewer_keywords: ReadDefinition element
ms.assetid: 1f250129-13b2-41b9-b083-b5aacddf0060
caps.latest.revision: "37"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 7596e2bbd2c560f9e3c47f7be3f60ab133ff5714
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="readdefinition-element-assl"></a>Élément ReadDefinition (ASSL)
  Détermine si les membres peuvent lire la définition de la base de données ou la définition des objets de la base de données.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Permission> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <ReadDefinition>...</ReadDefinition>  
   ...  
</Permission>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne (énumération)|  
|Valeur par défaut|*Aucun*|  
|Cardinalité|0-1: élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[CubePermission](../../../analysis-services/scripting/objects/cubepermission-element-assl.md), [DatabasePermission](../../../analysis-services/scripting/objects/databasepermission-element-assl.md), [DimensionPermission](../../../analysis-services/scripting/objects/dimensionpermission-element-assl.md), [MiningModelPermission](../../../analysis-services/scripting/objects/miningmodelpermission-element-assl.md), [MiningStructurePermission](../../../analysis-services/scripting/objects/miningstructurepermission-element-assl.md), [autorisation](../../../analysis-services/scripting/data-type/permission-data-type-assl.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 La valeur de cet élément est limitée à l'une des chaînes répertoriées dans le tableau suivant.  
  
|Valeur|Description|  
|-----------|-----------------|  
|*Aucun*|L'accès à la définition des objets n'est pas autorisé.|  
|*Base*|Un accès de base à la définition des objets est autorisé.<br /><br /> Remarque : Cette autorisation est requise pour créer des cubes locaux, lier les groupes de mesures et lier des dimensions.|  
|*Autorisé*|Un accès complet à la définition des objets est autorisé.<br /><br /> Remarque : Cette autorisation est requise pour exécuter un [Discover](../../../analysis-services/xmla/xml-elements-methods-discover.md) XML pour l’appel Analysis (XMLA) avec le paramètre DISCOVER_XML_METADATA.|  
  
 Les éléments qui correspondent aux parents de **ReadDefinition** dans le modèle d’objet objets AMO (Analysis Management) sont <xref:Microsoft.AnalysisServices.CubePermission>, <xref:Microsoft.AnalysisServices.DatabasePermission>, <xref:Microsoft.AnalysisServices.DimensionPermission>, <xref:Microsoft.AnalysisServices.MiningModelPermission>, <xref:Microsoft.AnalysisServices.MiningStructurePermission>, et <xref:Microsoft.AnalysisServices.Permission>.  
  
## <a name="see-also"></a>Voir aussi  
 [Élément role &#40; ASSL &#41;](../../../analysis-services/scripting/objects/role-element-assl.md)   
 [Propriétés &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
