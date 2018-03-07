---
title: "Priorité des opérateurs (Transact-SQL) | Documents Microsoft"
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|language-elements
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- operators [Transact-SQL], precedence
- operator precedence [Transact-SQL]
- order of operator execution [Transact-SQL]
- precedence [SQL Server], operators
ms.assetid: f04d2439-6fff-4e4c-801f-cc62faef510a
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: c9de4447c5918edbc33ec67c783272f724883e81
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="operator-precedence-transact-sql"></a>Priorités des opérateurs (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Lorsqu'une expression complexe comporte plusieurs opérateurs, les priorités des opérateurs déterminent l'ordre d'exécution des opérations. Cet ordre peut affecter considérablement la valeur résultante.  
  
 L'ordre de priorité des opérateurs est indiqué dans le tableau suivant. Un opérateur de priorité élevée est évalué avant un opérateur de priorité basse.  
  
|Niveau|Opérateurs|  
|-----------|---------------|  
|1|~ (NOT au niveau du bit)|  
|2|* (Multiplication), / (Division), % (modulo)|  
|3|+ (Positif), - (négatif), + (Addition), (+ concaténation),-(soustraction), & (AND au niveau du bit), ^ (opérateur de bits OR exclusif), &#124; (OR au niveau du bit)|  
|4|=, >, \<, > =, < =, <>, ! =, ! >, ! < (opérateurs de comparaison)|  
|5|NOT|  
|6|AND|  
|7|ALL, ANY, BETWEEN, IN, LIKE, OR, SOME|  
|8|= (Affectation)|  
  
 Lorsque deux opérateurs dans une expression ont le même niveau de priorité, ils sont évalués de gauche à droite en fonction de leur position dans l'expression. Par exemple, dans l'expression utilisée dans l'instruction `SET`, l'opérateur de soustraction est évalué avant l'opérateur d'addition.  
  
```  
DECLARE @MyNumber int;  
SET @MyNumber = 4 - 2 + 27;  
-- Evaluates to 2 + 27 which yields an expression result of 29.  
SELECT @MyNumber;  
```  
  
 Utilisez des parenthèses pour modifier la priorité habituelle des opérateurs dans une expression. Tout ce qui se trouve entre parenthèses est évalué en premier pour produire une seule valeur, qui est ensuite utilisée par un opérateur en dehors des parenthèses.  
  
 Par exemple, dans l'expression utilisée dans l'instruction `SET`, l'opérateur de multiplication est prioritaire par rapport à l'opérateur d'addition. Par conséquent, il est évalué en premier ; le résultat de l'expression est `13`.  
  
```  
DECLARE @MyNumber int;  
SET @MyNumber = 2 * 4 + 5;  
-- Evaluates to 8 + 5 which yields an expression result of 13.  
SELECT @MyNumber;  
```  
  
 Dans l'expression utilisée dans l'instruction `SET` suivante, les parenthèses font que l'addition est effectuée en premier. Le résultat de l'expression est `18`.  
  
```  
DECLARE @MyNumber int;  
SET @MyNumber = 2 * (4 + 5);  
-- Evaluates to 2 * 9 which yields an expression result of 18.  
SELECT @MyNumber;  
```  
  
 Si une expression comporte des parenthèses imbriquées, c'est l'expression la plus imbriquée qui est évaluée en premier. L'exemple suivant contient des parenthèses imbriquées ; l'expression `5 - 3` se trouve dans les parenthèses les plus imbriquées. Le résultat de cette expression est `2`. Ensuite, l'opérateur d'addition (`+`) ajoute ce résultat à `4`. Le résultat est alors `6`. Enfin, la valeur `6` est multipliée par `2`, ce qui produit le résultat `12` pour l'expression.  
  
```  
DECLARE @MyNumber int;  
SET @MyNumber = 2 * (4 + (5 - 3) );  
-- Evaluates to 2 * (4 + 2) which then evaluates to 2 * 6, and   
-- yields an expression result of 12.  
SELECT @MyNumber;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs logiques &#40; Transact-SQL &#41;](../../t-sql/language-elements/logical-operators-transact-sql.md)   
 [Operators &#40;Transact-SQL&#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [Fonctions intégrées &#40;Transact-SQL&#41;](~/t-sql/functions/functions.md)  
  
  
