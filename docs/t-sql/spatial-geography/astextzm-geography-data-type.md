---
title: "AsTextZM (Type de données geography) | Documents Microsoft"
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
- AsTextZM (geography Data Type)
- AsTextZM_TSQL
- AsTextZM
- AsTextZM_(geography_Data_Type)_TSQL
dev_langs: TSQL
helpviewer_keywords: AsTextZM method
ms.assetid: e9dc27f6-e945-4457-8498-7644db34008e
caps.latest.revision: "14"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c3672470989920d677958a9e4063f3585288c20a
ms.sourcegitcommit: 6c54e67818ec7b0a2e3c1f6e8aca0fdf65e6625f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2018
---
# <a name="astextzm-geography-data-type"></a>AsTextZM (type de données geography)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retourne la représentation de la réplication continue en cluster (WKT, Open Geospatial Consortium (OGC) Well-Known Text) d’un **geography** instance augmentée des **Z** (élévation) et **M** les valeurs (mesure) apportées par l’instance.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.AsTextZM ()  
```  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **nvarchar (max)**  
  
 Type de retour CLR : **SqlChars**  
  
## <a name="remarks"></a>Notes  
  
## <a name="examples"></a>Exemples  
 L’exemple suivant crée un `Point` instance qui contient **Z** (élévation) et **M** les valeurs (mesure). `STAsText()`Sélectionne les valeurs WKT, (-122.34900 47.65100) ; `AsTextZM()` sélectionne les mêmes valeurs WKT et retourne également les valeurs de **Z** et **M**, ce qui (-122.34900 47.65100 10.3 12).  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('POINT(-122.34900 47.65100 10.3 12)', 4326);  
SELECT @g.STAsText();  
SELECT @g.AsTextZM();  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes étendues sur les Instances Geography](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)   
 [M &#40; Type de données geography &#41;](../../t-sql/spatial-geography/m-geography-data-type.md)   
 [Z &#40; Type de données geography &#41;](../../t-sql/spatial-geography/z-geography-data-type.md)  
  
  
