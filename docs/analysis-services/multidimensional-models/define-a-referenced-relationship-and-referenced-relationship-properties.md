---
title: "D&#233;finir une relation r&#233;f&#233;renc&#233;e et des propri&#233;t&#233;s de relation r&#233;f&#233;renc&#233;e | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
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
  - "relation de dimension de référence"
  - "relations [Analysis Services], dimensions référencées"
ms.assetid: 5bb44b41-635b-4398-8fe9-0bfbb142553e
caps.latest.revision: 13
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
caps.handback.revision: 13
---
# D&#233;finir une relation r&#233;f&#233;renc&#233;e et des propri&#233;t&#233;s de relation r&#233;f&#233;renc&#233;e
  Vous pouvez définir une relation de dimension de référence sous l’onglet **Utilisation de la dimension** du Concepteur de cube. Pour définir la relation de dimension de référence, spécifiez les éléments suivants :  
  
-   La dimension intermédiaire à joindre. Il peut s'agir d'une dimension régulière ou d'une autre dimension de référence.  
  
-   Attribut de dimension de référence qui définit le niveau le plus bas où la dimension est disponible pour l'agrégation par rapport au groupe de mesures.  
  
-   L'attribut (clé étrangère) dans la dimension intermédiaire qui correspond à l'attribut de dimension de référence.  
  
 Notez que la colonne qui lie la dimension de référence à la table de faits, qui est généralement l'attribut clé dans la dimension de référence, doit aussi être définie en tant qu'attribut dans la dimension intermédiaire. Lorsque vous créez une chaîne de dimensions de référence, commencez par créer la relation régulière entre la première dimension de la chaîne et le groupe de mesures. Créez ensuite chaque relation référencée additionnelle dans l'ordre. Une relation référencée ne peut être créée qu'avec une dimension ayant une relation existante avec le groupe de mesures.  
  
 Quand vous créez une relation de dimension de référence, le lien d'attribut de dimension est matérialisé par défaut. La matérialisation d'un lien d'attribut de dimension fait que la valeur du lien entre la table de faits et la dimension de référence pour chaque ligne est matérialisée, ou stockée, dans la structure MOLAP de la dimension lors du traitement. Ceci a un effet mineur sur les performances du traitement et sur l'espace de stockage nécessaire, mais permet d'accroître les performances des requêtes.  
  
 Dans une dimension de référence, la granularité est spécifiée en identifiant l'attribut qui définit la relation entre une dimension de référence et le groupe de mesures correspondant à la table principale de la dimension. Lorsque plusieurs dimensions de référence sont chaînées ensemble, les références définissent la relation entre la dimension la plus éloignée et le groupe de mesures.  
  
  