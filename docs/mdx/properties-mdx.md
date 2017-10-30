---
title: "Propriétés (MDX) | Documents Microsoft"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Properties
dev_langs:
- kbMDX
helpviewer_keywords:
- Properties function
ms.assetid: 2d8442c5-30c4-4fd1-99ea-9845b6533e41
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: c77317f1717cc2f4b637839e40836a2096fa517d
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="properties-mdx"></a>Properties (MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retourne une chaîne ou une valeur fortement typée, contenant une valeur de propriété de membre.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Member_Expression.Properties(Property_Name [, TYPED])  
```  
  
## <a name="arguments"></a>Arguments  
 *Argument*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un membre.  
  
 *Property_name*  
 Expression de chaîne valide du nom d'une propriété de membre.  
  
## <a name="remarks"></a>Notes  
 Le **propriétés** fonction retourne la valeur du membre spécifié pour la propriété de membre spécifié. La propriété de membre peut être une des propriétés de membre intrinsèques, tels que **nom**, **ID**, **clé**, ou **légende**, ou il peut être une propriété de membre définies par l’utilisateur. Pour plus d’informations, consultez [des propriétés de membre intrinsèques &#40; MDX &#41; ](../analysis-services/multidimensional-models/mdx/mdx-member-properties-intrinsic-member-properties.md) et [des propriétés de membre définies par l’utilisateur &#40; MDX &#41; ](../analysis-services/multidimensional-models/mdx/mdx-member-properties-user-defined-member-properties.md).  
  
 Par défaut, la valeur est définie comme une chaîne. Si **TYPÉ** est spécifié, la valeur de retour est fortement typée.  
  
-   Si le type de propriété est intrinsèque, la fonction retourne le type d'origine du membre.  
  
-   Si le type de propriété est définie par l’utilisateur, le type de la valeur de retour est le même que le type de la valeur de retour de la **MemberValue** (fonction).  
  
> [!NOTE]  
>  Properties('Key') retourne le même résultat que Key0, sauf en ce qui concerne les clés composites. Properties('Key') retourne la valeur Null pour les clés composites. Utilisez la touche*x* syntaxe pour les clés composites comme illustré dans l’exemple suivant. Properties('Key0'), Properties('Key1'), Properties('Key2'), etc., forment collectivement la clé composite.  
  
## <a name="example"></a>Exemple  
 L'exemple ci-dessous retourne à la fois des propriétés de membres intrinsèques et définies par l'utilisateur en se servant de l'argument TYPED pour retourner la valeur fortement typée de la propriété de membre Day Name (Jour).  
  
```  
WITH MEMBER Measures.MemberName AS   
   [Date].[Calendar].[July 1, 2003].Properties('Name')  
MEMBER Measures.MemberVal AS   
   [Date].[Calendar].[July 1, 2003].Properties('Member_Value')  
MEMBER Measures.MemberKey AS   
   [Date].[Calendar].[July 1, 2003].Properties('Key')  
MEMBER Measures.MemberID AS   
   [Date].[Calendar].[July 1, 2003].Properties('ID')  
MEMBER Measures.MemberCaption AS   
   [Date].[Calendar].[July 1, 2003].Properties('Caption')  
MEMBER Measures.DayName AS   
   [Date].[Calendar].[July 1, 2003].Properties('Day Name', TYPED)  
MEMBER Measures.DayNameTyped AS   
   [Date].[Calendar].[July 1, 2003].Properties('Day Name')  
MEMBER Measures.DayofWeek AS   
   [Date].[Calendar].[July 1, 2003].Properties('Day of Week')  
MEMBER Measures.DayofMonth AS   
   [Date].[Calendar].[July 1, 2003].Properties('Day of Month')  
MEMBER Measures.DayofYear AS   
   [Date].[Calendar].[July 1, 2003].Properties('Day of Year')  
  
SELECT {Measures.MemberName  
   , Measures.MemberVal  
   , Measures.MemberKey  
   , Measures.MemberID  
   , Measures.MemberCaption  
   , Measures.DayName  
   , Measures.DayNameTyped  
   , Measures.DayofWeek  
   , Measures.DayofMonth  
   , Measures.DayofYear  
   }  ON 0  
FROM [Adventure Works]  
```  
  
 L’exemple suivant illustre l’utilisation de la clé*x* propriété.  
  
```  
WITH   
MEMBER Measures.MemberKey AS   
   [Customer].[Customer Geography].[State-Province].&[QLD]&[AU].Properties('Key')  
MEMBER Measures.MemberKey0 AS   
   [Customer].[Customer Geography].[State-Province].&[QLD]&[AU].Properties('Key0')  
MEMBER Measures.MemberKey1 AS   
   [Customer].[Customer Geography].[State-Province].&[QLD]&[AU].Properties('Key1')  
  
SELECT {Measures.MemberKey  
   , Measures.MemberKey0  
   , Measures.MemberKey1     
   }  ON 0  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [À l’aide des propriétés de membre &#40; MDX &#41;](../analysis-services/multidimensional-models/mdx/mdx-member-properties.md)   
 [Référence des fonctions MDX &#40; MDX &#41;](../mdx/mdx-function-reference-mdx.md)  
  
  

