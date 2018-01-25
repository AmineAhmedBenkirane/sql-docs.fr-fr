---
title: "STWithin (Type de données geography) | Documents Microsoft"
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
dev_langs: TSQL
helpviewer_keywords: STWithin method (geography)
ms.assetid: 6fc745cc-7976-418a-a89a-c267e64ab3a2
caps.latest.revision: "7"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 2955f1196020a7df8ba60cfe0e1a24b6a6e7ddcf
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="stwithin-geography-data-type"></a>STWithin (type de données geography)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  Retourne 1 si une **geography** instance est SPATIALEMENT dans une autre **geography** instance ; sinon, retourne 0.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.STWithin ( other_geography )  
```  
  
## <a name="arguments"></a>Arguments  
 *other_geography*  
 Une autre **geography** instance à comparer à l’instance sur laquelle `STWithin()` est appelé.  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **bits**  
  
 Type de retour CLR : **SqlBoolean**  
  
## <a name="remarks"></a>Notes  
 Cette méthode retourne toujours null si l’ID de référence spatiale (SRID) de la **geography** instances ne correspondent pas.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant utilise `STWithin()` pour tester deux instances `geography` pour voir si la première instance est complètement dans la deuxième instance.  
  
```  
DECLARE @g geography;  
DECLARE @h geography;  
SET @g = geography::Parse('POLYGON ((-120.533 46.566, -118.283 46.1, -122.3 47.45, -120.533 46.566))');  
SET @h = geography::Parse('CURVEPOLYGON (COMPOUNDCURVE (CIRCULARSTRING (-122.200928 47.454094, -122.810669 47.00648, -122.942505 46.687131, -121.14624 45.786679, -119.119263 46.183634), (-119.119263 46.183634, -119.273071 47.107523), CIRCULARSTRING (-119.273071 47.107523, -120.640869 47.569114, -122.200928 47.454094)))');  
SELECT @g.STWithin(@h);  
```  
  
  
