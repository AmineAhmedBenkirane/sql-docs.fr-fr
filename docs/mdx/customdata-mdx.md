---
title: CustomData (MDX) | Documents Microsoft
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
- EXISTS
dev_langs:
- kbMDX
helpviewer_keywords:
- Exists function
ms.assetid: 61d9f5a2-6f56-4179-a39b-317c8e0a2cdd
caps.latest.revision: 18
author: Minewiskan
ms.author: owend
manager: erikre
ms.openlocfilehash: 5fb7c745ac65b41095c3d4dfb41b62b081d83c1d
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="customdata-mdx"></a>CustomData (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Retourne la valeur de la **CustomData** la propriété de chaîne de connexion s’il est défini ; sinon, **null**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
CustomData()  
```  
  
## <a name="return-value"></a>Valeur retournée  
 Le **CustomData** fonction peut récupérer le **CustomData** propriété de chaîne de connexion et passer un paramètre à utiliser par les fonctions MDX (Multidimensional Expressions) et les instructions, telles que de configuration [UserName (MDX)](../mdx/username-mdx.md) et [instruction CALL (MDX)](../mdx/mdx-data-manipulation-call.md). Par exemple, cette fonction peut être utilisée dans une expression de la sécurité dynamique pour sélectionner les membres du jeu autorisé/refusé pour la valeur de chaîne dans le **CustomData** propriété de chaîne de connexion.  
  
## <a name="example"></a>Exemple  
 La requête suivante affiche la valeur retournée par la **CustomData** fonction dans une mesure calculée :  
  
```  
WITH MEMBER [Measures].CUSTOMDATADEMO AS CUSTOMDATA()  
SELECT [Measures].CUSTOMDATADEMO ON 0  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des fonctions MDX & #40 ; MDX & #41 ;](../mdx/mdx-function-reference-mdx.md)  
  
  
