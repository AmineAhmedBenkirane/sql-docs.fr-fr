---
title: STDEVP (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/13/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- STDEVP
- STDEVP_TSQL
dev_langs: TSQL
helpviewer_keywords:
- STDEVP function [Transact-SQL]
- expressions [SQL Server], statistical standard deviation
- statistical standard deviation
ms.assetid: 29f2a906-d084-4464-abc3-4b275ed19442
caps.latest.revision: "45"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: af2c89686b804e263d0a7e576a3c91e926a65644
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="stdevp-transact-sql"></a>STDEVP (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Renvoie l'écart type de remplissage pour toutes les valeurs de l'expression spécifiée.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-- Syntax for SQL Server and Azure SQL Database  
  
STDEVP ( [ ALL | DISTINCT ] expression )   
   OVER ( [ partition_by_clause ] order_by_clause )    
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
-- Aggregate Function Syntax   
STDEVP ( [ ALL | DISTINCT ] expression )  
  
-- Analytic Function Syntax   
STDEVP (expression) OVER ( [ partition_by_clause ] order_by_clause)  
```  
  
## <a name="arguments"></a>Arguments  
 **ALL**  
 Applique la fonction à toutes les valeurs. ALL est l'argument par défaut.  
  
 DISTINCT  
 Spécifie que chaque valeur unique est prise en considération.  
  
 *expression*  
 Est une valeur numérique [expression](../../t-sql/language-elements/expressions-transact-sql.md). Les fonctions d'agrégation et les sous-requêtes ne sont pas autorisées. *expression* est une expression de la catégorie de type de données numérique exact ou approché, à l’exception de la **bits** type de données.  
  
 SUR **(** [ *partition_by_clause* ] *order_by_clause***)**  
 *partition_by_clause* divise le jeu de résultats généré par la clause FROM en partitions auxquelles la fonction est appliquée. S'il n'est pas spécifié, la fonction gère toutes les lignes du jeu de résultats de la requête en un seul groupe. *order_by_clause* détermine l’ordre logique dans lequel l’opération est effectuée. *order_by_clause* est requis. Pour plus d’informations, consultez [la Clause OVER &#40; Transact-SQL &#41; ](../../t-sql/queries/select-over-clause-transact-sql.md).  
  
## <a name="return-types"></a>Types de retour  
 **float**  
  
## <a name="remarks"></a>Notes  
 Si la fonction STDEVP est exécutée sur tous les éléments d'une instruction SELECT, chaque valeur du jeu de résultats est comprise dans le calcul. La fonction STDEVP ne peut être utilisée qu'avec des colonnes de type numérique. Les valeurs NULL sont ignorées.  
  
 STDEVP est une fonction déterministe lorsqu'elle est utilisée sans les clauses OVER et ORDER BY. Elle n'est pas déterministe avec les clauses OVER et ORDER BY. Pour plus d’informations, consultez [Fonctions déterministes et non déterministes](../../relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions.md).  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-using-stdevp"></a>R : utilisez la fonction ECARTYPEP  
 Dans l'exemple suivant, la procédure retourne l'écart type de remplissage pour toutes les valeurs de bonus de la table `SalesPerson` dans la base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].  
  
```  
SELECT STDEVP(Bonus)  
FROM Sales.SalesPerson;  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemples : [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="b-using-stdevp"></a>B : utilisez la fonction ECARTYPEP  
 L’exemple suivant retourne le `STDEVP` des valeurs de quota de ventes dans la table `dbo.FactSalesQuota`. La première colonne contient l’écart type de toutes les valeurs distinctes, et la deuxième colonne contient l’écart type de toutes les valeurs, y compris toutes les valeurs de doublons.  
  
```  
-- Uses AdventureWorks  
  
SELECT STDEVP(DISTINCT SalesAmountQuota)AS Distinct_Values, STDEVP(SalesAmountQuota) AS All_Values  
FROM dbo.FactSalesQuota;SELECT STDEVP(DISTINCT Quantity)AS Distinct_Values, STDEVP(Quantity) AS All_Values  
FROM ProductInventory;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
Distinct_Values   All_Values  
----------------  ----------------  
397676.79         397226.44
```  
  
### <a name="c-using-stdevp-with-over"></a>C. À l’aide de la fonction STDEVP OVER  
 L’exemple suivant retourne le `STDEVP` des valeurs de quota de ventes pour chaque trimestre de l’année civile. Notez que l'argument `ORDER BY` de la clause `OVER` détermine l'ordre des valeurs `STDEVP` tandis que l'argument `ORDER BY` de l'instruction `SELECT` détermine l'ordre de l'ensemble de résultats.  
  
```  
-- Uses AdventureWorks  
  
SELECT CalendarYear AS Year, CalendarQuarter AS Quarter, SalesAmountQuota AS SalesQuota,  
       STDEVP(SalesAmountQuota) OVER (ORDER BY CalendarYear, CalendarQuarter) AS StdDeviation  
FROM dbo.FactSalesQuota  
WHERE EmployeeKey = 272 AND CalendarYear = 2002  
ORDER BY CalendarQuarter;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
Year  Quarter  SalesQuota              StdDeviation  
----  -------  ----------------------  -------------------  
2002  1         91000.0000             0.00  
2002  2        140000.0000             24500.00  
2002  3         70000.0000             29329.55  
2002  4        154000.0000             34426.55
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions d’agrégation &#40; Transact-SQL &#41;](../../t-sql/functions/aggregate-functions-transact-sql.md)   
 [SUR la clause for &#40; Transact-SQL &#41;](../../t-sql/queries/select-over-clause-transact-sql.md)  
  
  

