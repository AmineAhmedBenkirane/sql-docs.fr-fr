---
title: ALIMENTATION (Transact-SQL) | Documents Microsoft
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
- POWER_TSQL
- POWER
dev_langs: TSQL
helpviewer_keywords: POWER function
ms.assetid: 0fd34494-90b9-4559-8011-a8c1b9f40239
caps.latest.revision: "41"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 749be659f84e6f2bad04863477bbcd5923e8a216
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="power-transact-sql"></a>POWER (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retourne la valeur de l'expression spécifiée à la puissance indiquée.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
POWER ( float_expression , y )  
```  
  
## <a name="arguments"></a>Arguments  
 *expression*  
 Est un [expression](../../t-sql/language-elements/expressions-transact-sql.md) de type **float** ou d’un type qui peut être implicitement converti en **float**.  
  
 *y*  
 La puissance à laquelle élever *expression*. *y* peut être une expression de la catégorie de type de données numérique exact ou approché, à l’exception de la **bits** type de données.  
  
## <a name="return-types"></a>Types de retour  
 Retourne le même type que celui envoyé dans *expression*. Par exemple, si un **décimal**(2,0) est envoyé sous la forme *expression*, le résultat retourné est **décimal**(2,0).  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-using-power-to-return-the-cube-of-a-number"></a>A. Utilisation de la fonction POWER pour retourner le cube d'un nombre  
 L'exemple suivant montre comment élever un nombre à la puissance 3 (le cube du nombre).  
  
```  
DECLARE @input1 float;  
DECLARE @input2 float;  
SET @input1= 2;  
SET @input2 = 2.5;  
SELECT POWER(@input1, 3) AS Result1, POWER(@input2, 3) AS Result2;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
Result1                Result2  
---------------------- ----------------------  
8                      15.625  
  
(1 row(s) affected)  
```  
  
### <a name="b-using-power-to-show-results-of-data-type-conversion"></a>B. Utilisation de la fonction POWER pour afficher les résultats de la conversion du type de données  
 L’exemple suivant montre comment la *expression* conserve le type de données qui peut retourner des résultats inattendus.  
  
```  
SELECT   
POWER(CAST(2.0 AS float), -100.0) AS FloatResult,  
POWER(2, -100.0) AS IntegerResult,  
POWER(CAST(2.0 AS int), -100.0) AS IntegerResult,  
POWER(2.0, -100.0) AS Decimal1Result,  
POWER(2.00, -100.0) AS Decimal2Result,  
POWER(CAST(2.0 AS decimal(5,2)), -100.0) AS Decimal2Result;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
FloatResult            IntegerResult IntegerResult Decimal1Result Decimal2Result Decimal2Result  
---------------------- ------------- ------------- -------------- -------------- --------------  
7.88860905221012E-31   0             0             0.0            0.00           0.00  
```  
  
### <a name="c-using-power"></a>C. Utilisation de POWER  
 Cet exemple retourne des résultats `POWER` pour `2`.  
  
```  
DECLARE @value int, @counter int;  
SET @value = 2;  
SET @counter = 1;  
  
WHILE @counter < 5  
   BEGIN  
      SELECT POWER(@value, @counter)  
      SET NOCOUNT ON  
      SET @counter = @counter + 1  
      SET NOCOUNT OFF  
   END;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
-----------   
2             
  
(1 row(s) affected)  
  
-----------   
4             
  
(1 row(s) affected)  
  
-----------   
8             
  
(1 row(s) affected)  
  
-----------   
16            
  
(1 row(s) affected)  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemples : [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="d-using-power-to-return-the-cube-of-a-number"></a>D: à l’aide de POWER pour retourner le cube d’un nombre  
 L’exemple suivant montre retourne `POWER` les résultats pour `2.0` à la puissance 3.  
  
```  
SELECT POWER(2.0, 3);  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
------------ 
8.0
```  
  
## <a name="see-also"></a>Voir aussi  
 [Decimal et numeric &#40; Transact-SQL &#41;](../../t-sql/data-types/decimal-and-numeric-transact-sql.md)   
 [float et real &#40; Transact-SQL &#41;](../../t-sql/data-types/float-and-real-transact-sql.md)   
 [int, bigint, smallint, tinyint et #40 ; Transact-SQL &#41;](../../t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql.md)   
 [Fonctions mathématiques &#40; Transact-SQL &#41;](../../t-sql/functions/mathematical-functions-transact-sql.md)   
 [Money et smallmoney &#40; Transact-SQL &#41;](../../t-sql/data-types/money-and-smallmoney-transact-sql.md)  
  
  

