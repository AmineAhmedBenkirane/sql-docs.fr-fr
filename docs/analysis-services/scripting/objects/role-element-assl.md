---
title: "Élément role (ASSL) | Documents Microsoft"
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
apiname: Role Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: ROLE
helpviewer_keywords: Role element
ms.assetid: 56f52462-a7fd-4b51-a7fb-4311134439e9
caps.latest.revision: "34"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: b239ef6cadeff39bbb26c84950c48a9667d9238d
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="role-element-assl"></a>Élément Role (ASSL)
  Contient des informations à propos d'un rôle de sécurité.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Roles>  
      <Role>  
      <Name>...</Name>  
      <ID>...</ID>  
      <CreatedTimestamp>...</CreateTimestamp>  
      <LastSchemaUpdate>...</LastSchemaUpdate>  
      <Description>...</Description>  
      <Members>...</Members>  
      <Annotations>...</Annotations>  
   </Role>  
</Roles>  
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
|Éléments parents|[Roles](../../../analysis-services/scripting/collections/roles-element-assl.md)|  
|Éléments enfants|[Annotations](../../../analysis-services/scripting/collections/annotations-element-assl.md), [CreatedTimestamp](../../../analysis-services/scripting/properties/createdtimestamp-element-assl.md), [Description](../../../analysis-services/scripting/properties/description-element-assl.md), [ID](../../../analysis-services/scripting/properties/id-element-assl.md), [LastSchemaUpdate](../../../analysis-services/scripting/properties/lastschemaupdate-element-assl.md), [membres](../../../analysis-services/scripting/collections/members-element-assl.md), [nom](../../../analysis-services/scripting/properties/name-element-assl.md)|  
  
## <a name="remarks"></a>Notes  
 La définition du rôle contient les utilisateurs qui sont membres de ce rôle.  
  
 L’élément correspondant dans le modèle d’objet objets AMO (Analysis Management) est <xref:Microsoft.AnalysisServices.Role>.  
  
## <a name="see-also"></a>Voir aussi  
 [Élément de la base de données &#40; ASSL &#41;](../../../analysis-services/scripting/objects/database-element-assl.md)   
 [Server, élément &#40; ASSL &#41;](../../../analysis-services/scripting/objects/server-element-assl.md)   
 [Objets &#40; ASSL &#41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  
