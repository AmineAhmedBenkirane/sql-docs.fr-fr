---
title: "AsTextZM (Type de données geometry) | Documents Microsoft"
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
- AsTextZM_TSQL
- AsTextZM
- AsTextZM (geometry Data Type)
- AsTextZM_(geometry_Data_Type)_TSQL
dev_langs: TSQL
helpviewer_keywords: AsTextZM (geometry Data Type)
ms.assetid: 08ac8aa0-aff7-4b22-87e0-1a1d55dcbc04
caps.latest.revision: "20"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 0b87b51e59b6416da601f4b4d730f9a9a3dcfc5c
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="astextzm-geometry-data-type"></a>AsTextZM (type de données geometry)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Retourne la représentation sous forme de réplication continue en cluster (WKT, Open Geospatial Consortium (OGC) Well-Known Text) d’une instance geometry augmentée des **Z** (élévation) et **M** les valeurs (mesure) apportées par l’instance.
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.AsTextZM ()  
```  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **nvarchar (max)**  
  
 Type de retour CLR : **SqlChars**  
  
## <a name="remarks"></a>Notes  
  
## <a name="examples"></a>Exemples  
 L’exemple suivant crée un `Point` instance qui contient **Z** (élévation) et **M** les valeurs (mesure). `STAsText()`Sélectionne les valeurs WKT, (1 2) ; `AsTextZM()` sélectionne les mêmes valeurs WKT et retourne également les valeurs de **Z** et **M**, ce qui (1 2 3 4).  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POINT(1 2 3 4)', 0);  
SELECT @g.STAsText();  
SELECT @g.AsTextZM();  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes étendues sur les Instances géométriques](../../t-sql/spatial-geometry/extended-methods-on-geometry-instances.md)   
 [M &#40; Type de données geometry &#41;](../../t-sql/spatial-geometry/m-geometry-data-type.md)   
 [Z &#40; Type de données geometry &#41;](../../t-sql/spatial-geometry/z-geometry-data-type.md)  
  
  

