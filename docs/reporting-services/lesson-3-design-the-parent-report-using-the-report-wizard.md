---
title: "Leçon 3 : Concevoir le rapport Parent à l’aide de l’Assistant rapport | Documents Microsoft"
ms.custom: 
ms.date: 05/18/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- SQL Server 2016
ms.assetid: 2f69dcd3-cd6d-45a9-a62a-ba6f5f3179d8
caps.latest.revision: 9
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: b491008866649087e050b04261bfde7a3ad82e92
ms.contentlocale: fr-fr
ms.lasthandoff: 08/09/2017

---
# <a name="lesson-3-design-the-parent-report-using-the-report-wizard"></a>Leçon 3 : concevoir le rapport parent à l'aide de l'Assistant Rapport
Après avoir créé une connexion de données et une table de données pour le rapport parent, l'étape suivante consiste à concevoir le rapport parent à l'aide de l'Assistant Rapport dans le Concepteur de rapports. Pour plus d’informations sur le Concepteur de rapports, consultez [concevoir des rapports avec le Concepteur de rapports &#40; SSRS &#41; ](../reporting-services/tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).  
  
### <a name="to-design-the-parent-report-using-the-report-wizard"></a>Pour concevoir le rapport parent à l'aide de l'Assistant Rapport  
  
1.  Vérifiez que le site web de niveau supérieur est sélectionné dans **l’Explorateur de solutions**.  
  
2.  Cliquez avec le bouton droit sur le site web et sélectionnez **Ajouter un nouvel élément**.  
  
3.  Dans la boîte de dialogue **Ajouter un nouvel élément** , sélectionnez **Assistant Rapport**, entrez un nom pour le fichier de rapport, puis sélectionnez **Ajouter**.  
  
    Cette opération permet de lancer l'Assistant Rapport.  
  
4.  Dans la page **Propriétés du dataset** , dans la zone **Source de données** , sélectionnez le **DataSet1** que vous avez créé à la [Leçon 2 : Définir une connexion de données et une table de données pour le rapport parent](../reporting-services/lesson-2-define-a-data-connection-and-data-table-for-parent-report.md).  
  
    La zone **Datasets disponibles** est mise à jour automatiquement avec l’objet **DataTable** créé précédemment.  
  
5.  Sélectionnez **Suivant**.  
  
6.  Dans la page **Organiser les champs** , procédez comme suit :  
  
    1.  Faites glisser **ProductID**, **Name**, **ProductNumber**, **SafetyStockLevel**et **ReorderLevel** depuis **Champs disponibles** vers la zone **Valeurs** .  
  
    2.  Sélectionnez la flèche en regard de **Sum(ProductID)**, **Sum(SafetyStockLevel)**, **Sum(ReorderLevel)** et effacez la sélection de **Somme** .  
  
7.  Sélectionnez deux fois **Suivant** , puis sélectionnez **Terminer** pour fermer **l’Assistant Rapport**.  
  
    Vous venez de créer le fichier .rdlc. Le fichier s'ouvre dans le Concepteur de rapports. Le tableau matriciel que vous avez conçu est maintenant affiché dans l'aire de conception.  
  
8.  Enregistrez le fichier .rdlc.  
  
## <a name="next-task"></a>Tâche suivante  
Vous venez de concevoir le rapport parent à l'aide de l'Assistant Rapport. Vous allez à présent créer une connexion de données et une table de données pour le rapport enfant. Consultez la [Leçon 4 : Définir une connexion de données et une table de données pour le rapport enfant](../reporting-services/lesson-4-define-a-data-connection-and-data-table-for-child-report.md).  
  
  
  


