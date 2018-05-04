---
title: Élément Edition (ASSL) | Documents Microsoft
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
- Edition Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- Edition
helpviewer_keywords:
- Edition element
ms.assetid: 521e1286-097e-494f-b036-61047096e87e
caps.latest.revision: 38
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: f55b9ae5a8d98512f8d34f47cbe3a08647e24ebc
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="edition-element-assl"></a>Élément Edition (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Contient la version en lecture seule de l’instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] représenté par le [Server](../../../analysis-services/scripting/objects/server-element-assl.md) élément.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Server>  
      ...  
      <Edition>...</Edition>  
   ...  
</Server>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne (énumération)|  
|Valeur par défaut|Aucune|  
|Cardinalité|0-1: élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Server](../../../analysis-services/scripting/objects/server-element-assl.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 Le **édition** élément décrit quelle édition de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] est installé. La valeur de cet élément est limitée à l'une des chaînes du tableau suivant.  
  
|Valeur| Description|  
|-----------|-----------------|  
|*Standard*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Standard edition pour processeurs 32 bits.|  
|*Enterprise*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Enterprise edition pour processeurs 32 bits.|  
|*EnterpriseCore*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Enterprise edition : gestion des licences par cœur pour les processeurs 32 bits.|  
|*Business Intelligence*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Édition business Intelligence pour les processeurs 32 bits.|  
|*Développeur*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Developer edition pour processeurs 32 bits|  
|*Évaluation*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Evaluation edition pour processeurs 64 bits.|  
|*Local*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Local edition pour processeurs 32 bits.|  
|*Standard 64*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Standard edition pour processeurs 64 bits.|  
|*Enterprise 64*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Enterprise edition pour processeurs 64 bits.|  
|*Enterprisecore 64*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Enterprise edition : gestion des licences par cœur pour processeurs 64 bits.|  
|*Business Intelligence 64*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Édition business Intelligence pour processeurs 64 bits.|  
|*Developer 64*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Developer edition pour processeurs 64 bits|  
|*Évaluation 64*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Evaluation edition pour processeurs 64 bits.|  
|*Local64*|[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Local edition pour processeurs 64 bits.|  
  
 L’énumération qui correspond aux valeurs autorisées pour **ServerEdition** dans l’objet d’objets AMO (Analysis Management) est modèle <xref:Microsoft.AnalysisServices.ServerEdition>.  
  
## <a name="see-also"></a>Voir aussi  
 [Élément version & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/properties/version-element-assl.md)   
 [Propriétés & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
