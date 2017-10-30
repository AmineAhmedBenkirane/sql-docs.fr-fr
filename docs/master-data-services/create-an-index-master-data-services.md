---
title: "Créer un index (Master Data Services) | Microsoft Docs"
ms.custom:
- SQL2016_New_Updated
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d694a105-69b1-4ff6-99d3-1f408b916b81
caps.latest.revision: 6
author: smartysanthosh
ms.author: nagavo
manager: craigg
ms.workload: Inactive
ms.translationtype: HT
ms.sourcegitcommit: 0b832a9306244210e693bde7c476269455e9b6d8
ms.openlocfilehash: ee405ebea31b8ca2a178b2d287a1ba1b8d4e97f8
ms.contentlocale: fr-fr
ms.lasthandoff: 09/07/2017

---
# <a name="create-an-index-master-data-services"></a>Créer un index (Master Data Services)
  Créez un index personnalisé sur une liste d’attributs que vous interrogez fréquemment, afin d’améliorer les performances des requêtes.  
  
## <a name="prerequisites"></a>Conditions préalables  
 Pour effectuer cette procédure :  
  
-   Vous devez avoir l’autorisation d’accéder à la zone fonctionnelle Administration de système. Pour plus d’informations, consultez [Autorisations de zone fonctionnelle &#40;Master Data Services&#41;](../master-data-services/functional-area-permissions-master-data-services.md).  
  
-   Vous devez être administrateur de modèle. Pour plus d’informations, consultez [Administrateurs &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
 **Pour créer un index**  
  
1.  Dans Master Data Manager, cliquez sur **Administration de système**.  
  
2.  Dans la page **Gérer le modèle** , sélectionnez un modèle dans la grille et cliquez sur **Entités**.  
  
3.  Dans la **grille** de la page **Gérer l’entité** , sélectionnez la ligne de l’entité pour laquelle vous souhaitez créer un index.  
  
4.  Cliquez sur **Index**.  
  
5.  Dans la zone **Nom** , indiquez le nom de l’index.  
  
6.  Sélectionnez **Est unique** si vous souhaitez créer un index unique. Pour plus d’informations sur les types d’index, consultez [Index personnalisé &#40;Master Data Services&#41;](../master-data-services/custom-index-master-data-services.md).  
  
7.  Cliquez sur les attributs dans la zone **Attributs disponibles** , puis sur la flèche **Ajouter** . Pour ajouter tous les attributs, cliquez sur la flèche **Ajouter tout** .  
  
8.  Cliquez sur **Enregistrer**.  
  
 Pour chaque index créé, une ligne avec quatre colonnes est ajoutée dans la grille. Le tableau suivant décrit les colonnes.  
  
|Nom de la colonne|Description|  
|-----------------|-----------------|  
|État|État de l’index.<br /><br /> Quand vous cliquez sur **Enregistrer**, l’image ![Icône d’état de mise à jour](../master-data-services/media/mds-statusicon-updating.png "Icône d’état de mise à jour") s’affiche, indiquant que l’index est en cours de mise à jour.<br /><br /> Si des erreurs se produisent pendant la création ou la modification d’un index, l’image ![Icône d’état d’erreur](../master-data-services/media/mds-statusicon-error.png "Icône d’état d’erreur") apparaît.<br /><br /> Sinon, l’état est OK ; dans cas, l’image ![Icône d’état OK](../master-data-services/media/mds-statusicon-ok.png "Icône d’état OK") s’affiche.|  
|Nom|Nom de l'index.|  
|Est unique|Indique si l’index est unique.|  
|Sur les attributs|Affiche les noms complets des attributs sur lesquels l’index est défini.|  
  
 Lorsque vous cliquez sur un index, les informations suivantes s’affichent.  
  
-   **Créé par**: nom de l’utilisateur qui a créé l’index.  
  
-   **Le**: date et heure de création de l’index.  
  
-   **Mis à jour par**: nom de l’utilisateur qui a en dernier mis à jour l’index.  
  
-   **Le**: date et heure de mise à jour de l’index.  
  
## <a name="next-steps"></a>Étapes suivantes  
 [Modifier et supprimer un index &#40;Master Data Services&#41;](../master-data-services/edit-and-delete-an-index-master-data-services.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Index personnalisé &#40;Master Data Services&#41;](../master-data-services/custom-index-master-data-services.md)  
  
  

