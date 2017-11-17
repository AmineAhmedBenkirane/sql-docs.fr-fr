---
title: "EnvelopeAggregate (Type de données geography) | Documents Microsoft"
ms.custom: 
ms.date: 07/30/2017
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
- EnvelopeAggregate_TSQL
- EnvelopeAggregate
dev_langs:
- TSQL
helpviewer_keywords:
- EnvelopeAggregate method (geography)
ms.assetid: 4947797f-edb8-490f-beca-37df9ec06954
caps.latest.revision: 11
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: e9d50e15f644a5662af2eead65d29447af8493a9
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="envelopeaggregate-geography-data-type"></a>EnvelopeAggregate (type de données geography)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

Retourne un objet englobant pour un ensemble donné de **geography** objets. Résultant **geography** objet contient plusieurs segments d’arc de cercle.
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
EnvelopeAggregate ( geography_operand )  
```  
  
## <a name="arguments"></a>Arguments  
 *geography_operand*  
 Est un **geography** colonne de table de type qui conserve le jeu de **geography** opération d’agrégation des objets sur lesquels effectuer une enveloppe.  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **geography**  
  
## <a name="remarks"></a>Notes  
 A **FullGlobe** est retourné lorsque l’objet englobant obtenu est plus grand qu’un hémisphère. Cette méthode n'est pas précise.  
  
 Méthode renvoie **null** si l’entrée a des SRID différents. Consultez [identificateurs de référence spatiale &#40; SRID &#41; ](../../relational-databases/spatial/spatial-reference-identifiers-srids.md).  
  
 Méthode ignore **null** entrées.  
  
> [!NOTE]  
>  Méthode renvoie **null** si toutes les valeurs entrées sont **null**.  
  
## <a name="examples"></a>Exemples  
 L’exemple suivant effectue une `EnvelopeAggregate` sur un ensemble de **geography** points d’emplacement au sein d’une ville.  
  
 ```
 USE AdventureWorks2012  
 GO  
 SELECT City,  
 geography::EnvelopeAggregate(SpatialLocation) AS SpatialLocation  
 FROM Person.Address  
 WHERE PostalCode LIKE('981%')  
 GROUP BY City;
 ```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes géographiques statiques étendues](../../t-sql/spatial-geography/extended-static-geography-methods.md)  
  
  

