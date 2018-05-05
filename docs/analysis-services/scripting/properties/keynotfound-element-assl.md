---
title: Élément KeyNotFound (ASSL) | Documents Microsoft
ms.custom: ''
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- KeyNotFound Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- KeyNotFound
helpviewer_keywords:
- KeyNotFound element
ms.assetid: 2a93bbfa-2409-4e94-8b68-926532895a4c
caps.latest.revision: 35
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 65d337bce196f7af2fe740683b8da3d7ab9d5b54
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="keynotfound-element-assl"></a>Élément KeyNotFound (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Spécifie comment [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] répond quand il rencontre une erreur d’intégrité référentielle.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<ErrorConfiguration>  
   ...  
      <KeyNotFound>...</KeyNotFound>  
   ...  
</ErrorConfiguration>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne (énumération)|  
|Valeur par défaut|*ReportAndContinue*|  
|Cardinalité|0-1: élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Élément parent|[ErrorConfiguration](../../../analysis-services/scripting/objects/errorconfiguration-element-assl.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 Les erreurs d'intégrité référentielle se produisent lorsqu'une valeur de clé étrangère dans une table dépendante n'a pas d'entrée correspondante dans la table parente. Cette erreur se produit lorsque [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] traite une dimension dans laquelle la table de faits contient une référence à une valeur de clé étrangère qui n'existe pas dans la table de dimension pour cette dimension, ou lorsque [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] traite une partition si la table principale de dimension pour une dimension qui est incluse dans la partition fait référence à une valeur de clé qui n'existe pas dans une autre table de dimension associée. (Dans le cas de dimensions avec des hiérarchies parent-enfant et des attributs parents, ceci peut aussi se produire lorsque la table principale de dimension pour une dimension qui est incluse dans la partition fait référence à une valeur de clé qui n'existe pas dans la même table de dimension.)  
  
 La valeur de cet élément est limitée à l'une des chaînes du tableau suivant.  
  
|Valeur|Description|  
|-----------|-----------------|  
|*IgnoreError*|Le traitement doit ignorer l'erreur et se poursuivre.|  
|*ReportAndContinue*|Le traitement doit signaler l'erreur et se poursuivre.|  
|*ReportAndStop*|Le traitement doit signaler l'erreur et s'arrêter.|  
  
 L’énumération qui correspond aux valeurs autorisées pour **KeyNotFound** dans l’objet d’objets AMO (Analysis Management) est modèle <xref:Microsoft.AnalysisServices.ErrorOption>.  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
