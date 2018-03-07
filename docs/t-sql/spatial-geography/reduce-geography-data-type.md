---
title: "Réduire (Type de données geography) | Documents Microsoft"
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
- Reduce_TSQL
- Reduce
dev_langs:
- TSQL
helpviewer_keywords:
- Reduce method
ms.assetid: c5dfa8c1-6764-41d8-9150-f3cb30633d3e
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a4ac2e0f44ee4d6361f0f91c47f4472de7c23756
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="reduce-geography-data-type-"></a>Reduce (type de données geography)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retourne une approximation de la donnée **geography** instance générés par l’exécution de l’algorithme de Douglas-Peucker sur l’instance avec la tolérance donnée.  
  
 Cela **geography** prend en charge de la méthode de type de données **FullGlobe** instances ou les instances spatiales qui sont plus grandes qu’un hémisphère.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.Reduce ( tolerance )  
```  
  
## <a name="arguments"></a>Arguments  
  
|||  
|-|-|  
|Terme|Définition|  
|*tolerance*|Est une valeur de type **float**. *la tolérance de panne* est la tolérance à entrer à l’algorithme de Douglas-Peucker. *la tolérance de panne* doit être un nombre positif.|  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **geography**  
  
 Type de retour CLR : **SqlGeography**  
  
## <a name="remarks"></a>Notes  
 Pour les types de collection, cet algorithme fonctionne indépendamment sur chaque **geography** contenus dans l’instance. Cet algorithme ne modifie pas **Point** instances.  
  
 Cette méthode tente de conserver les points de terminaison de **LineString** instances, mais risque d’échouer afin de préserver un résultat valide.  
  
 Si `Reduce()` est appelée avec une valeur négative, cette méthode produira un **ArgumentException**. Les tolérances utilisées dans `Reduce()` doivent être des nombres positifs.  
  
 L’algorithme de Douglas-Peucker fonctionne sur chaque courbe ou anneau dans le **geography** instance en supprimant tous les points à l’exception du point de départ et le point de terminaison. Chaque point supprimé est ensuite rajouté, en commençant par le point excentré le plus lointain, aucun point ne soit plus de *la tolérance de panne* à partir du résultat. Le résultat est ensuite rendu valide si nécessaire, dans la mesure où un résultat valide est garanti.  
  
 Dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], cette méthode a été étendue aux **FullGlobe** instances.  
  
 Cette méthode n'est pas précise.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant crée une instance `LineString` et utilise `Reduce()` afin de simplifier l'instance.  
  
```  
DECLARE @g geography = 'LineString(120 45, 120.1 45.1, 199.9 45.2, 120 46)'  
SELECT @g.Reduce(10000).ToString()  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes étendues sur des instances geography](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)  
  
  
