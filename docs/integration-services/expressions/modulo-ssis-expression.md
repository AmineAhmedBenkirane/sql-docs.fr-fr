---
title: "(Modulo) (expression SSIS) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "% (opérateur modulo)"
  - "reste d'une division"
  - "modulo (opérateur) (%)"
ms.assetid: e2920821-2f5b-4c76-8db8-8b9eddf4606f
caps.latest.revision: 34
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 34
---
# (Modulo) (expression SSIS)
  Fournit le reste entier de la division de la première expression numérique par la deuxième.  
  
## Syntaxe  
  
```  
  
dividend % divisor  
  
```  
  
## Arguments  
 *dividend*  
 Expression numérique à diviser. *dividend* peut être n’importe quelle expression numérique valide. Pour plus d’informations, consultez [Types de données d’Integration Services](../../integration-services/data-flow/integration-services-data-types.md).  
  
 *divisor*  
 Expression numérique par laquelle diviser le dividende. *divisor* peut être n’importe quelle expression numérique valide, sauf zéro.  
  
## Types des résultats  
 Déterminés par les types de données des deux arguments. Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](../../integration-services/expressions/integration-services-data-types-in-expressions.md).  
  
## Notes  
 Les valeurs des deux expressions doivent s'évaluer à des types de données entier signé ou non signé.  
  
 Si l'un des opérandes est NULL, le résultat est NULL.  
  
 Un modulo égal à zéro n'est pas autorisé.  
  
## Exemples d'expressions  
 L'exemple suivant calcule le modulo à partir de deux littéraux numériques. Le résultat est 3.  
  
```  
42 % 13  
```  
  
 L’exemple suivant calcule le modulo à partir de la colonne **SalesQuota** et d’un littéral numérique.  
  
```  
SalesQuota % 12  
```  
  
 L’exemple suivant calcule le modulo à partir de deux variables numériques : **Sales$** et **Month**. La variable **Sales$** doit figurer entre crochets car elle contient le caractère « $ ». Pour plus d’informations, consultez [Identificateurs &#40;SSIS&#41;](../../integration-services/expressions/identifiers-ssis.md).  
  
```  
@[Sales$] % @Month  
```  
  
 L’exemple suivant utilise l’opérateur modulo pour déterminer si la valeur de la variable **Value** est paire ou impaire, et utilise l’opérateur conditionnel pour renvoyer une chaîne décrivant le résultat. Pour plus d’informations, consultez [? : &#40;Conditionnel&#41; &#40;expression SSIS&#41;](../../integration-services/expressions/conditional-ssis-expression.md).  
  
```  
@Value % 2 == 0? "even":"odd"  
```  
  
## Voir aussi  
 [Priorités et associativité des opérateurs](../../integration-services/expressions/operator-precedence-and-associativity.md)   
 [Opérateurs &#40;expression SSIS&#41;](../../integration-services/expressions/operators-ssis-expression.md)  
  
  