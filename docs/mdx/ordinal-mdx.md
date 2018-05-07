---
title: Ordinal (MDX) | Documents Microsoft
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
- Ordinal
dev_langs:
- kbMDX
helpviewer_keywords:
- Ordinal function
ms.assetid: 9d416c39-da4a-4f0d-8d85-a76af5df0a87
caps.latest.revision: 28
author: Minewiskan
ms.author: owend
manager: erikre
ms.openlocfilehash: 3e1a3e550dd694972ce137d44f620bf87b1169de
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ordinal-mdx"></a>Ordinal (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Retourne la valeur ordinale de base zéro associée à un niveau.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Level_Expression.Ordinal   
```  
  
## <a name="arguments"></a>Arguments  
 *Level_Expression*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un niveau.  
  
## <a name="remarks"></a>Notes  
 Le **ordinale** fonction est souvent utilisée conjointement avec la **IIF** et **CurrentMember** fonctions pour afficher de manière conditionnelle des valeurs différentes à différents niveaux de hiérarchie, en fonction de la position ordinale de chaque cellule spécifique dans le résultat de la requête. Par exemple, vous pouvez utiliser la **Ordinal** fonction pour effectuer des calculs à certains niveaux et affiche la valeur par défaut « N/a » à d’autres niveaux.  
  
## <a name="example"></a>Exemple  
 L'exemple ci-dessous retourne le nombre ordinal du niveau Calendar Quarter dans la hiérarchie Calendar.  
  
```  
WITH MEMBER Measures.x AS [Date].[Calendar].[Calendar Quarter].Ordinal  
SELECT Measures.x on 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des fonctions MDX & #40 ; MDX & #41 ;](../mdx/mdx-function-reference-mdx.md)  
  
  
