---
title: "STCurveToLine (Type de données geography) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- STCurveToLine_TSQL
- STCurveToLine
dev_langs:
- TSQL
helpviewer_keywords:
- STCurveToLine method (geography)
ms.assetid: 2f863a85-6168-465a-b32f-bb5e3de58dee
caps.latest.revision: 12
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 9d2ad93d8bc292ebb86233917dc3f934fbe57dca
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="stcurvetoline-geography-data-type"></a>STCurveToLine (type de données geography)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retourne une approximation polygonale d’une **geography** instance qui contient les segments d’arc de cercle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.STCurveToLine()  
```  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **geography**  
  
 Type de retour CLR : **SqlGeography**  
  
## <a name="remarks"></a>Notes  
 Retourne un **LineString** d’instance pour un **CircularString** ou **CompoundCurve** instance.  
  
 Retourne un **polygone** d’instance pour un **CurvePolygon** instance.  
  
 Retourner une copie de **geography** instances qui ne contiennent pas **CircularString**, **CompoundCurve**, ou **CurvePolygon** instances.  
  
 Contrairement à la spécification SQL MM, cette méthode n’utilise pas les valeurs de coordonnée z dans le calcul de l’approximation polygonale. Toutes les valeurs de coordonnée z présent dans l’appel **geography** instance sont ignorés.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant retourne une instance `LineString` qui est une approximation polygonale d'une instance `CircularString` :  
  
```
 DECLARE @g1 geography = 'CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653)';  
 DECLARE @g2 geography;  
 SET @g2 = @g1.STCurveToLine();  
 SELECT @g1.STNumPoints() AS G1, @g2.STNumPoints() AS G2;
 ```  
  
## <a name="see-also"></a>Voir aussi  
 [STLength &#40; Type de données geography &#41;](../../t-sql/spatial-geography/stlength-geography-data-type.md)   
 [STNumPoints &#40; Type de données geography &#41;](../../t-sql/spatial-geography/stnumpoints-geography-data-type.md)   
 [Présentation des types de données spatiales](../../relational-databases/spatial/spatial-data-types-overview.md)  
  
  
