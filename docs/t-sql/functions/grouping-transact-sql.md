---
title: REGROUPEMENT (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- GROUPING
- GROUPING_TSQL
dev_langs: TSQL
helpviewer_keywords:
- null values [SQL Server], GROUPING function
- grouping columns
- ROLLUP operator
- GROUP BY clause, GROUPING function
- GROUPING function
- CUBE operator
ms.assetid: 4efa3868-1fc4-4626-8fb1-e863cc03e422
caps.latest.revision: "32"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
ms.openlocfilehash: cb9c9e7f4e5fe4a82c6f7a451614fde82e730e08
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="grouping-transact-sql"></a>GROUPING (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Indique si une expression de colonne spécifiée dans une liste GROUPE PAR est regroupée ou non. GROUPING retourne 1 pour agrégation ou 0 pour aucune agrégation dans le jeu de résultats. GROUPING peut être utilisé uniquement dans l’instruction SELECT \<sélectionnez > répertorier, HAVING et les clauses ORDER BY Lorsque GROUP BY est spécifié.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
GROUPING ( <column_expression> )  
```  
  
## <a name="arguments"></a>Arguments  
 \<column_expression >  
 Est une colonne ou une expression qui contient une colonne dans un [GROUP BY](../../t-sql/queries/select-group-by-transact-sql.md) clause.  
  
## <a name="return-types"></a>Types de retour  
 **tinyint**  
  
## <a name="remarks"></a>Notes  
 GROUPING sert à distinguer les valeurs NULL retournées par CUBE, ROLLUP ou GROUPING SETS des valeurs NULL standard. La valeur NULL retournée comme résultat d'une opération CUBE, ROLLUP ou GROUPING SETS est une utilisation spéciale de NULL. Elle agit comme un espace réservé d'une colonne dans l'ensemble de résultats et signifie « tout ».  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant regroupe `SalesQuota` et totalise les montants `SaleYTD` dans la base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)]. La fonction `GROUPING` est appliquée à la colonne `SalesQuota`.  
  
```  
SELECT SalesQuota, SUM(SalesYTD) 'TotalSalesYTD', GROUPING(SalesQuota) AS 'Grouping'  
FROM Sales.SalesPerson  
GROUP BY SalesQuota WITH ROLLUP;  
GO  
```  
  
 L'ensemble de résultats indique deux valeurs NULL sous `SalesQuota`. La première `NULL` représente le groupe des valeurs NULL de cette colonne dans la table. La seconde `NULL` se trouve dans la ligne résumée ajoutée par l'opération ROLLUP. La ligne résumée indique le `TotalSalesYTD` quantités pour tous les `SalesQuota` regroupe et est indiqué par `1` dans les `Grouping` colonne.  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
 SalesQuota     TotalSalesYTD       Grouping  
------------   -----------------   --------  
NULL           1533087.5999          0  
250000.00      33461260.59           0  
300000.00      9299677.9445          0  
NULL           44294026.1344         1  

(4 row(s) affected)
```  
  
## <a name="see-also"></a>Voir aussi  
 [GROUPING_ID &#40; Transact-SQL &#41;](../../t-sql/functions/grouping-id-transact-sql.md)   
 [GROUP BY &#40; Transact-SQL &#41;](../../t-sql/queries/select-group-by-transact-sql.md)  
  
  
