---
title: '&amp;(AND au niveau du bit) (Transact-SQL) | Documents Microsoft'
ms.custom: 
ms.date: 01/10/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|language-elements
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bitwise
- '&'
- '&_TSQL'
dev_langs: TSQL
helpviewer_keywords:
- AND, bitwise AND
- '& (bitwise AND)'
- bitwise AND (&)
ms.assetid: 20275755-4fa7-47b1-a9be-ac85606d63b0
caps.latest.revision: "42"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 0f81606a64480990a2f511a9820672c2cf1bb5c8
ms.sourcegitcommit: 6c54e67818ec7b0a2e3c1f6e8aca0fdf65e6625f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2018
---
# <a name="amp-bitwise-and-transact-sql"></a>&amp;(AND au niveau du bit) (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Effectue une opération AND logique au niveau du bit avec deux valeurs entières.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
expression & expression  
```  
  
## <a name="arguments"></a>Arguments  
 *expression*  
 Valide [expression](../../t-sql/language-elements/expressions-transact-sql.md) de n’importe quel type de données de la catégorie de type de données entier, ou le **bits**, ou **binaire** ou **varbinary** des types de données. *expression* est traité comme un nombre binaire pour l’opération au niveau du bit.  
  
> [!NOTE]  
>  Dans une opération au niveau du bit, seul *expression* peut être du type **binaire** ou **varbinary** type de données.  
  
## <a name="result-types"></a>Types des résultats  
 **int** si les valeurs d’entrée sont **int**.  
  
 **smallint** si les valeurs d’entrée sont **smallint**.  
  
 **tinyint** si les valeurs d’entrée sont **tinyint** ou **bits**.  
  
## <a name="remarks"></a>Notes  
 Le  **&**  opérateur au niveau du bit exécute un AND logique au niveau du bit entre les deux expressions, évaluant chaque bit pour les deux expressions correspondant. Dans le résultat, les bits prennent la valeur 1 si et seulement si les deux bits correspondants (pour la position en cours d'évaluation) dans les deux expressions d'entrées ont une valeur de 1 ; si tel n'est pas le cas, le bit résultant est mis à 0.  
  
 Si les expressions de gauche et droite ont des types de données entiers différents (par exemple, sur la gauche *expression* est **smallint** et du droit *expression* est **int**), l’argument du type de données plus petit est converti au type de données plus volumineux. Dans ce cas, le **smallint *** expression* est converti en un **int**.  
  
## <a name="examples"></a>Exemples  
 L’exemple suivant crée une table à l’aide de la **int** type pour stocker les valeurs de données et insère deux valeurs dans une ligne.  
  
```  
CREATE TABLE bitwise  
(   
a_int_value int NOT NULL,  
b_int_value int NOT NULL  
);  
GO  
INSERT bitwise VALUES (170, 75);  
GO  
```  
  
 Cette requête exécute le AND au niveau du bit entre les deux colonnes `a_int_value` et `b_int_value`.  
  
```  
SELECT a_int_value & b_int_value  
FROM bitwise;  
GO  
```  
  
 Voici l'ensemble de résultats obtenu :  
  
```  
-----------   
10            
  
(1 row(s) affected)  
```  
  
 La représentation binaire de 170 (`a_int_value` ou `A`) est `0000 0000 1010 1010`. La représentation binaire de 75 (`b_int_value` ou `B`) est `0000 0000 0100 1011`. L'exécution de l'opération AND au niveau du bit sur ces deux valeurs produit le résultat binaire `0000 0000 0000 1010`, qui est la valeur décimale 10.  
  
```  
(A & B)  
0000 0000 1010 1010  
0000 0000 0100 1011  
-------------------  
0000 0000 0000 1010  
```  
  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md)   
 [Operators &#40;Transact-SQL&#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [Opérateurs de bits &#40; Transact-SQL &#41;](../../t-sql/language-elements/bitwise-operators-transact-sql.md)   
 [&= &#40;Bitwise AND Assignment&#41; &#40;Transact-SQL&#41;](../../t-sql/language-elements/bitwise-and-equals-transact-sql.md)   
 [Compound, opérateurs &#40; Transact-SQL &#41;](../../t-sql/language-elements/compound-operators-transact-sql.md)  
  
  


