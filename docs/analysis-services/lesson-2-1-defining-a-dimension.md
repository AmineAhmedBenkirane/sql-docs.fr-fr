---
title: Définition d’une Dimension | Documents Microsoft
ms.custom: ''
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- SQL Server 2016
ms.assetid: 112696db-3838-4b50-91bd-d2ce5fa04ee5
caps.latest.revision: 18
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: e3c8150fcd4bd757bd29732fb2d0ec40a8b487c8
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="lesson-2-1---defining-a-dimension"></a>Leçon 2-1-Définition d’une Dimension
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

Dans la tâche suivante, vous allez utiliser l'Assistant Dimension pour générer une dimension Date.  
  
> [!NOTE]  
> Avant de commencer cette leçon, vous devez avoir terminé toutes les procédures de la leçon 1.  
  
### <a name="to-define-a-dimension"></a>Pour définir une dimension  
  
1.  Dans l’Explorateur de solutions (à droite de Microsoft Visual Studio), cliquez avec le bouton droit sur **Dimensions**, puis cliquez sur **Nouvelle dimension**. L'Assistant Dimension apparaît.  
  
2.  Dans la page **Assistant Dimension** , cliquez sur **Suivant**.  
  
3.  Dans la page **Sélectionner la méthode de création** , vérifiez que l’option **Utiliser une table existante** est sélectionnée, puis cliquez sur **Suivant**.  
  
4.  Dans la page **Spécifier des informations sur la source** , vérifiez que la vue de source des données **Adventure Works DW 2012** est sélectionnée.  
  
5.  Dans la liste **Table principale** , sélectionnez **Date**.  
  
6.  Cliquez sur **Suivant**.  
  
7.  Dans la page **Sélectionner les attributs de la dimension** , cochez les cases à côté des attributs suivants :  
  
    -   **Date Key**  
  
    -   **Full Date Alternate Key**  
  
    -   **English Month Name**  
  
    -   **Calendar Quarter**  
  
    -   **Calendar Year**  
  
    -   **Calendar Semester**  
  
8.  Modifiez le paramètre de la colonne **Type d’attribut** de l’attribut **Full Date Alternate Key** de **Regular** en **Date**. Pour cela, cliquez sur **Regular** dans la colonne **Type d’attribut** . Puis, cliquez sur la flèche pour développer les options. Ensuite, cliquez sur **Date** > **Calendar** > **Date**. Cliquez sur **OK**. Répétez ces étapes pour modifier le type d’attribut des attributs suivants comme suit :  
  
    -   **English Month Name** en **Month**  
  
    -   **Calendar Quarter** en **Quarter**  
  
    -   **Calendar Year** en **Year**  
  
    -   **Calendar Semester** en **Half Year**  
  
9. Cliquez sur **Suivant**.  
  
10. Dans la page **Fin de l’Assistant** , dans le volet de visualisation, vous pouvez consulter la dimension **Date** et ses attributs.  
  
11. Cliquez sur **Terminer** pour terminer l’Assistant.  
  
    Dans l’Explorateur de solutions, dans le projet Didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , la dimension Date apparaît dans le dossier **Dimensions** . Au centre de l'environnement de développement, le Concepteur de dimensions affiche la dimension Date.  
  
12. Dans le menu **Fichier** , cliquez sur **Enregistrer tout**.  
  
## <a name="next-task-in-lesson"></a>Tâche suivante de la leçon  
[Définition d’un Cube](../analysis-services/lesson-2-2-defining-a-cube.md)  
  
## <a name="see-also"></a>Voir aussi  
[Dimensions dans les modèles multidimensionnels](../analysis-services/multidimensional-models/dimensions-in-multidimensional-models.md)  
[Créer une dimension à l'aide d'une table existante](../analysis-services/multidimensional-models/create-a-dimension-by-using-an-existing-table.md)  
[Créer une dimension à l'aide de l'Assistant Dimension](../analysis-services/multidimensional-models/create-a-dimension-using-the-dimension-wizard.md)  
  
  
  
