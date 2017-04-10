---
title: "Cr&#233;er des requ&#234;tes d&#39;extraction &#224; l&#39;aide de DMX | Microsoft Docs"
ms.custom: ""
ms.date: "03/06/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "analysis-services/data-mining"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 42c896ee-e5ee-4017-b66e-31d1fe66d369
caps.latest.revision: 5
author: "Minewiskan"
ms.author: "owend"
manager: "jhubbard"
caps.handback.revision: 5
---
# Cr&#233;er des requ&#234;tes d&#39;extraction &#224; l&#39;aide de DMX
  Pour tous les modèles qui prennent en charge l'extraction, vous pouvez récupérer les données de cas et les données de structure en créant une requête DMX dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou dans tout autre client qui prend en charge DMX.  
  
> [!WARNING]  
>  Pour afficher les données, l'extraction doit avoir été activée, et vous devez disposer des autorisations nécessaires.  
  
## Spécification des options d'extraction  
 La syntaxe générale pour extraire les cas de modèles et les cas de structure est la suivante :  
  
```  
SELECT <model column list>, StructureColumn('<structure column name') FROM <modelname>.CASES  
```  
  
 Pour plus d’informations sur l’utilisation de requêtes DMX pour retourner des données de cas, consultez [SELECT FROM &#60;modèle&#62;.CASES &#40;DMX&#41;](../Topic/SELECT%20FROM%20%3Cmodel%3E.CASES%20\(DMX\).md) et [SELECT FROM &#60;structure&#62;.CASES](../Topic/SELECT%20FROM%20%3Cstructure%3E.CASES.md).  
  
## Exemples  
 La requête DMX suivante retourne les données de cas pour une série de produit spécifique, à partir d'un modèle de série chronologique. La requête retourne également la colonne **Amount**, qui n'a pas été utilisée dans le modèle, mais qui est disponible dans la structure d'exploration de données.  
  
```  
SELECT [DateSeries], [Model Region], Quantity, StructureColumn('Amount') AS [M200 Pacific Amount]  
FROM Forecasting.CASES  
WHERE [Model Region] = 'M200 Pacific'  
```  
  
 Notez que, dans cet exemple, un alias a été utilisé pour renommer la colonne de structure. Si vous n'assignez pas d'alias à la colonne de structure, la colonne est retournée avec le nom 'Expression'. Il s'agit du comportement par défaut pour toutes les colonnes sans nom.  
  
## Voir aussi  
 [Requêtes d’extraction &#40;exploration de données&#41;](../../analysis-services/data-mining/drillthrough-queries-data-mining.md)   
 [Extraction sur des structures d'exploration de données](../../analysis-services/data-mining/drillthrough-on-mining-structures.md)  
  
  