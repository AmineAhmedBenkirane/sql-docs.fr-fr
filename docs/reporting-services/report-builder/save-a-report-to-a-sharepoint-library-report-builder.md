---
title: "Enregistrer un rapport dans une biblioth&#232;que SharePoint (G&#233;n&#233;rateur de rapports) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4daa1eee-78b7-43d0-8b22-4a98e8fa66ba
caps.latest.revision: 10
author: "maggiesMSFT"
ms.author: "maggies"
manager: "erikre"
caps.handback.revision: 10
---
# Enregistrer un rapport dans une biblioth&#232;que SharePoint (G&#233;n&#233;rateur de rapports)
  Pour enregistrer un rapport sur un serveur de rapports configuré pour une intégration SharePoint, vous devez accéder au serveur SharePoint et établir une connexion au serveur de rapports. Dans la définition de rapport, toutes les références aux éléments associés au rapport doivent utiliser des valeurs spécifiques à un serveur de rapports SharePoint. Les éléments associés peuvent consister en des sous-rapports, des rapports d'extraction et des ressources telles que des images Web. Pour plus d’informations, consultez [Spécification de chemins d’accès à des éléments externes &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md).  
  
 Vous devez disposer de l’autorisation **Membre** ou **Propriétaire** sur le site SharePoint pour définir les propriétés du projet.  
  
### Pour enregistrer un rapport sur un site SharePoint  
  
1.  À partir du bouton Générateur de rapports, cliquez sur **Enregistrer**. La boîte de dialogue **Enregistrer sous***\<élément de rapport>* s’affiche.  
  
    > [!NOTE]  
    >  Si vous réenregistrez un rapport, il est automatiquement stocké à son emplacement précédent. Utilisez l’option **Enregistrer sous** pour modifier l’emplacement.  
  
2.  Cliquez éventuellement sur **Sites et serveurs récents** pour afficher une liste de serveurs de rapports et de sites SharePoint récemment utilisés.  
  
3.  Accédez au site SharePoint, puis cliquez sur **Enregistrer**.  
  
    > [!NOTE]  
    >  Si vous n'enregistrez pas un rapport ayant subi des modifications dans un délai de 10 heures, il est déconnecté du serveur sans être enregistré. Dans ce cas, dans la barre d’état inférieure droite, cliquez sur **Déconnecter**, puis sur **Connecter**. Le serveur le plus récent figurera dans la liste des serveurs disponibles. Sélectionnez-le pour que le rapport soit à nouveau connecté.  
  
## Voir aussi  
 [Recherche, affichage et gestion des rapports &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  