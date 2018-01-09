---
title: Gestion de Caches (XMLA) | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
helpviewer_keywords:
- XMLA, cache
- XML for Analysis, cache
- clearing cache
- cache [Analysis Services]
ms.assetid: afad5c39-d4c3-4307-b3b9-a06617da0028
caps.latest.revision: "13"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: a8dfd107f6d71f913a2a4737d554b05ed4c61b47
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="managing-caches-xmla"></a>Gestion des caches (XMLA)
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Vous pouvez utiliser la [ClearCache](../../analysis-services/xmla/xml-elements-commands/clearcache-element-xmla.md) commande XML for Analysis (XMLA) pour effacer le cache de dimension spécifiée ou la partition. Effacement du cache contraint [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour régénérer le cache pour cet objet.  
  
## <a name="specifying-objects"></a>Spécification d'objets  
 Le [objet](../../analysis-services/xmla/xml-elements-properties/object-element-xmla.md) propriété de la **ClearCache** commande peut contenir une référence d’objet que pour un des objets suivants. Si une référence d'objet désigne un objet différent de ceux mentionnés ci-dessous, une erreur se produit :  
  
 Base de données  
 Efface le cache pour l'ensemble des dimensions et des partitions contenues dans la base de données.  
  
 Dimension  
 Efface le cache pour la dimension spécifiée.  
  
 Cube  
 Efface le cache pour l'ensemble des partitions contenues dans les groupes de mesures du cube.  
  
 Groupe de mesures  
 Efface le cache pour l'ensemble des partitions contenues dans le groupe de mesures.  
  
 Partition  
 Efface le cache pour la partition spécifiée.  
  
## <a name="see-also"></a>Voir aussi  
 [Développement avec XMLA dans Analysis Services](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/developing-with-xmla-in-analysis-services.md)  
  
  
