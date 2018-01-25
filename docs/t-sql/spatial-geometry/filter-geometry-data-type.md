---
title: "Filtre (Type de données geometry) | Documents Microsoft"
ms.custom: 
ms.date: 08/03/2017
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
- Filter
- Filter_TSQL
- Filter (geometry Data Type)
dev_langs: TSQL
helpviewer_keywords: Filter method
ms.assetid: 3d629a39-157e-4159-a3ca-a3c2e0ed4160
caps.latest.revision: "10"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: e09f4ac5d6d4ecaf32f6b500aee9a3a50c772c02
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="filter-geometry-data-type"></a>Filter (type de données geometry)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Une méthode qui offre une méthode rapide index uniquement d’intersection pour déterminer si un **geometry** instance croise une autre **geometry** instance, en supposant un index est disponible.
  
Retourne 1 si une **geometry** instance potentiellement entre en intersection avec une autre **geometry** instance. Cette méthode peut produire un retour de faux positif, et le résultat exact peut être dépendant du plan. Retourne une valeur 0 exacte (retour négatif vrai) s’il n’existe aucune intersection de **geometry** instance a été trouvée.
  
Dans le cas où un index n’est pas disponible ou n’est pas utilisé, la méthode retourne les mêmes valeurs que **STIntersects()** lorsqu’elle est appelée avec les mêmes paramètres.
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.Filter ( other_geometry )  
```  
  
## <a name="arguments"></a>Arguments  
 *other_geometry*  
 Une autre **geometry** instance à comparer à l’instance sur laquelle Filter() est appelée.  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **bits**  
  
 Type de retour CLR : **SqlBoolean**  
  
## <a name="remarks"></a>Notes  
 Cette méthode n'est pas déterministe et n'est pas précise.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant utilise `Filter()` pour déterminer si deux instances `geometry` entrent en intersection.  
  
```  
CREATE TABLE sample (id int primary key, g geometry);  
GO  
INSERT INTO sample VALUES  
   (0, geometry::Point(0, 0, 0)),  
   (1, geometry::Point(0, 1, 0)),  
   (2, geometry::Point(0, 2, 0)),  
   (3, geometry::Point(0, 3, 0)),  
   (4, geometry::Point(0, 4, 0));  
  
CREATE SPATIAL INDEX sample_idx ON sample(g)  
WITH (bounding_box = (-8000, -8000, 8000, 8000));  
GO  
SELECT id  
FROM sample   
WHERE g.Filter(geometry::Parse('POLYGON((-1 -1, 1 -1, 1 1, -1 1, -1 -1))')) = 1;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes étendues sur les Instances géométriques](../../t-sql/spatial-geometry/extended-methods-on-geometry-instances.md)   
 [STIntersects &#40;type de données geometry&#41;](../../t-sql/spatial-geometry/stintersects-geometry-data-type.md)  
  
  

