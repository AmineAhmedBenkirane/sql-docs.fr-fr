---
title: Hiérarchie (MDX) | Documents Microsoft
ms.custom: ''
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- Hierarchy
dev_langs:
- kbMDX
helpviewer_keywords:
- Hierarchy function
ms.assetid: 5ddf354f-8cae-4e3a-8803-0055fa86bad1
caps.latest.revision: 33
author: Minewiskan
ms.author: owend
manager: erikre
ms.openlocfilehash: 19ee9504682303372450100e2e5ab78abc271bbf
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="hierarchy-mdx"></a>Hierarchy (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Retourne la hiérarchie qui contient le membre ou le niveau spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Member expression syntax  
Member_Expression.Hierarchy  
  
Level expression syntax  
Level_Expression.Hierarchy  
```  
  
## <a name="arguments"></a>Arguments  
 *Argument*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un membre.  
  
 *Level_Expression*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un niveau.  
  
### <a name="examples"></a>Exemples  
 L’exemple suivant retourne le nom de la hiérarchie de calendrier dans la dimension Date dans le cube AdventureWorks.  
  
 `WITH`  
  
 `MEMBER Measures.HierarchyName as`  
  
 `[Date].[Calendar].Currentmember.Hierarchy.Name`  
  
 `SELECT {Measures.HierarchyName}  ON 0,`  
  
 `{[Date].[Calendar].[All Periods]} ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des fonctions MDX & #40 ; MDX & #41 ;](../mdx/mdx-function-reference-mdx.md)  
  
  
