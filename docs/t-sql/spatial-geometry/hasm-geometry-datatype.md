---
title: "HasM (type de données de géométrie) | Documents Microsoft"
ms.custom: 
ms.date: 05/05/2017
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
helpviewer_keywords: HasM geometry
ms.assetid: 15540837-c4bf-4d18-b380-13ae31f3226f
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 00033a151755f0dad6f2551db53ebba0e5e6d077
ms.sourcegitcommit: 6c54e67818ec7b0a2e3c1f6e8aca0fdf65e6625f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2018
---
# <a name="hasm-geometry-datatype"></a>HasM (type de données geometry)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  Retourne 1 (true) si un objet spatial contient au moins une valeur M ; sinon retourne 0 (false).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.HasM  
```  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **bits**  
  
 Type de retour CLR : **booléenne**  
  
## <a name="remarks"></a>Notes  
  
## <a name="examples"></a>Exemples  
  
```sql  
DECLARE @p GEOMETRY = 'Point(1 1 1 1)'  
SELECT @p.HasM   
--Returns: 1 (true)  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes étendues sur les Instances géométriques](../../t-sql/spatial-geometry/extended-methods-on-geometry-instances.md)   
 [M &#40; Type de données geometry &#41;](../../t-sql/spatial-geometry/m-geometry-data-type.md)  
  
  
