---
title: Type de données ClrAssembly (ASSL) | Documents Microsoft
ms.custom: ''
ms.date: 03/14/2017
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
- ClrAssembly Data Type
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- ClrAssembly
helpviewer_keywords:
- ClrAssembly data type
ms.assetid: 3f5dc5a1-ebd6-41b8-ac04-91d4de137eb4
caps.latest.revision: 44
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d5529e5782ecfb50479437a1c5d405d7567501bc
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="clrassembly-data-type-assl"></a>Type de données ClrAssembly (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Définit un type de données dérivé qui représente un [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assembly associé à un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) ou [Server](../../../analysis-services/scripting/objects/server-element-assl.md) élément  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<ClrAssembly>  
      <!-- The following elements extend Assembly -->  
   <Files>...</Files>  
      <PermissionSet>...</PermissionSet>  
</ClrAssembly>  
```  
  
## <a name="data-type-characteristics"></a>Caractéristiques du type de données  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Types de données de base|[Assembly](../../../analysis-services/scripting/objects/assembly-element-assl.md)|  
|Types de données dérivés|Aucune|  
  
## <a name="data-type-relationships"></a>Relations du type de données  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|Aucun (type abstrait)|  
|Éléments enfants|[Fichiers](../../../analysis-services/scripting/collections/files-element-assl.md), [PermissionSet](../../../analysis-services/scripting/properties/permissionset-element-assl.md)|  
|Éléments dérivés|Voir [Assembly](../../../analysis-services/scripting/objects/assembly-element-assl.md) (collection[Assemblies](../../../analysis-services/scripting/collections/assemblies-element-assl.md) d'éléments [Database](../../../analysis-services/scripting/objects/database-element-assl.md) ou [Server](../../../analysis-services/scripting/objects/server-element-assl.md))|  
  
## <a name="remarks"></a>Notes  
 Le **ClrAssembly** élément contient les fichiers nécessaires pour recréer un [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assembly, associés à une instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ou avec une base de données spécifique sur une instance de [!INCLUDE[ssAS](../../../includes/ssas-md.md)], ainsi que les autorisations nécessaires pour exécuter l’assembly.  
  
 L’élément correspondant dans le modèle d’objet objets AMO (Analysis Management) est <xref:Microsoft.AnalysisServices.ClrAssembly>.  
  
## <a name="see-also"></a>Voir aussi  
 [Élément File & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/objects/file-element-assl.md)   
 [Type de données ClrAssemblyFile & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md)   
 [Élément de données & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/objects/data-element-assl.md)   
 [Type de données DataBlock & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/data-type/datablock-data-type-assl.md)   
 [Blocs élément & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/collections/blocks-element-assl.md)   
 [Élément de bloc & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/objects/block-element-assl.md)   
 [Type de données ComAssembly & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/data-type/comassembly-data-type-assl.md)   
 [Analysis Services script des Types de données XML Language & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
