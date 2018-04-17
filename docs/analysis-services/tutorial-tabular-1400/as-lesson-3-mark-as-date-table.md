---
title: 'Leçon du didacticiel Analysis Services 3 : marquer en tant que Table de dates | Documents Microsoft'
description: Décrit comment marquer une table de dates dans le projet du didacticiel Analysis Services.
ms.prod_service: analysis-services, azure-analysis-services
services: analysis-services
ms.suite: pro-bi
documentationcenter: ''
author: Minewiskan
manager: kfile
editor: ''
tags: ''
ms.assetid: ''
ms.service: analysis-services
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: na
ms.date: 02/20/2018
ms.author: owend
monikerRange: '>= sql-analysis-services-2017 || = sqlallproducts-allversions'
ms.openlocfilehash: 679e3d629bb69ce4aab067b1becc7df8af24e140
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="mark-as-date-table"></a>Marquer en tant que table de dates

[!INCLUDE[ssas-appliesto-sql2017-later-aas](../../includes/ssas-appliesto-sql2017-later-aas.md)]

Dans, leçon 2 : Obtenir des données, vous avez importé une table de dimension nommée **DimDate**. Alors que dans votre modèle, cette table est nommée DimDate, il peut également être appelé une *table de dates*, car elle contient des données de date et d’heure.  
  
Lorsque vous utilisez les fonctions time intelligence DAX, comme lorsque vous créez des mesures plus tard, vous devez spécifier les propriétés qui incluent un *table de dates* et un identificateur unique *colonne de Date* dans cette table.
  
Dans cette leçon, vous marquez le **DimDate** table en tant que le *table de dates* et **Date** colonne (dans la table Date) en tant que le *colonne de Date* (unique identificateur).  

Avant de sélectionner la table de dates et une colonne de date, il est judicieux de faire un peu housekeeping pour faciliter la compréhension de votre modèle. Notez que, dans la table DimDate, une colonne nommée **FullDateAlternateKey**. Cette colonne contient une ligne pour chaque jour de l’année civile incluse dans la table. Vous utilisez cette colonne beaucoup dans les formules de mesure et dans les rapports. Toutefois, FullDateAlternateKey n’est pas vraiment un bon identificateur pour cette colonne. Renommez-le à **Date**, rendant ainsi plus faciles à identifier et à inclure dans les formules. Chaque fois que possible, il est judicieux de renommer des objets tels que des tables et des colonnes pour les rendre plus facilement repérable dans SSDT et les applications de création de rapports. 
  
Durée estimée pour effectuer cette leçon : **trois minutes**  
  
## <a name="prerequisites"></a>Configuration requise  

Cet article fait partie d’un didacticiel de modélisation tabulaire, qui doit être effectué dans l’ordre. Avant d’effectuer les tâches de cette leçon, vous devez avoir terminé la leçon précédente : [leçon 2 : obtenir des données](../tutorial-tabular-1400/as-lesson-2-get-data.md). 

### <a name="to-rename-the-fulldatealternatekey-column"></a>Pour renommer la colonne FullDateAlternateKey

1.  Dans le Générateur de modèles, cliquez sur le **DimDate** table.

2.  Double-cliquez sur l’en-tête pour le **FullDateAlternateKey** colonne, puis renommez-le à **Date**.

  
### <a name="to-set-mark-as-date-table"></a>Pour définir Marquer en tant que table de dates  
  
1.  Sélectionnez la colonne **Date** , puis dans la fenêtre **Propriétés** , sous **Type de données**, vérifiez que  **Date** est sélectionné.  
  
2.  Cliquez sur le menu **Table** , cliquez sur **Date**, puis sur **Marquer comme Table de Date**.  
  
3.  Dans la boîte de dialogue **Marquer comme Table de Date** , dans la zone de liste **Date** , sélectionnez la colonne **Date** comme identificateur unique. Il est généralement sélectionné par défaut. Cliquez sur **OK**. 

    ![en tant que-lesson3-date-table](../tutorial-tabular-1400/media/as-lesson3-date-table.png)
  

## <a name="whats-next"></a>Quelle est l’étape suivante ?

[Leçon 4 : Créer des relations](../tutorial-tabular-1400/as-lesson-4-create-relationships.md).
  
