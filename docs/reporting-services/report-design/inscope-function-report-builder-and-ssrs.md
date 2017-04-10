---
title: "Fonction InScope (G&#233;n&#233;rateur de rapports et SSRS) | Microsoft Docs"
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
ms.assetid: a8cd209a-e5d3-4dce-ab2d-f271f6c54955
caps.latest.revision: 7
author: "maggiesMSFT"
ms.author: "maggies"
manager: "erikre"
---
# Fonction InScope (G&#233;n&#233;rateur de rapports et SSRS)
  Indique si l'instance actuelle d'un élément se trouve dans l'étendue spécifiée.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## Syntaxe  
  
```  
InScope(scope)  
```  
  
#### Paramètres  
 *portée*  
 (**Chaîne**) Nom d’un dataset, d’une région de données ou d’un groupe qui spécifie une étendue.  
  
## Type de retour  
 Retourne une valeur **booléenne**.  
  
## Notes  
 La fonction **InScope** teste l’étendue de l’instance actuelle d’un élément de rapport pour l’appartenance à l’étendue spécifiée par le paramètre *scope*.  
  
 *Scope* ne peut pas être une expression.  
  
 En règle générale, la fonction **InScope** est utilisée dans les régions de données avec définition d’étendue dynamique. Ainsi, la fonction **InScope** peut être utilisée dans un lien d’extraction situé dans les cellules d’une région de données pour fournir un autre nom de rapport et des jeux de paramètres différents en fonction de la cellule sur laquelle l’utilisateur clique. En voici un exemple :  
  
-   L’expression suivante, utilisée comme nom de rapport dans un lien d’extraction, ouvre le rapport `ProductDetail` si l’utilisateur clique sur une cellule située dans le groupe `Month` et le rapport `ProductSummary` s’il clique sur une autre cellule.  
  
    ```  
    =Iif(InScope("Month"), "ProductDetail", "ProductSummary")  
    ```  
  
-   L’expression suivante, utilisée dans la propriété **Omit** d’un paramètre de rapport d’extraction, passe le paramètre au rapport cible uniquement si la cellule sur laquelle l’utilisateur clique se trouve dans le groupe `Product`.  
  
    ```  
    =Not(InScope("Product"))  
    ```  
  
 Pour plus d’informations, consultez [Informations de référence sur les fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/aggregate-functions-reference-report-builder-and-ssrs.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/expression scope for totals, aggregates, and built-in collections.md).  
  
## Exemple  
 L'exemple de code ci-dessous indique si l'instance actuelle de l'élément se trouve dans l'étendue du groupe, de la région de données ou du dataset `Product`.  
  
```  
=InScope("Product")  
```  
  
## Voir aussi  
 [Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](../../reporting-services/report-design/expression-uses-in-reports-report-builder-and-ssrs.md)   
 [Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/expression-examples-report-builder-and-ssrs.md)   
 [Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/data-types-in-expressions-report-builder-and-ssrs.md)   
 [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/expression scope for totals, aggregates, and built-in collections.md)  
  
  