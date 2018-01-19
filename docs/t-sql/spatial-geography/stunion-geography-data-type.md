---
title: "STUnion (Type de données geography) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|spatial-geography
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- STUnion (geography Data Type)
- STUnion_TSQL
dev_langs: TSQL
helpviewer_keywords: STUnion method
ms.assetid: 9bf87691-efd8-4c53-bd2f-eefe0acd19ca
caps.latest.revision: "23"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 686096ef4e69427574edf71ce12db7c1c2862384
ms.sourcegitcommit: 6c54e67818ec7b0a2e3c1f6e8aca0fdf65e6625f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2018
---
# <a name="stunion-geography-data-type"></a>STUnion (type de données geography)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retourne un objet qui représente l’union entre un **geography** instance avec un autre **geography** instance.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.STUnion ( other_geography )  
```  
  
## <a name="arguments"></a>Arguments  
 *other_geography*  
 Une autre **geography** instance pour former une union avec l’instance sur laquelle STUnion() est appelé.  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **geography**  
  
 Type de retour CLR : **SqlGeography**  
  
## <a name="exceptions"></a>Exceptions  
 Cette méthode lève un **ArgumentException** si l’instance contient un contour antipode.  
  
## <a name="remarks"></a>Notes  
 Cette méthode retourne toujours null si les identificateurs de référence spatiale (SRID) de la **geography** instances ne correspondent pas.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prend en charge des instances spatiales qui sont plus grandes qu'un hémisphère. Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le jeu de résultats possibles retourné sur le serveur a été étendu aux **FullGlobe** instances.  
  
 Le résultat peut contenir des segments d'arc de cercle uniquement si les instances d'entrée contiennent des segments d'arc de cercle.  
  
 Cette méthode n'est pas précise.  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-computing-the-union-of-two-polygons"></a>A. Calcul de l'union de deux polygones  
 L'exemple suivant utilise `STUnion()` pour calculer l'union de deux instances `Polygon`.  
  
```  
DECLARE @g geography;  
DECLARE @h geography;  
SET @g = geography::STGeomFromText('POLYGON((-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))', 4326);  
SET @h = geography::STGeomFromText('POLYGON((-122.351 47.656, -122.341 47.656, -122.341 47.661, -122.351 47.661, -122.351 47.656))', 4326);  
SELECT @g.STUnion(@h).ToString();  
```  
  
### <a name="b-producing-a-fullglobe-result"></a>B. Génération d'un résultat FullGlobe  
 L'exemple suivant produit un `FullGlobe` lorsque `STUnion()` combine deux instances `Polygon`.  
  
```
 DECLARE @g geography = 'POLYGON ((-122.358 47.653, -122.358 47.658,-122.348 47.658, -122.348 47.649, -122.358 47.653))';  
 DECLARE @h geography = 'POLYGON ((-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))';  
 SELECT @g.STUnion(@h).ToString();
 ```  
  
### <a name="c-producing-a-triagonal-hole-from-a-union-of-a-curvepolygon-and-a-traigonal-hole"></a>C. Génération d'un trou triagonal d'une union d'un CurvePolygon et d'un trou triagonal.  
 L'exemple suivant produit un trou triagonal de l'union d'un `CurvePolygon` avec une instance `Polygon`.  
  
```
 DECLARE @g geography = 'POLYGON ((-0.5 0, 0 1, 0.5 0.5, -0.5 0))';  
 DECLARE @h geography = 'CURVEPOLYGON(COMPOUNDCURVE(CIRCULARSTRING(0 0, 0.7 0.7, 0 1), (0 1, 0 0)))';  
 SELECT @g.STUnion(@h).ToString();
 ```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes OGC sur des instances geography](../../t-sql/spatial-geography/ogc-methods-on-geography-instances.md)  
  
  
