---
title: = (Égal à) (MDX) | Documents Microsoft
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
- =
dev_langs:
- kbMDX
helpviewer_keywords:
- equals operator (=)
- = (equals operator)
ms.assetid: 5e1f3b58-a646-4fc1-a3f1-19090a5437b7
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: erikre
ms.openlocfilehash: 1e401e3c69397ce7aa1bf0941528a9e31219e2dd
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="-equal-to-mdx"></a>= (Égal à) (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Exécute une opération de comparaison qui détermine si la valeur d'une expression MDX est égale à celle d'une autre expression MDX.  
  
> [!NOTE]  
>  Pour comparer des objets, utilisez la [IS &#40;MDX&#41; ](../mdx/is-mdx.md) opérateur. Par exemple, utilisez l'opérateur IS lorsque vous vérifiez si le membre actuel sur un axe de requête est un membre spécifique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
MDX_Expression = MDX_Expression   
```  
  
#### <a name="parameters"></a>Paramètres  
 *MDX_Expression*  
 Expression MDX valide.  
  
## <a name="return-value"></a>Valeur retournée  
 Valeur booléenne basée sur les conditions suivantes :  
  
-   **true** si la valeur du premier paramètre est égale à la valeur du second paramètre.  
  
-   **false** si la valeur du premier paramètre n’est pas égale à la valeur du second paramètre.  
  
-   **true** si les deux paramètres sont null, ou un paramètre est null, et l’autre paramètre est 0.  
  
## <a name="examples"></a>Exemples  
 La requête suivante offre des exemples de ces conditions :  
  
 `With`  
  
 `--Returns true`  
  
 `Member [Measures].bool1 as 1=1`  
  
 `--Returns false`  
  
 `Member [Measures].bool2 as 1=0`  
  
 `--Returns true`  
  
 `Member [Measures].bool3 as null=null`  
  
 `--Returns true`  
  
 `Member [Measures].bool4 as 0=null`  
  
 `--Returns false`  
  
 `Member [Measures].bool5 as 1=null`  
  
 `Select {[Measures].bool1,[Measures].bool2,[Measures].bool3,[Measures].bool4,[Measures].bool5}`  
  
 `On 0`  
  
 `From [Adventure Works]`  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des opérateurs MDX &#40;MDX&#41;](../mdx/mdx-operator-reference-mdx.md)  
  
  
