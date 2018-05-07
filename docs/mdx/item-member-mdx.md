---
title: Élément (membre) (MDX) | Documents Microsoft
ms.custom: ''
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- ITEM
dev_langs:
- kbMDX
helpviewer_keywords:
- Item function
ms.assetid: 71cca249-910b-4ecd-9097-1a17b224e219
caps.latest.revision: 35
author: Minewiskan
ms.author: owend
manager: erikre
ms.openlocfilehash: 48944238630565e6a8655cb10a3f6c7d8adddbdf
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="item-member-mdx"></a>Item (Member) (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Retourne un membre à partir d'un tuple spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Tuple_Expression.Item( Index )  
```  
  
## <a name="arguments"></a>Arguments  
 *Tuple_Expression*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un tuple.  
  
 *Index*  
 Expression numérique valide qui précise le membre spécifique par position dans le tuple à retourner.  
  
## <a name="remarks"></a>Notes  
 Le **élément** fonction retourne un membre du tuple spécifié. La fonction retourne le membre trouvé à la position de base zéro spécifiée par *Index*.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant retourne le membre `[2003]` - le premier élément dans le tuple `[Date].[Calendar Year].&[2003], [Measures].[Internet Sales Amount] ).`- sur les colonnes :  
  
 `SELECT`  
  
 `{( [Date].[Calendar Year].&[2003], [Measures].[Internet Sales Amount] ).Item(0)} ON 0`  
  
 `,{[Measures].[Reseller Sales Amount]} ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des fonctions MDX & #40 ; MDX & #41 ;](../mdx/mdx-function-reference-mdx.md)  
  
  
