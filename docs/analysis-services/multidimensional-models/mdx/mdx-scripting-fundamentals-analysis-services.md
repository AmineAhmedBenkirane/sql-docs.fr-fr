---
title: Notions de base (Analysis Services) des scripts MDX | Documents Microsoft
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
- cubes [Analysis Services], scripts
- calculations [Analysis Services], scripts
- MDX [Analysis Services], scripts
- scripts [MDX]
- cubes [Analysis Services], calculations
- Multidimensional Expressions [Analysis Services], scripts
ms.assetid: fdecb3ce-7c87-4bab-8000-532ba7a29f96
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: bba357ff7e84870c9b734591b80712c25de2b750
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2018
---
# <a name="mdx-scripting-fundamentals-analysis-services"></a>Principes de base des scripts MDX (Analysis Services)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
Dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], un script MDX (Multidimensional Expressions) est constitué d’une ou plusieurs expressions ou instructions MDX qui remplissent un cube avec des calculs.  
  
 Un script MDX définit le processus de calcul pour un cube. Il est également considéré comme un élément du cube proprement dit. Par conséquent, la modification d'un script MDX associé à un cube entraîne immédiatement la modification de son processus de calcul.  
  
 Pour créer des scripts MDX, vous pouvez utiliser le Concepteur de cube disponible dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]. Pour plus d’informations, consultez [Définir des attributions et d’autres commandes de script](../../../analysis-services/multidimensional-models/define-assignments-and-other-script-commands.md) et [Introduction aux scripts MDX dans Microsoft SQL Server 2005](http://go.microsoft.com/fwlink/?LinkId=81892).  
  
 Pour résoudre les problèmes de performance liés aux calculs et aux requêtes MDX, consultez la section relative à l’optimisation de MDX du [Guide des performances de SQL Server Analysis Services](http://go.microsoft.com/fwlink/p/?LinkId=399050).  
  
## <a name="in-this-section"></a>Dans cette section  
  
|Rubrique|Description|  
|-----------|-----------------|  
|[Le Script MDX de base &#40; MDX &#41;](../../../analysis-services/multidimensional-models/mdx/the-basic-mdx-script-mdx.md)|Décrit en détail le script MDX de base, notamment le script MDX par défaut fourni dans chaque cube, ainsi que le mode de fonctionnement général des scripts MDX au sein d’un cube dans [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].|  
|[La gestion de la portée et contexte &#40; MDX &#41;](../../../analysis-services/multidimensional-models/mdx/managing-scope-and-context-mdx.md)|Décrit l’utilisation de l’instruction [CALCULATE](../../../mdx/mdx-scripting-calculate.md), de l’instruction [SCOPE](../../../mdx/mdx-scripting-scope.md) et de la fonction [This](../../../mdx/this-mdx.md) pour gérer le contexte et la portée au sein d’un script MDX.|  
|[À l’aide de Variables et paramètres &#40; MDX &#41;](../../../analysis-services/multidimensional-models/mdx/using-variables-and-parameters-mdx.md)|Décrit l'utilisation de variables et de paramètres dans un script MDX.|  
|[Gestion des erreurs &#40; MDX &#41;](../../../analysis-services/multidimensional-models/mdx/error-handling-mdx.md)|Explique la gestion des erreurs au sein d'un script MDX.|  
|[Prise en charge MDX &#40; MDX &#41;](../../../analysis-services/multidimensional-models/mdx/supported-mdx-mdx.md)|Fournit la liste des opérateurs, instructions et fonctions MDX pris en charge dans un script MDX.|  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du langage MDX &#40; MDX &#41;](../../../mdx/mdx-language-reference-mdx.md)  
  
  
