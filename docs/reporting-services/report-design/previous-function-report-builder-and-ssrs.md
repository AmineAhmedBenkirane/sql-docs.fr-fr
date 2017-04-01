---
title: "Fonction Previous (G&#233;n&#233;rateur de rapports et SSRS) | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 403a9384-6ca4-42e8-97ca-ac3f6fe4316b
caps.latest.revision: 8
author: "maggiesMSFT"
ms.author: "maggies"
manager: "erikre"
---
# Fonction Previous (G&#233;n&#233;rateur de rapports et SSRS)
  Retourne la valeur ou la valeur d'agrégation spécifiée pour l'instance précédente d'un élément dans l'étendue spécifiée.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## Syntaxe  
  
```  
  
Previous(expression, scope)  
```  
  
#### Paramètres  
 *expression*  
 (**Variant** or **Binary**) Expression à utiliser pour identifier les données et pour laquelle récupérer la valeur précédente, par exemple `Fields!Fieldname.Value` ou `Sum(Fields!Fieldname.Value)`.  
  
 *scope*  
 (**Chaîne**) Facultatif. Nom d’un groupe ou d’une région de données, ou valeur Null (**Nothing** en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), qui spécifie l’étendue à partir de laquelle récupérer la valeur précédente spécifiée par *expression*.  
  
## Type de retour  
 Retourne une valeur **Variant** ou **Binary**.  
  
## Notes  
 La fonction **Previous** retourne la valeur précédente de l’expression évaluée dans l’étendue spécifiée après que cette dernière a été triée et filtrée correctement.  
  
 Si *expression* ne contient pas d’agrégat, la fonction **Previous** utilise par défaut l’étendue actuelle de l’élément de rapport.  
  
 Dans le groupe de détails, utilisez **Previous** pour spécifier la valeur d’une référence de champ dans l’instance précédente de la ligne de détails.  
  
> [!NOTE]  
>  La fonction **Previous** ne prend en charge que les références de champ dans le groupe de détails. Par exemple, dans une zone de texte du groupe de détails, `=Previous(Fields!Quantity.Value)` retourne les données du champ `Quantity` de la ligne précédente. Cette expression sur la première ligne retourne une valeur Null (**Nothing** en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).  
  
 Si *expression* contient une fonction d’agrégation qui utilise une étendue par défaut, **Previous** agrège les données de l’instance précédente de l’étendue spécifiée dans l’appel de la fonction d’agrégation.  
  
 Si *expression* contient une fonction d’agrégation qui spécifie une étendue autre que celle par défaut, le paramètre *scope* de la fonction **Previous** doit être une étendue contenante pour l’étendue spécifiée dans l’appel de la fonction d’agrégation.  
  
 Vous ne pouvez pas utiliser les fonctions **Level**, **InScope**, **Aggregate** et **Previous** dans le paramètre *expression*. La spécification du paramètre *recursive* pour une fonction d’agrégation n’est pas prise en charge.  
  
 Pour plus d’informations, consultez [Informations de référence sur les fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/aggregate-functions-reference-report-builder-and-ssrs.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/expression scope for totals, aggregates, and built-in collections.md).  
  
## Exemples  
  
### Description  
 L’exemple de code ci-dessous, quand il est placé sur la ligne de données par défaut d’une région de données, fournit la valeur du champ `LineTotal` de la ligne précédente.  
  
### Code  
  
```  
=Previous(Fields!LineTotal.Value)  
```  
  
### Description  
 L'exemple suivant montre une expression qui calcule la somme des ventes réalisées au cours d'un jour spécifique du mois et la valeur précédente pour le même jour du mois d'une année précédente. L’expression est ajoutée à une cellule d’une ligne qui appartient au groupe enfant `GroupbyDay`. Son groupe parent est `GroupbyMonth`, ayant lui-même le groupe parent `GroupbyYear`. L'expression affiche les résultats pour GroupbyDay (étendue par défaut), puis pour `GroupbyYear` (le parent du groupe parent `GroupbyMonth`).  
  
 Par exemple, pour une région de données avec un groupe parent nommé `Year`, son groupe enfant nommé `Month` et son groupe enfant nommé `Day` (3 niveaux imbriqués). L’expression `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` d’une ligne associée au groupe `Day` retourne la valeur des ventes réalisées le même jour du même mois de l’année précédente.  
  
### Code  
  
```  
=Sum(Fields!Sales.Value) & " " & Previous(Sum(Fields!Sales.Value,"GroupbyDay"),"GroupbyYear")  
```  
  
## Voir aussi  
 [Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](../../reporting-services/report-design/expression-uses-in-reports-report-builder-and-ssrs.md)   
 [Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/expression-examples-report-builder-and-ssrs.md)   
 [Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/data-types-in-expressions-report-builder-and-ssrs.md)   
 [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/expression scope for totals, aggregates, and built-in collections.md)  
  
  