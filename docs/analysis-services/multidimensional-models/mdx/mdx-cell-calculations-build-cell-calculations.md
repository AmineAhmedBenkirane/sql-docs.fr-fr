---
title: "Création de calculs de cellules dans la syntaxe MDX (MDX) | Documents Microsoft"
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
- calculated cells [MDX]
- queries [MDX], cell calculations
- cells [MDX]
- MDX [Analysis Services], calculations
- calculation subcubes [MDX]
- calculated values [MDX]
- Multidimensional Expressions [Analysis Services], cell calculations
ms.assetid: 068aea63-d419-4791-a960-3d74e76f808e
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 8e2e963c47746a85e760b3b4464edd5cbe39f1fe
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2018
---
# <a name="mdx-cell-calculations---build-cell-calculations"></a>Calculs de cellules MDX - calculs de cellules de Build
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
MDX (Multidimensional Expressions) propose un certain nombre d'outils qui vous permettent de générer des valeurs calculées comme des membres calculés, des cumuls personnalisés et des membres personnalisés. Cependant, il est difficile d'affecter un jeu de cellules spécifique (voire une cellule unique) à l'aide de ces outils.  
  
 Pour générer des valeurs calculées en particulier pour des cellules, vous devez utiliser la fonctionnalité de cellules calculées de MDX. Les cellules calculées permettent de définir une « tranche » de cellules, appelée *sous-cube de calcul*, et d’appliquer une formule à chacune des cellules de ce sous-cube de calcul, sous réserve d’une condition facultative qui peut être appliquée à chaque cellule.  
  
 Les cellules calculées proposent également des fonctionnalités complexes (par exemple, des formules de recherche d’objectif, telles qu'elles sont utilisées dans les KPI, ou des formules d'analyse spéculative). Ce niveau de fonctionnalité provient de la fonctionnalité d’ordre de passage de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] qui permet d’effectuer des passages récursifs sur des cellules calculées, avec des formules de calcul appliquées lors de passages spécifiques dans l’ordre de passage. Pour plus d’informations sur l’ordre de passage, consultez [Présentation des concepts d’ordre de passage et d’ordre de résolution &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/mdx-data-manipulation-understanding-pass-order-and-solve-order.md).  
  
 Du point de vue de leur portée, les cellules calculées sont semblables aux jeux nommés et aux membres calculés en ce sens qu'elles peuvent créées temporairement pour la durée d'une session ou d'une seule requête, ou encore être globalement mises à la disposition des utilisateurs dans le cadre d'un cube :  
  
-   **Étendue de requête** Pour créer une cellule calculée définie en tant que partie d’une requête MDX, et dont l’étendue est donc limitée à la requête, utilisez le mot clé WITH. Vous pouvez ensuite utiliser la cellule calculée au sein d'une instruction MDX SELECT. De cette manière, vous pouvez modifier la cellule calculée créée à l’aide du mot clé **WITH** sans porter atteinte à l’instruction SELECT.  
  
     Pour plus d’informations sur l’utilisation du mot clé WITH pour la création de membres calculés, consultez [Création de calculs de cellules au niveau de la requête &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/mdx-cell-calculations-query-scoped-cell-calculations.md).  
  
-   **Étendue de session** Pour créer un membre calculé dont l’étendue est plus étendue que le contexte de la requête, c’est-à-dire dont l’étendue est la durée de vie de la session MDX, vous devez utiliser l’instruction CREATE CELL CALCULATION ou ALTER CUBE.  
  
     Pour plus d’informations sur l’utilisation de l’instruction CREATE CELL CALCULATION ou ALTER CUBE afin de créer des cellules calculées dans une session, consultez [Création de cellules calculées au niveau de la session](../../../analysis-services/multidimensional-models/mdx/mdx-cell-calculations-session-scoped-calculated-cells.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Instruction ALTER CUBE &#40; MDX &#41;](../../../mdx/mdx-data-definition-alter-cube.md)   
 [CRÉER une instruction de calcul de cellule &#40; MDX &#41;](../../../mdx/mdx-data-definition-create-cell-calculation.md)   
 [Création de calculs de cellules d’étendue de requête &#40; MDX &#41;](../../../analysis-services/multidimensional-models/mdx/mdx-cell-calculations-query-scoped-cell-calculations.md)   
 [Principes de base de requête MDX &#40; Analysis Services &#41;](../../../analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services.md)  
  
  
