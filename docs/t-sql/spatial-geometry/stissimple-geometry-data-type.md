---
title: "STIsSimple (Type de données geometry) | Documents Microsoft"
ms.custom: 
ms.date: 08/03/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- STIsSimple_TSQL
- STIsSimple (geometry Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- STIsSimple (geometry Data Type)
ms.assetid: da8f45d4-4f9c-405d-b883-760eb5344a71
caps.latest.revision: 20
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 12b150546378ef76c0165c6d8e3c166e93db304b
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="stissimple-geometry-data-type"></a>STIsSimple (type de données geometry)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

Retourne 1 si une **geometry** instance est simple, tel que défini par l’OGC Open Geospatial Consortium (). Retourne 0 si une **geometry** instance n’est pas simple.
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.STIsSimple ( )  
```  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **bits**  
  
 Type de retour CLR : **SqlBoolean**  
  
## <a name="remarks"></a>Notes  
 Pour être simple, un **geometry** instance doit satisfaire toutes les conditions suivantes :  
  
-   Chaque graphique de l'instance ne doit pas se croiser lui-même, sauf à ses points de terminaison.  
  
-   Deux graphiques de l'instance ne peuvent se croiser l'un l'autre à un point qui n'est pas dans leurs limites.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant crée une instance `LineString` non simple qui se croise elle-même et utilise `STIsSimple()` pour tester si le `LineString` est simple.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('LINESTRING(0 0, 2 2, 0 2, 2 0)', 0);  
SELECT @g.STIsSimple();  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes OGC sur les Instances géométriques](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  


