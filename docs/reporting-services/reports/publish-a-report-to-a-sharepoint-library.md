---
title: "publier un rapport dans une biblioth&#232;que SharePoint | Microsoft Docs"
ms.custom: ""
ms.date: "03/07/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "déploiement [Reporting Services], rapports dans SharePoint en mode intégré"
  - "intégration SharePoint [Reporting Services], publication dans une bibliothèque"
  - "publication de rapports [Reporting Services], dans une bibliothèque SharePoint"
ms.assetid: 3f6dfc28-50d8-4231-bd25-871b5f77cce6
caps.latest.revision: 15
author: "guyinacube"
ms.author: "asaxton"
manager: "erikre"
caps.handback.revision: 15
---
# publier un rapport dans une biblioth&#232;que SharePoint
  Pour publier un rapport sur un site SharePoint configuré pour l'intégration SharePoint, vous devez définir les propriétés du projet dans le Concepteur de rapports. Dans les propriétés du projet, toutes les références aux serveurs, aux rapports et aux sources de données partagées doivent être des URL complètes. Dans la définition de rapport, toutes les références aux sous-rapports, aux rapports d'extraction et aux ressources, telles que des images Web, doivent être des URL complètes.  
  
 Vous devez avoir l’autorisation de **Membre** ou de **Propriétaire** sur le site SharePoint pour définir les propriétés du projet. Pour plus d’informations, consultez [Exemples d’URL pour les éléments de rapport publiés sur un serveur de rapports en mode SharePoint &#40;SSRS&#41;](../../reporting-services/tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).  
  
### Pour publier un rapport sur un site SharePoint  
  
1.  Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez un projet Report Server nouveau ou existant.  
  
2.  Dans le menu **Projet**, cliquez sur **Propriétés**. La boîte de dialogue *Pages de propriétés de \<projet>***** s’affiche.  
  
3.  Dans la liste **Configuration**, sélectionnez le nom d’une configuration de build de solution à utiliser pour générer et publier votre rapport. La configuration actuelle est répertoriée comme **Active**(*\<configuration>*).  
  
4.  Si vous souhaitez publier les sources de données partagées dans votre projet et remplacer celles précédemment publiées, affectez la valeur **True** à **OverwriteDataSources**.  
  
5.  (Facultatif) Pour **TargetDataSourceFolder**, tapez une URL vers une bibliothèque SharePoint ou un dossier de bibliothèque (par exemple, *http://TestServer/TestSite/Documents/DataSources)*.  
  
     Si vous ne spécifiez pas de valeur, la valeur **TargetReportFolder** est utilisée.  
  
6.  Pour **TargetReportFolder**, tapez une URL vers une bibliothèque ou un dossier de bibliothèque (par exemple, *http://TestServer/TestSite/Documents/Reports)*.  
  
7.  Pour **TargetServerURL**, tapez une URL vers un sous-site ou un site SharePoint de niveau supérieur. Si vous ne spécifiez pas de site, le site de niveau supérieur par défaut est utilisé (par exemple, *http://nom_serveur*, *http://nom_serveur/site* ou *http://nom_serveur/site/sous-site*).  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
9. Dans l’Explorateur de solutions, cliquez avec le bouton droit sur le rapport à publier, puis cliquez sur **Déployer**. Le rapport est publié à l’emplacement spécifié dans **TargetReportFolder**. Les erreurs de déploiement apparaissent dans la fenêtre Sortie.  
  
## Voir aussi  
 [Pages de propriétés du projet, boîte de dialogue](../../reporting-services/tools/project-property-pages-dialog-box.md)   
 [Définir des propriétés de déploiement &#40;Reporting Services&#41;](../../reporting-services/tools/set-deployment-properties-reporting-services.md)   
 [Publication de rapports sur un serveur de rapports](../../reporting-services/reports/publishing-reports-to-a-report-server.md)   
 [Exemples d’URL pour les éléments de rapport publiés sur un serveur de rapports en mode SharePoint &#40;SSRS&#41;](../../reporting-services/tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md)   
 [Utiliser une connexion de données Office &#40;.odc&#41; avec les rapports &#40;Reporting Services en mode intégré SharePoint&#41;](../../reporting-services/report-data/use an office data connection (.odc) with reports.md)  
  
  