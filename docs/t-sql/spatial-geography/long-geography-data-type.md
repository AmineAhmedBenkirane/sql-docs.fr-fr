---
title: "Long (Type de données geography) | Documents Microsoft"
ms.custom: 
ms.date: 06/02/2016
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
- Long_TSQL
- Long
dev_langs: TSQL
helpviewer_keywords: Long method
ms.assetid: bedbeced-70b8-4569-84f3-f86bfb04ce50
caps.latest.revision: "14"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 5993c081a4366338981f7bf6f86c577a8e8a189e
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="long-geography-data-type"></a>Long (type de données geography)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  La propriété de longitude de le **geography** instance.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.Long  
```  
  
## <a name="return-value"></a>Valeur retournée  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type : **float**  
  
 Type CLR : **SqlDouble**  
  
## <a name="remarks"></a>Notes  
 Dans le modèle OpenGIS, durée pendant laquelle est défini uniquement sur **geography** instances composé d’un point unique. Cette propriété retourne NULL si **geography** instances contiennent plus d’un point unique. Cette propriété est précise et en lecture seule.  
  
## <a name="examples"></a>Exemples  
 Cet exemple crée un **Point** de l’instance et extrait la longitude du point.  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('POINT(-122.34900 47.65100)', 4326);  
SELECT @g.Long;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes étendues sur des instances geography](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)  
  
  
