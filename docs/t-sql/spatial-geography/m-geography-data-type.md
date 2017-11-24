---
title: "M (Type de données geography) | Documents Microsoft"
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
- M (geography Data Type)
- M_TSQL
dev_langs: TSQL
helpviewer_keywords: M method
ms.assetid: cdba04f0-4e17-48f6-bafb-b1f918c5a501
caps.latest.revision: "14"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: df8a2eb38891ba584d6ffee666b4df5312996b44
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="m-geography-data-type"></a>M (type de données geography)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Le **M** valeur (mesure) de le **geography** instance. La sémantique de la valeur de mesure est définie par l'utilisateur, mais décrit en général la distance le long d'un linestring. Par exemple, la valeur de mesure pourrait être utilisée pour effectuer le suivi de bornes kilométriques le long d'une route.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.M  
```  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type : **float**  
  
 Type CLR : **SqlDouble**  
  
## <a name="remarks"></a>Notes  
 La valeur de cette propriété a la valeur null si le **geography** instance n’est pas un **Point**, ainsi que pour les **Point** de l’instance pour laquelle il n’est pas définie.  
  
 Cette propriété est en lecture seule.  
  
 Les valeurs de M ne sont pas utilisées dans aucun calcul effectué par la bibliothèque et ne sont reportées dans aucun calcul de bibliothèque.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant crée une instance `Point` avec des valeurs Z (élévation) et M (mesure) et utilise `M` pour extraire la valeur `M` de l'instance.  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('POINT(-122.34900 47.65100 10.3 12)', 4326);  
SELECT @g.M;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes étendues sur les Instances Geography](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)   
 [Z &#40; Type de données geography &#41;](../../t-sql/spatial-geography/z-geography-data-type.md)  
  
  
