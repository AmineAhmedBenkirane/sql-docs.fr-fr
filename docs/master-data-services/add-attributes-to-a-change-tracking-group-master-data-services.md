---
title: "Ajouter des attributs &#224; un groupe de suivi des modifications (Master Data Services) | Microsoft Docs"
ms.custom: 
  - "SQL2016_New_Updated"
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "master-data-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "groupes de suivi des modifications [Master Data Services]"
  - "Attributs [Master Data Services], groupes de suivi des modifications"
  - "groupes de suivi des modifications [Master Data Services], ajout d’attributs"
ms.assetid: e153eb5f-70ca-4c6f-89d8-1f937ed3917d
caps.latest.revision: 7
author: "sabotta"
ms.author: "carlasab"
manager: "jhubbard"
caps.handback.revision: 7
---
# Ajouter des attributs &#224; un groupe de suivi des modifications (Master Data Services)
  Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], ajoutez des attributs à un groupe de suivi des modifications lorsque vous souhaitez effectuer le suivi des modifications apportées aux valeurs d'attribut.  
  
> [!NOTE]  
>  Lorsque qu'un attribut est ajouté à un groupe de suivi des modifications et que ses valeurs changent, l'attribut est alors signalé comme modifié dans la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] . Créez une règle d'entreprise pour entreprendre une action basée sur la modification.  
  
## Conditions préalables  
 Pour effectuer cette procédure :  
  
-   Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .  
  
-   Vous devez être administrateur de modèle. Pour plus d’informations, consultez [Administrateurs &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
-   Les attributs doivent exister pour pouvoir être ajoutés au groupe de suivi des modifications. Pour plus d’informations, consultez [Créer un attribut de texte &#40;Master Data Services&#41;](../master-data-services/create-a-text-attribute-master-data-services.md).  
  
### Pour ajouter des attributs à un groupe de suivi des modifications  
  
1.  Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.  
  
2.  Dans la page **Gérer le modèle** , sélectionnez un modèle dans la grille et cliquez sur **Entités**.  
  
3.  Dans la page **Gérer l’entité** , sélectionnez la ligne de l’entité pour laquelle vous souhaitez créer un attribut.  
  
4.  Cliquez sur **Attributs**.  
  
5.  Sur la page **Gérer les attributs** , effectuez l’une des opérations suivantes.  
  
    -   Si l’attribut concerne les membres feuille, sélectionnez **Feuille** dans la zone de liste **Types de membres** .  
  
    -   Si l’attribut concerne les membres consolidés, sélectionnez **Consolidé** dans la zone de liste **Types de membre** .  
  
    -   Si l’attribut concerne les collections, sélectionnez **Collection** dans la zone de liste **Types de membre** .  
  
6.  Sélectionnez la ligne de l’attribut que vous souhaitez modifier, puis cliquez sur **Modifier**.  
  
7.  Activez la case à cocher **Activer le suivi des modifications** .  
  
8.  Dans la zone **Groupe de suivi des modifications** , tapez un numéro pour le groupe.  
  
9. Cliquez sur **Enregistrer l'attribut**.  
  
     Pour l’attribut modifié, la colonne **Activer le groupe de suivi des modifications** de la grille est remplacée par **Oui (Groupe : numéro de groupe saisi)**.  
  
10. Répétez cette procédure pour tous les attributs que vous souhaitez inclure dans le groupe. Utilisez le même numéro de groupe de suivi des modifications pour chaque attribut dans le groupe.  
  
## Étapes suivantes  
  
-   [Initier des actions en fonction de modifications de valeurs d’attribut &#40;Master Data Services&#41;](../master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)  
  
## Voir aussi  
 [Créer un attribut de texte &#40;Master Data Services&#41;](../master-data-services/create-a-text-attribute-master-data-services.md)   
 [Créer un attribut basé sur un domaine &#40;Master Data Services&#41;](../master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  