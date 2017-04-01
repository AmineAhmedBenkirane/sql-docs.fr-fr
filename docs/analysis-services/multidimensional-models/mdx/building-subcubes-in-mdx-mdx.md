---
title: "Cr&#233;ation de sous-cubes &#224; l&#39;aide de la syntaxe MDX (MDX) | Microsoft Docs"
ms.custom: ""
ms.date: "03/13/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "analysis-services/multidimensional-tabular"
  - "analysis-services/data-mining"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "requêtes [MDX], sous-cubes"
  - "sous-cubes [MDX]"
  - "filtres [MDX]"
  - "MDX [Analysis Services], sous-cubes"
  - "expressions multidimensionnelles [Analysis Services], sous-cubes"
  - "instruction CREATE SUBCUBE"
ms.assetid: 5403a62b-99ac-4d83-b02a-89bf78bf0f46
caps.latest.revision: 31
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
caps.handback.revision: 31
---
# Cr&#233;ation de sous-cubes &#224; l&#39;aide de la syntaxe MDX (MDX)
  Un sous-cube est un sous-jeu d'un cube représentant une vue filtrée des données sous-jacentes. En limitant le cube à un sous-cube, vous pouvez améliorer les performances des requêtes.  
  
 Pour définir un sous-cube, vous devez utiliser l’instruction [CREATE SUBCUBE](../Topic/CREATE%20SUBCUBE%20Statement%20\(MDX\).md), comme décrit dans cette rubrique.  
  
## Syntaxe CREATE SUBCUBE  
 Utilisez la syntaxe suivante pour créer un sous-cube :  
  
```  
CREATE SUBCUBE Subcube_Identifier AS Subcube_Expression  
```  
  
 La syntaxe CREATE SUBCUBE est relativement simple. Le paramètre *Subcube_Identifier* identifie le cube sur lequel doit se baser le sous-cube. Le paramètre *Subcube_Expression* sélectionne la partie du cube qui deviendra le sous-cube.  
  
 Une fois le sous-cube créé, il devient le contexte de toutes les requêtes MDX jusqu’à la fermeture de la session ou l’exécution de l’instruction [DROP SUBCUBE](../Topic/DROP%20SUBCUBE%20Statement%20\(MDX\).md).  
  
### Éléments contenus dans un sous-cube  
 Même si l'instruction CREATE SUBCUBE est relativement simple à utiliser, l'instruction proprement dite n'indique pas explicitement tous les membres qui font partie d'un sous-cube. Lors de la définition d'un sous-cube, les règles suivantes s'appliquent :  
  
-   Si vous incluez le membre **(All)** d’une hiérarchie, vous incluez tous les membres qu’elle contient.  
  
-   Si vous incluez un membre, vous incluez également ses ascendants et ses descendants.  
  
-   Si vous incluez tous les membres d'un niveau, vous incluez tous les membres de la hiérarchie. Les membres des autres hiérarchies seront exclus s'ils ne possèdent pas de membre de ce niveau (par exemple, une hiérarchie déséquilibrée telle qu'une ville qui ne contient aucun client).  
  
-   Un sous-cube contient toujours tous les membres **(All)** du cube.  
  
 En outre, les valeurs d'agrégation contenues dans le sous-cube sont totalisées visuellement. Par exemple, un sous-cube contient `USA`, `WA` et `OR`. La valeur d'agrégation de `USA` sera la somme de `{WA,OR}`, car `WA` et `OR` sont les seuls États définis par le sous-cube. Tous les autres États seront ignorés.  
  
 Par ailleurs, les références explicites à des cellules situées en dehors du sous-cube retournent des valeurs évaluées dans le contexte de l'intégralité du cube. Supposons que vous créez un sous-cube limité à l'année en cours. Ensuite, vous utilisez la fonction [ParallelPeriod](../../../mdx/parallelperiod-mdx.md) pour comparer l’année en cours à l’année précédente. La différence entre les valeurs est retournée, même si la valeur de l'année précédente est située à l'extérieur du sous-cube.  
  
 Pour terminer, si le contexte original n'est pas remplacé, les fonctions de jeu évaluées dans une sous-sélection sont évaluées dans le contexte de celle-ci. Si ce contexte est remplacé, les fonctions de jeu sont évaluées dans le contexte de l'intégralité du cube.  
  
## Exemple de syntaxe CREATE SUBCUBE  
 L'exemple suivant crée un sous-cube qui limite le cube Budget aux comptes 4200 et 4300 uniquement :  
  
 `CREATE SUBCUBE Budget AS SELECT {[Account].[Account].&[4200], [Account].[Account].&[4300] } ON 0 FROM Budget`  
  
 Lorsque vous avez créé un sous-cube pour la session, toutes les requêtes suivantes sont exécutées sur celui-ci plutôt que sur l'intégralité du cube. Vous pouvez par exemple exécuter la requête suivante. Elle ne retourne que les membres des comptes 4200 et 4300.  
  
 `SELECT [Account].[Account].Members ON 0, Measures.Members ON 1 FROM Budget`  
  
## Voir aussi  
 [Définition d’un contexte de cube dans une requête &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/establishing-cube-context-in-a-query-mdx.md)   
 [Principes de base des requêtes MDX &#40;Analysis Services&#41;](../../../analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services.md)  
  
  