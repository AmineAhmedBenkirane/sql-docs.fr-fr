---
title: "STIsSimple (Type de données geometry) | Documents Microsoft"
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
- STIsSimple_TSQL
- STIsSimple (geometry Data Type)
dev_langs: TSQL
helpviewer_keywords: STIsSimple (geometry Data Type)
ms.assetid: da8f45d4-4f9c-405d-b883-760eb5344a71
caps.latest.revision: "20"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 5240f2a8c9dc28f9256db87106fdcfaf0b689034
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="stissimple-geometry-data-type"></a>STIsSimple (type de données geometry)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

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
 [Méthodes OGC sur des instances geography](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  

