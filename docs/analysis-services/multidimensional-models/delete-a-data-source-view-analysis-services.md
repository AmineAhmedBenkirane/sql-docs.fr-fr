---
title: "Supprimer une vue de Source de données (Analysis Services) | Documents Microsoft"
ms.custom: 
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting data source views
- data source views [Analysis Services], deleting
- removing data source views
ms.assetid: ae3f5ca0-ecbf-4b52-8386-eb457719d854
caps.latest.revision: "37"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 93a7e6243839f508dc078b299b8f4b587672b92e
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2017
---
# <a name="delete-a-data-source-view-analysis-services"></a>Supprimer une vue de source de données (Analysis Services)
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Si vous n’utilisez plus une vue de source de données (DSV) dans un projet OLAP, vous pouvez le supprimer à partir du projet dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].  
  
 La suppression d'une vue DSV est définitive. Vous ne pouvez pas restaurer une vue DSV supprimée dans un projet ou une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .  
  
 Les vues de source de données (DSV) dont dépendent d’autres objets ne peuvent pas être supprimées d’une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ouverte par [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] en mode en ligne. Pour supprimer une vue DSV d'un projet qui est connecté à une base de données s'exécutant sur un serveur, vous devez d'abord supprimer tous les objets de la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui dépendent de cette vue DSV avant de supprimer la vue DSV elle-même.  
  
 La suppression d'une vue DSV invalidera d'autres objets [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui dépendent d'elle ; par conséquent, avant de supprimer la vue DSV, vous verrez la liste des objets qui deviendront non valides une fois la vue DSV supprimée. Examinez cette liste avec soin pour vous assurer qu'elle n'inclut pas les objets que vous vous attendez toujours à utiliser.  
  
 ![Supprimer la boîte de dialogue objets](../../analysis-services/multidimensional-models/media/ssas-olapdsv-deleteobjects.gif "boîte de dialogue Supprimer les objets")  
  
## <a name="see-also"></a>Voir aussi  
 [Vues de sources de données dans les modèles multidimensionnels](../../analysis-services/multidimensional-models/data-source-views-in-multidimensional-models.md)   
 [Modifier les propriétés d’une vue de source de données &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/change-properties-in-a-data-source-view-analysis-services.md)  
  
  
