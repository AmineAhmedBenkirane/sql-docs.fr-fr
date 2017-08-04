---
title: "Créer et exécuter une relation de synchronisation d’entité (Master Data Services) | Documents Microsoft"
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
ms.assetid: 0ddceab4-d2b3-4bc1-bd9c-6b852200b414
caps.latest.revision: 6
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: f9efe68604f73df42930c5b3eb348e5c2b3e7965
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="create-and-execute-an-entity-sync-relationship-master-data-services"></a>Créer et exécuter une relation de synchronisation d’entités (Master Data Services)
  La synchronisation d'entités est une synchronisation unidirectionnelle et reproductible entre des versions d'entités. Elle fournit un moyen de partager des données d’entités entre différents modèles.  
  
## <a name="prerequisites"></a>Conditions préalables  
 Conditions préalables pour créer une relation de synchronisation d’entités :  
  
-   Vous devez avoir l’autorisation d’accéder à la zone fonctionnelle Administration de système. Pour plus d’informations, consultez [Autorisations de zone fonctionnelle &#40;Master Data Services&#41;](../master-data-services/functional-area-permissions-master-data-services.md).  
  
-   Vous devez être administrateur du modèle cible. Pour plus d’informations, consultez [Administrateurs &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
-   Vous devez disposer au minimum de l’accès en lecture pour l’entité source et l’ensemble de ses attributs et de ses membres.  
  
 Conditions préalables pour exécuter une relation de synchronisation d’entités :  
  
-   Vous devez avoir l’autorisation d’accéder à la zone fonctionnelle Administration de système. Pour plus d’informations, consultez [Autorisations de zone fonctionnelle &#40;Master Data Services&#41;](../master-data-services/functional-area-permissions-master-data-services.md).  
  
-   Vous devez être administrateur du modèle cible. Pour plus d’informations, consultez [Administrateurs &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
 Considérez les éléments suivants lorsque vous créez une relation de synchronisation d’entités.  
  
-   Les entités source et cible doivent être dans des modèles différents.  
  
-   Le statut de la version de l’entité cible ne doit pas être validé.  
  
-   Une fois une relation de synchronisation établie, la cible est immédiatement synchronisée avec la source.  
  
-   Une version de l'entité cible ne peut pas être une version de l'entité source d'une autre relation de synchronisation.  
  
 Considérez les éléments suivants lorsque vous exécutez une relation de synchronisation d’entités.  
  
-   Seuls les membres feuilles seront copiés.  
  
-   Les attributs fondés sur les domaines ne seront pas copiés.  
  
-   Les membres supprimés de façon réversible ne seront pas copiés.  
  
-   La synchronisation ne génère pas de transactions/historiques de l'entité cible.  
  
 **Pour créer une relation de synchronisation d’entités**  
  
1.  Dans Master Data Manager, cliquez sur **Administration de système**.  
  
2.  Sur la page **Vue du modèle** , dans la barre de menus, pointez sur **Gérer** et cliquez sur **Synchronisation d’entités**.  
  
3.  Sur la page **Maintenance de la synchronisation d'entités** , cliquez sur **Ajouter**. Un panneau s'affiche sur le côté droit.  
  
4.  Dans la liste **Modèle** source, sélectionnez un modèle.  
  
5.  Dans la liste **Version** source, sélectionnez une version.  
  
6.  Dans la liste **Entité** source, sélectionnez une entité.  
  
7.  Dans la liste **Modèle** cible, sélectionnez un modèle.  
  
8.  Dans la liste **Version** cible, sélectionnez une version.  
  
9. Choisissez **Entité existante** et sélectionnez une entité dans la liste des entités, si vous souhaitez synchroniser une entité existante, ou choisissez **Nouvelle entité** et entrez le nom de l'entité cible si vous voulez effectuer la synchronisation avec une nouvelle entité  
  
10. Sélectionnez **Synchronisation à la demande**, ou sélectionnez **Synchronisation automatique** et définissez une fréquence.  
  
11. Cliquez sur **Enregistrer**.  
  
 **Pour exécuter une relation de synchronisation d’entités**  
  
1.  Dans Master Data Manager, cliquez sur **Administration de système**.  
  
2.  Sur la page **Vue du modèle** , dans la barre de menus, pointez sur **Gérer** et cliquez sur **Synchronisation d’entités**.  
  
3.  Sur la page **Maintenance de la synchronisation d'entités** , sélectionnez une relation de synchronisation dans la grille.  
  
4.  Cliquez sur **Exécuter**.  
  
## <a name="sync-relationship-information"></a>Informations sur les relations de synchronisation  
 Pour chaque relation de synchronisation créée, une ligne comportant dix colonnes est ajoutée à la grille. Le tableau suivant décrit ces colonnes.  
  
|Colonne|Description|  
|------------|-----------------|  
|État|Le statut de la relation de synchronisation.<br /><br /> Lorsque vous cliquez sur **enregistrer** ou exécuter une relation de synchronisation, le ![icône de mise à jour d’état](../master-data-services/media/mds-statusicon-updating.png "icône de mise à jour d’état") image s’affiche, indiquant que la relation de synchronisation met à jour.<br /><br /> S’il existe des erreurs lors de la création, de modification ou de l’exécution d’une relation de synchronisation, le ![icône de statut d’erreur](../master-data-services/media/mds-statusicon-error.png "icône de statut d’erreur") image s’affiche.<br /><br /> Dans le cas contraire, l’état est OK et la ![icône pour l’état OK](../master-data-services/media/mds-statusicon-ok.png "icône pour l’état OK") image s’affiche.|  
|Modèle source|Nom du modèle source.|  
|Version source|Nom de la version source.|  
|Entité source|Nom de l'entité source.|  
|Modèle cible|Nom du modèle cible.|  
|Version cible|Nom de la version cible.|  
|Entité cible|Nom de l'entité cible.|  
|Fréquence|Spécifie la fréquence de la relation de synchronisation.|  
|Heure de la dernière tentative|Affiche l’heure de la dernière tentative de synchronisation.|  
|Heure de la dernière tentative réussie|Affiche l’heure de la dernière tentative de synchronisation réussie.|  
  
 Lorsque vous cliquez sur un index, les informations suivantes s'affichent.  
  
-   **Erreur de la dernière tentative**: affiche les informations d'erreur de la dernière tentative de synchronisation.  
  
-   **Créée par**: nom de l’utilisateur qui a créé la synchronisation.  
  
-   **Le**: date et heure de création de la synchronisation.  
  
-   **Mise à jour par**: nom de l’utilisateur qui a mis à jour la synchronisation en dernier.  
  
-   **Le**: date et heure de la dernière mise à jour de la synchronisation.  
  
## <a name="next-steps"></a>Étapes suivantes  
 [Modifier et supprimer une relation de synchronisation d’entités &#40;Master Data Services&#41;](../master-data-services/edit-and-delete-an-entity-sync-relationship-master-data-services.md)  
  
  
