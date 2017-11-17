---
title: "STCurveN (Type de données geometry) | Documents Microsoft"
ms.custom: 
ms.date: 08/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|spatial-geography
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- STCurveN method (geometry)
ms.assetid: 64adf1a1-3a41-41fb-b7d1-44390c3e4ea9
caps.latest.revision: 21
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: dd5b459bfa271d98844d30455e4e1a9e03d0e2cd
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="stcurven-geometry-data-type"></a>STCurveN (type de données geometry)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

Retourne la courbe spécifiée d’un **geometry** instance qui est un **LineString**, **CircularString**, **CompoundCurve**, ou **MultiLineString**.
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.STCurveN ( curve_index )  
```  
  
## <a name="arguments"></a>Arguments  
 *curve_index*  
 Est un **int** expression comprise entre 1 et le nombre de courbes dans le **geometry** instance.  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **geometry**  
  
 Type de retour CLR : **SqlGeometry**  
  
## <a name="exceptions"></a>Exceptions  
 Si *curve_index* 1 < alors un `ArgumentOutOfRangeException` est levée.  
  
## <a name="remarks"></a>Notes  
 **NULL** est retourné lorsque une des actions suivantes se produit :  
  
-   le **geometry** instance est déclarée, mais pas instanciée  
  
-   le **geometry** instance est vide  
  
-   *curve_index* dépasse le nombre de courbes dans le **geometry** instance  
  
-   le **geometry** instance est un **Point**, **MultiPoint**, **polygone**, **CurvePolygon**, ou **MultiPolygon**  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-using-stcurven-on-a-circularstring-instance"></a>A. Utilisation de STCurveN() sur une instance CircularString  
 L'exemple suivant retourne la deuxième courbe dans une instance `CircularString` :  
  
```
 DECLARE @g geometry = 'CIRCULARSTRING(0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)';  
 SELECT @g.STCurveN(2).ToString();
 ```  
  
 L'exemple précédent de cette rubrique retourne :  
  
 `CIRCULARSTRING (3 6.3246, 0 7, -3 6.3246)`  
  
### <a name="b-using-stcurven-on-a-compoundcurve-instance-with-one-circularstring-instance"></a>B. Utilisation de STCurveN() sur une instance CompoundCurve avec une instance CircularString  
 L'exemple suivant retourne la deuxième courbe dans une instance `CompoundCurve` :  
  
```
 DECLARE @g geometry = 'COMPOUNDCURVE(CIRCULARSTRING(0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0))';  
 SELECT @g.STCurveN(2).ToString();
 ```  
  
 L'exemple précédent de cette rubrique retourne :  
  
 `CIRCULARSTRING (3 6.3246, 0 7, -3 6.3246)`  
  
### <a name="c-using-stcurven-on-a-compoundcurve-instance-with-three-circularstring-instances"></a>C. Utilisation de STCurveN() sur une instance CompoundCurve avec trois instances CircularString  
 L'exemple suivant utilise une instance `CompoundCurve` qui combine trois instances `CircularString` distinctes dans la même séquence de courbes que l'exemple précédent :  
  
```
 DECLARE @g geometry = 'COMPOUNDCURVE (CIRCULARSTRING (0 0, 1 2.1082, 3 6.3246), CIRCULARSTRING(3 6.3246, 0 7, -3 6.3246), CIRCULARSTRING(-3 6.3246, -1 2.1082, 0 0))';  
 SELECT @g.STCurveN(2).ToString();
 ```  
  
 L'exemple précédent de cette rubrique retourne :  
  
 `CIRCULARSTRING (3 6.3246, 0 7, -3 6.3246)`  
  
 Notez que les résultats sont les mêmes pour les trois exemples précédents. Quel que soit le format WKT (Well-known Text) utilisé pour entrer la même séquence de courbes, les résultats retournés par `STCurveN()` sont identiques lorsqu'une instance `CompoundCurve` est utilisée.  
  
### <a name="d-validating-the-parameter-before-calling-stcurven"></a>D. Validation du paramètre avant d'appeler STCurveN()  
 L’exemple suivant montre comment s’assurer que `@n` est valide avant d’appeler le `STCurveN()`méthode :  
  
```
 DECLARE @g geometry;  
 DECLARE @n int;  
 SET @n = 3;  
 SET @g = geometry::Parse('CIRCULARSTRING(0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)');  
 IF @n >= 1 AND @n <= @g.STNumCurves()  
 BEGIN  
 SELECT @g.STCurveN(@n).ToString();  
 END
 ```  
  
## <a name="see-also"></a>Voir aussi  
 [STNumCurves &#40; Type de données geometry &#41;](../../t-sql/spatial-geometry/stnumcurves-geometry-data-type.md)   
 [Méthodes OGC sur les Instances géométriques](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  


