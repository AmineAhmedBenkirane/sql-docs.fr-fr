---
title: "SUBSTRING (expression SSIS) | Microsoft Docs"
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
  - "SUBSTRING (fonction)"
  - "partie d'expression renvoyée [Integration Services]"
ms.assetid: 3a46748a-f5f8-4a6c-9108-673666754068
caps.latest.revision: 34
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 34
---
# SUBSTRING (expression SSIS)
  Renvoie la partie d'une expression de caractères qui commence à la position spécifiée et qui a la longueur spécifiée. Les paramètres *position* et *length* doivent correspondre à des entiers.  
  
## Syntaxe  
  
```  
  
SUBSTRING(character_expression, position, length)  
```  
  
## Arguments  
 *character_expression*  
 Expression de caractères à partir de laquelle doivent être extraits les caractères.  
  
 *position*  
 Entier précisant où commence sous-chaîne.  
  
 *length*  
 Entier exprimant, en nombre de caractères, la longueur de la sous-chaîne.  
  
## Types des résultats  
 DT_WSTR  
  
## Notes  
 SUBSTRING utilise un index de base un. Si *position* est 1, la sous-chaîne commence par le premier caractère de *character_expression*.  
  
 La fonction SUBSTRING n'est opérationnelle qu'avec le type de données DT_WSTR. Un argument *character_expression* représentant un littéral de chaîne ou une colonne de données du type de données DT_STR est implicitement converti dans le type de données DT_WSTR avant que la fonction SUBSTRING soit exécutée. Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR. Pour plus d’informations, consultez [Types de données d’Integration Services](../../integration-services/data-flow/integration-services-data-types.md) et [Cast &#40;expression SSIS&#41;](../../integration-services/expressions/cast-ssis-expression.md).  
  
 La fonction SUBSTRING renvoie un résultat NULL si l'argument est NULL.  
  
 Tous les arguments de l'expression peuvent utiliser des variables et des colonnes.  
  
 L'argument *length* peut être supérieur à la longueur de la chaîne. Dans ce cas, la fonction renvoie le reste de la chaîne.  
  
## Exemples d'expressions  
 L'exemple suivant renvoie deux caractères, à partir du quatrième caractère, d'un littéral de chaîne. Le résultat obtenu est « ph ».  
  
```  
SUBSTRING("elephant",4,2)  
```  
  
 L'exemple suivant renvoie le reste d'un littéral de chaîne, à partir du quatrième caractère. Le résultat obtenu est « phant ». Si l'argument *length* dépasse la longueur de la chaîne, cela ne constitue pas une erreur.  
  
```  
SUBSTRING ("elephant",4,50)  
```  
  
 L'exemple suivant renvoie la première lettre de la colonne **MiddleName** .  
  
```  
SUBSTRING(MiddleName,1,1)  
```  
  
 L'exemple suivant utilise des variables dans les arguments *position* et *length* . Si les variables **Start** et **Length** ont pour valeur respective 1 et 5, la fonction renvoie les cinq premiers caractères de la colonne **Name** .  
  
```  
SUBSTRING(Name,@Start,@Length)  
```  
  
 L'exemple suivant renvoie les quatre derniers caractères de la variable **PostalCode** , à partir du sixième caractère.  
  
```  
SUBSTRING (@PostalCode,6,4)  
```  
  
 L'exemple suivant renvoie une chaîne de longueur nulle d'un littéral de chaîne.  
  
```  
SUBSTRING ("Redmond",4,0)  
```  
  
## Voir aussi  
 [Fonctions &#40;expression SSIS&#41;](../../integration-services/expressions/functions-ssis-expression.md)  
  
  