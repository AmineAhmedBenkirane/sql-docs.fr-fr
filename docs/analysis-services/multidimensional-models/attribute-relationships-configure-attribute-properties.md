---
title: "Configurer les propriétés de relation d’attribut | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- flexible relationships (Analysis Services)
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
- properties [Analysis Services], attribute relationships
- rigid relationships (Analysis Services)
ms.assetid: fce511af-66d7-42fc-bb3a-6c516f16b10e
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: bcc42c8bcd73c52851f3ed7fae5f4f7a4915b450
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2018
---
# <a name="attribute-relationships---configure-attribute-properties"></a>Relations d’attributs - configurer les propriétés d’attribut
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
Le tableau suivant répertorie et décrit les propriétés d'une relation d'attribut.  
  
|Propriété|Description|  
|--------------|-----------------|  
|Attribut|Contient le nom de l'attribut.|  
|Cardinalité|Indique la cardinalité de la relation. Les valeurs sont Many, pour une relation plusieurs-à-un, ou One, pour une relation un-à-un. La valeur par défaut est Many. Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], la propriété de cardinalité n’a aucun effet ; son utilisation est réservée pour une implémentation future.|  
|Nom|Contient le nom convivial de l'attribut.|  
|RelationshipType|Indique si les relations de membres changent avec le temps. Les valeurs sont Rigid, qui signifie que les relations entre membres ne changent pas avec le temps, ou Flexible, qui signifie que les relations entre membres changent avec le temps. La valeur par défaut est Flexible. Si vous définissez une relation comme flexible, les agrégations sont supprimées et recalculées dans le cadre de la mise à jour incrémentielle (elles ne sont pas supprimées si seuls de nouveaux membres sont ajoutés). Si vous définissez une relation rigide, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] conserve les agrégations une fois la dimension mise à jour de manière incrémentielle. Si une relation rigide change, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] génère une erreur pendant le traitement incrémentiel. En spécifiant les relations et les propriétés de relations appropriées, vous améliorez les performances de requête et de traitement.|  
|Visible|Détermine la visibilité de la relation d'attribut. Les valeurs sont True ou False. La valeur par défaut est True.|  
  
  
