---
title: "Leçon 6 : Créer des colonnes calculées | Documents Microsoft"
ms.custom: 
ms.date: 03/27/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: tutorial
ms.reviewer: 
ms.suite: sql
ms.technology: analysis-services
ms.tgt_pltfrm: 
ms.topic: get-started-article
applies_to: SQL Server 2016
ms.assetid: d126766a-5699-4e9f-8213-8c7eea0fc14e
caps.latest.revision: "26"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: On Demand
ms.openlocfilehash: be1b5d0bbe08a51ec4ffd6873a8f8295125d13db
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="lesson-5-create-calculated-columns"></a>Leçon 5 : Créer des colonnes calculées
[!INCLUDE[ssas-appliesto-sql2016-later-aas](../includes/ssas-appliesto-sql2016-later-aas.md)]

Dans cette leçon, vous allez créer des données dans votre modèle en ajoutant des colonnes calculées. Une colonne calculée est basée sur les données qui existent déjà dans votre modèle. Pour plus d’informations, consultez [colonnes calculées](../analysis-services/tabular-models/ssas-calculated-columns.md).  
  
Vous allez créer cinq nouvelles colonnes calculées dans trois tables différentes. Les étapes sont légèrement différentes pour chaque tâche. Il s'agit de montrer qu'il existe plusieurs façons de créer de nouvelles colonnes, de les renommer, puis de les placer à différents emplacements dans une table.  
  
Durée estimée pour effectuer cette leçon : **15 minutes**  
  
## <a name="prerequisites"></a>Conditions préalables  
Cette rubrique fait partie d'un didacticiel de modélisation tabulaire, qui doit être suivi dans l'ordre. Avant d’effectuer les tâches de cette leçon, vous devez avoir terminé la leçon précédente : [leçon 4 : créer des relations](../analysis-services/lesson-4-create-relationships.md). 
  
## <a name="create-calculated-columns"></a>Créer des colonnes calculées  
  
#### <a name="create-a-monthcalendar-calculated-column-in-the-dimdate-table"></a>Créer une colonne calculée MonthCalendar dans la table DimDate  
  
1.  Cliquez sur le **modèle** menu > **vue de modèle** > **vue données**.  
  
    Les colonnes calculées ne peuvent être créées qu'à l'aide du concepteur de modèles dans la vue de données.  
  
2.  Dans le Générateur de modèles, cliquez sur le **DimDate** table (onglet).  
  
3.  Cliquez sur le **CalendarQuarter** en-tête de colonne, puis cliquez sur **insérer une colonne**.  
  
    Une nouvelle colonne nommée **Calculated Column 1** est insérée à gauche de la colonne **Calendar Quarter** .  
  
4.  Dans la barre de formule au-dessus de la table, tapez la formule suivante. La saisie semi-automatique vous aide à taper les noms complets de colonnes et de tables et répertorie les fonctions disponibles.  
  
    ```  
    =RIGHT(" " & FORMAT([MonthNumberOfYear],"#0"), 2) & " - " & [EnglishMonthName]  
    ``` 
  
    Des valeurs remplissent ensuite toutes les lignes de la colonne calculée. Si vous faites défiler la table vers le bas, vous remarquez que les lignes peuvent avoir des valeurs différentes pour cette colonne, en fonction des données figurant dans chaque ligne.    
  
5.  Renommer cette colonne **MonthCalendar**. 

    ![en tant que-tabulaire-lesson5-nouvelle colonne](../analysis-services/media/as-tabular-lesson5-newcolumn.png) 
  
Le MonthCalendar calculée de colonne qui fournit un nom triable pour le mois.  
  
#### <a name="create-a-dayofweek-calculated-column-in-the-dimdate-table"></a>Créer une colonne calculée DayOfWeek dans la table DimDate  
  
1.  Avec la **DimDate** table toujours active, cliquez sur le **colonne** menu, puis sur **ajouter une colonne**.  
  
2.  Dans la barre de formule, entrez la formule suivante :  
    
    ```
    =RIGHT(" " & FORMAT([DayNumberOfWeek],"#0"), 2) & " - " & [EnglishDayNameOfWeek]  
    ```
    
    Lorsque vous avez terminé de générer la formule, appuyez sur ENTRÉE. La nouvelle colonne est ajoutée à droite de la table.  
  
3.  Renommer la colonne **DayOfWeek**.  
  
4.  Cliquez sur l’en-tête de colonne, puis faites glisser la colonne entre la **EnglishDayNameOfWeek** colonne et la **DayNumberOfMonth** colonne.  
  
    > [!TIP]  
    > Déplacer les colonnes dans la table facilite la navigation.  
  
L’énumération DayOfWeek calculée de colonne qui fournit un nom triable pour le jour de semaine.  
  
#### <a name="create-a-productsubcategoryname-calculated-column-in-the-dimproduct-table"></a>Créer une colonne calculée ProductSubcategoryName dans la table DimProduct  
  
  
1.  Dans le **DimProduct** table, faites défiler vers la droite de la table. Notez que la colonne la plus à droite est nommée **Add Column** (en italique), cliquez sur l’en-tête de colonne.  
  
2.  Dans la barre de formule, entrez la formule suivante.  
    
    ```
    =RELATED('DimProductSubcategory'[EnglishProductSubcategoryName])  
    ```
  
3.  Renommer la colonne **ProductSubcategoryName**.  
  
La colonne calculée ProductSubcategoryName est utilisée pour créer une hiérarchie dans la table DimProduct qui inclut des données à partir de la colonne EnglishProductSubcategoryName dans la table DimProductSubcategory. Les hiérarchies ne peuvent pas couvrir plusieurs tables. Vous allez créer des hiérarchies plus loin dans la leçon 9.  
  
#### <a name="create-a-productcategoryname-calculated-column-in-the-dimproduct-table"></a>Créer une colonne calculée ProductCategoryName dans la table DimProduct  
  
1.  Avec la **DimProduct** table toujours active, cliquez sur le **colonne** menu, puis sur **ajouter une colonne**.  
  
2.  Dans la barre de formule, entrez la formule suivante :  
  
    ```
    =RELATED('DimProductCategory'[EnglishProductCategoryName]) 
    ```
    
3.  Renommer la colonne **ProductCategoryName**.  
  
La colonne ProductCategoryName est utilisée pour créer une hiérarchie dans la table DimProduct qui inclut des données à partir de la colonne EnglishProductCategoryName dans la table DimProductCategory. Les hiérarchies ne peuvent pas couvrir plusieurs tables.  
  
#### <a name="create-a-margin-calculated-column-in-the-factinternetsales-table"></a>Créer une colonne calculée de marge dans la table FactInternetSales  
  
1.  Dans le Générateur de modèles, sélectionnez le **FactInternetSales** table.  
  
2.  Ajoutez une nouvelle colonne.  
  
3.  Dans la barre de formule, entrez la formule suivante :  
  
    ```
    =[SalesAmount]-[TotalProductCost]
    ``` 

4.  Renommez la colonne en **Margin**.  
  
5.  Faites glisser la colonne entre la **SalesAmount** colonne et la **TaxAmt** colonne. 
 
      ![en tant que-tabulaire-lesson5-newmargin](../analysis-services/media/as-tabular-lesson5-newmargin.png)
      
    La colonne calculée Margin est utilisée pour analyser les marges bénéficiaires pour chaque vente.  
  
## <a name="whats-next"></a>Étape suivante
Accédez à la leçon suivante : [Leçon 6 : créer des mesures](../analysis-services/lesson-6-create-measures.md).
  
  
  
