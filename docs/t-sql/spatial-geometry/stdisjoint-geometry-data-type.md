---
title: "STDisjoint (Type de données geometry) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
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
f1_keywords:
- STDisjoint_TSQL
- STDisjoint (geometry Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- STDisjoint (geometry Data Type)
ms.assetid: 90acdb21-e826-4d81-afe8-45a71f33282a
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 8257a4a8d3e73d3afd59f9d0774ecc5fb055428f
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="stdisjoint-geometry-data-type"></a>STDisjoint (type de données geometry)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  Retourne 1 si une **geometry** instance est SPATIALEMENT disjointe d’une autre **geometry** instance. Retourne 0 dans le cas contraire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.STDisjoint ( other_geometry )  
```  
  
## <a name="arguments"></a>Arguments  
 *other_geometry*  
 Une autre **geometry** instance à comparer à l’instance sur laquelle `STDisjoint()` est appelé.  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **bits**  
  
 Type de retour CLR : **SqlBoolean**  
  
## <a name="remarks"></a>Notes  
 Deux **geometry** instances sont disjointes si l’intersection de leurs ensembles de points est vide.  
  
 Cette méthode retourne toujours null si l’ID de référence spatiale (SRID) de la **geometry** instances ne correspondent pas.  
  
## <a name="examples"></a>Exemples  
 L’exemple suivant utilise `STDisjoint()` pour tester deux **geometry** pour les instances spatiales disjoint.  
  
```  
DECLARE @g geometry;  
DECLARE @h geometry;  
SET @g = geometry::STGeomFromText('LINESTRING(0 2, 2 0, 4 2)', 0);  
SET @h = geometry::STGeomFromText('POINT(1 1)', 0);  
SELECT @g.STDisjoint(@h);  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes OGC sur des instances geography](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  
