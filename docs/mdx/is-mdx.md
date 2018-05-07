---
title: EST (MDX) | Documents Microsoft
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
- IS
dev_langs:
- kbMDX
helpviewer_keywords:
- IS operator
ms.assetid: dc8c0b91-3bb1-49e5-8d70-57545baaa8e0
caps.latest.revision: 29
author: Minewiskan
ms.author: owend
manager: erikre
ms.openlocfilehash: 5a3cc017970de59914e639c42a23e7808756f076
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="is-mdx"></a>IS (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Effectue une comparaison logique sur deux expressions d'objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Expression1 IS ( Expression2 | NULL )  
```  
  
#### <a name="parameters"></a>Paramètres  
 *Expression1*  
 Expression MDX (Multidimensional Expressions) valide retournant une référence à un objet MDX.  
  
 *Expression2*  
 Expression MDX valide retournant une référence à un objet MDX.  
  
## <a name="return-value"></a>Valeur retournée  
 Valeur booléenne qui retourne **true** si les deux arguments font référence au même objet ; sinon, **false**. Si le **NULL** mot clé est spécifié, l’opérateur retourne **true** si *Expression1* est **null**; sinon, **false**.  
  
## <a name="remarks"></a>Notes  
 Le **IS** opérateur est souvent utilisée pour déterminer si tuples et membres sont idempotents, ce qui signifie qu’ils sont tout à fait équivalents.  
  
## <a name="examples"></a>Exemples  
 L’exemple suivant montre comment utiliser le **IS** opérateur afin de vérifier si le membre actuel sur un axe est un membre spécifique :  
  
 `With`  
  
 `//Returns TRUE if the currentmember is Bikes`  
  
 `Member [Measures].[IsBikes?] AS`  
  
 `[Product].[Category].CurrentMember IS [Product].[Category].&[1]`  
  
 `SELECT`  
  
 `{[Measures].[IsBikes?]} ON 0,`  
  
 `[Product].[Category].[Category].Members ON 1`  
  
 `FROM`  
  
 `[Adventure Works]`  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des opérateurs MDX &#40;MDX&#41;](../mdx/mdx-operator-reference-mdx.md)  
  
  
