---
title: "À l’aide de fonctions logiques | Documents Microsoft"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology: analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: kbMDX
helpviewer_keywords: logical functions [MDX]
ms.assetid: 0cb34d53-9146-4924-9c9b-607afcb7a2be
caps.latest.revision: "25"
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: ecfb449175242454c1f643d8179e3eb6863df5fc
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="using-logical-functions"></a>Utilisation de fonctions logiques
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Une fonction logique exécute une opération ou une comparaison logique sur des objets et des expressions et retourne une valeur booléenne. Les fonctions logiques sont essentielles dans la syntaxe MDX (Multidimensional Expressions) pour déterminer la position d'un membre.  
  
 La fonction logique couramment utilisée est le **IsEmpty** (fonction). Pour plus d’informations sur l’utilisation de la **IsEmpty** , consultez [fonctionne avec des valeurs vides](../mdx/working-with-empty-values.md).  
  
 La requête suivante montre comment utiliser le **IsLeaf** et **IsAncestor** fonctions :  
  
 `WITH`  
  
 `//Returns true if the CurrentMember on Calendar is a leaf member, ie it has no children`  
  
 `MEMBER MEASURES.[IsLeafDemo] AS IsLeaf([Date].[Calendar].CurrentMember)`  
  
 `//Returns true if the CurrentMember on Calendar is an Ancestor of July 1st 2001`  
  
 `MEMBER MEASURES.[IsAncestorDemo] AS IsAncestor([Date].[Calendar].CurrentMember, [Date].[Calendar].[Date].&[1])`  
  
 `SELECT{MEASURES.[IsLeafDemo],MEASURES.[IsAncestorDemo] } ON 0,`  
  
 `[Date].[Calendar].MEMBERS ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions &#40; La syntaxe MDX &#41;](../mdx/functions-mdx-syntax.md)  
  
  
