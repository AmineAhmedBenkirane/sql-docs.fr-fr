---
title: CalculationPassValue (MDX) | Documents Microsoft
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
- CALCULATIONPASSVALUE
dev_langs:
- kbMDX
helpviewer_keywords:
- CalculationPassValue function
ms.assetid: 1b4012cb-c8c7-441a-bb9c-59430703b189
caps.latest.revision: 45
author: Minewiskan
ms.author: owend
manager: erikre
ms.openlocfilehash: bac34c96e9acaeeb480b12cd3acded7e08225093
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="calculationpassvalue-mdx"></a>CalculationPassValue (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Retourne la valeur numérique ou la valeur de chaîne d'une expression MDX (Multidimensional Expressions) évaluée pendant le test de calcul spécifié d'un cube.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      Numeric syntax  
CalculationPassValue(Numeric_Expression,Pass_Value [, ABSOLUTE | RELATIVE [,ALL]])  
String syntax  
CalculationPassValue(String_Expression ,Pass_Value [, ABSOLUTE | RELATIVE [,ALL]])  
```  
  
## <a name="arguments"></a>Arguments  
 *Numeric_expression*  
 Expression numérique valide qui correspond généralement à une expression MDX (Multidimensional Expressions) des coordonnées des cellules qui retournent un nombre.  
  
 *String_Expression*  
 Expression de chaîne valide qui correspond généralement à une expression MDX (Multidimensional Expressions) valide des coordonnées des cellules qui retournent un nombre exprimé sous forme de chaîne.  
  
 *Pass_Value*  
 Expression numérique valide qui précise le numéro du test de calcul.  
  
 ABSOLUTE  
 Une valeur d’indicateur accès qui spécifie que la *Pass_Value* paramètre contient l’index de base zéro de la passe de calcul. ABSOLUTE est la valeur d'indicateur d'accès par défaut si aucune valeur de ce type n'est spécifiée.  
  
 RELATIVE  
 Une valeur d’indicateur accès qui spécifie que la *Pass_Value* paramètre contient un décalage relatif au test de calcul du calcul déclencheur. Si le décalage se résout à un index de test de calcul inférieur à 0, le test de calcul 0 est utilisé et aucune erreur ne survient.  
  
 ALL  
 Lorsque vous définissez cet indicateur, toutes les valeurs sont NULL, sauf les valeurs chargées par le moteur de stockage. Si l'indicateur n'est pas défini, les valeurs sont agrégées sans qu'aucun calcul ne soit appliqué.  
  
## <a name="remarks"></a>Notes  
 Si une expression numérique est spécifiée, la fonction retourne une valeur numérique en évaluant l'expression numérique MDX précisée dans le test de calcul spécifié, et éventuellement modifiée par un indicateur d'accès et un modificateur d'indicateur d'accès.  
  
 Si une expression de chaîne est fournie, la fonction retourne une valeur de chaîne en évaluant l’expression de chaîne MDX précisée dans le test de calcul spécifié et éventuellement modifiée par un indicateur d’accès et un modificateur d’indicateur d’accès *.*  
  
 Avec une résolution automatique de la récursivité dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], cette fonction a peu utilisation pratique.  
  
> [!NOTE]  
>  Seuls les administrateurs peuvent utiliser le **CalculationPassValue** fonction dans un script MDX. Une erreur se produit si un script MDX contenant cette fonction est exécuté dans le contexte d'un rôle qui ne dispose pas des droits d'administrateur.  
  
## <a name="see-also"></a>Voir aussi  
 [CalculationCurrentPass & #40 ; MDX & #41 ;](../mdx/calculationcurrentpass-mdx.md)   
 [IIf &#40;MDX&#41;](../mdx/iif-mdx.md)   
 [Référence des fonctions MDX & #40 ; MDX & #41 ;](../mdx/mdx-function-reference-mdx.md)  
  
  
