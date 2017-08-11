---
title: "Ajouter, modifier ou supprimer les valeurs par défaut d’un paramètre de rapport | Documents Microsoft"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- "10460"
- sql13.rtp.rptdesigner.reportparameters.defaultvalues.f1
- "10072"
ms.assetid: 6a87e069-b3a9-47b6-bcec-afcdd8aff65f
caps.latest.revision: 11
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: aca61d548532fcb6f61c23130e34bf426c8672c9
ms.contentlocale: fr-fr
ms.lasthandoff: 08/09/2017

---
# <a name="add-change-or-delete-default-values-for-a-report-parameter"></a>Ajouter, modifier ou supprimer les valeurs par défaut d'un paramètre de rapport
  Après avoir créé un paramètre de rapport, vous pouvez fournir une liste de valeurs par défaut. Si tous les paramètres ont une valeur par défaut valide, le rapport s'exécute automatiquement lorsque vous l'affichez pour la première fois ou en affichez un aperçu.  
  
 Les paramètres de rapport peuvent représenter une ou plusieurs valeurs. Pour les valeurs uniques, vous pouvez fournir un littéral ou une expression. Pour les valeurs multiples, vous pouvez fournir une liste statique ou une liste provenant d'un dataset de rapport.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 Après la publication d'un rapport, vous pouvez remplacer les valeurs par défaut définies dans l'outil de création de rapports en définissant les valeurs de propriété de paramètre sur le serveur de rapports. Vous pouvez également fournir plusieurs jeux de valeurs de paramètre par défaut en créant des rapports liés. Pour plus d’informations, consultez  [Report Parameters &#40;Report Builder and Report Designer&#41;](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md)  
  
### <a name="to-add-or-change-the-default-values-for-a-report-parameter"></a>Pour ajouter ou modifier les valeurs par défaut d'un paramètre de rapport  
  
1.  Dans le volet Données du rapport, développez le nœud **Paramètres** . Cliquez avec le bouton droit sur le paramètre, puis cliquez sur **Modifier**. La boîte de dialogue **Propriétés du paramètre de rapport** s'ouvre.  
  
    > [!NOTE]  
    >  Si le volet Données du rapport n’est pas visible, cliquez sur **Affichage** , puis sur **Données du rapport**.  
  
2.  Cliquez sur **Valeurs par défaut**.  
  
3.  Sélectionnez une option par défaut :  
  
    -   Pour fournir manuellement une valeur ou une liste de valeurs, cliquez sur **Spécifier les valeurs**. Cliquez sur **Ajouter** , puis entrez la valeur dans la zone de texte **Valeur** . Vous pouvez écrire une expression pour une valeur. Le type de données doit correspondre au type de données du paramètre. Les noms de champs ne peuvent pas être utilisés dans une expression pour un paramètre.  
  
         Pour les paramètres à valeurs multiples, répétez cette étape pour toutes les valeurs que vous souhaitez fournir. L'ordre des éléments que vous voyez dans cette liste détermine l'ordre dans lequel l'utilisateur les voit dans la liste déroulante. Pour modifier l’ordre d’un élément dans la liste, cliquez sur la zone de texte **Valeur** pour sélectionner l’élément, puis utilisez les flèches haut et bas pour déplacer l’élément dans la liste.  
  
    -   Pour fournir le nom d’un dataset existant qui récupère les valeurs, cliquez sur **Obtenir les valeurs à partir d’une requête**. Dans **Dataset**, choisissez le nom du dataset.  
  
         Dans **Champ de valeur**, choisissez le nom du champ qui fournit les valeurs de paramètre.  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-the-default-values-for-a-report-parameter"></a>Pour supprimer les valeurs par défaut d'un paramètre de rapport  
  
1.  Dans le volet Données du rapport, développez le nœud **Paramètres** . Cliquez avec le bouton droit sur le paramètre, puis cliquez sur **Modifier**. La boîte de dialogue **Propriétés du paramètre de rapport** s'ouvre.  
  
2.  Cliquez sur **Valeurs par défaut**.  
  
3.  Dans **Sélectionnez l’une des options suivantes**, cliquez sur **Aucune valeur par défaut**.  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Paramètres de rapport &#40; Le Générateur de rapports et le Concepteur de rapports &#41;](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md)   
 [Ajouter des paramètres en cascade à un rapport &#40; Le Générateur de rapports et SSRS &#41;](../../reporting-services/report-design/add-cascading-parameters-to-a-report-report-builder-and-ssrs.md)   
 [Didacticiel : Ajouter un paramètre à votre rapport &#40; Le Générateur de rapports &#41;](../../reporting-services/tutorial-add-a-parameter-to-your-report-report-builder.md)   
 [Ajouter des filtres de Dataset, filtres de régions de données et les filtres de groupe &#40; Le Générateur de rapports et SSRS &#41;](../../reporting-services/report-design/add-dataset-filters-data-region-filters-and-group-filters.md)   
 [Références à la Collection Parameters &#40; Le Générateur de rapports et SSRS &#41;](../../reporting-services/report-design/built-in-collections-parameters-collection-references-report-builder.md)   
 [Modifier l’ordre d’un paramètre de rapport &#40; Le Générateur de rapports et SSRS &#41;](../../reporting-services/report-design/change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)   
 [Ajouter, modifier ou supprimer un paramètre de rapport &#40; Le Générateur de rapports et SSRS &#41;](../../reporting-services/report-design/add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md)   
 [Expressions &#40; Le Générateur de rapports et SSRS &#41;](../../reporting-services/report-design/expressions-report-builder-and-ssrs.md)  
  
  
