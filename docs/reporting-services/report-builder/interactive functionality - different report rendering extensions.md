---
title: "Fonctionnalit&#233; interactive des diff&#233;rentes extensions de rendu de rapport (G&#233;n&#233;rateur de rapports et SSRS) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f0bd1c4c-e8b5-467f-b5a1-541f19c7e3e2
caps.latest.revision: 7
author: "maggiesMSFT"
ms.author: "maggies"
manager: "erikre"
---
# Fonctionnalit&#233; interactive des diff&#233;rentes extensions de rendu de rapport (G&#233;n&#233;rateur de rapports et SSRS)
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] propose des fonctionnalités permettant d’interagir avec un rapport paginé au moment de l’exécution. Certains formats de rendu de rapport ne prennent pas en charge toutes les fonctionnalités interactives. Le tableau suivant permet de comprendre le fonctionnement de chaque fonctionnalité interactive dans des formats spécifiques.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## Fonctionnalités interactives dans différents formats de sortie  
 Les rapports paginés qui sont restitués aux formats XML, CSV ou Image ne prennent pas en charge les fonctionnalités interactives.  
  
 Les rapports que vous affichez dans le portail web [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], les composants WebPart de SharePoint ou dans un navigateur sont restitués au format HTML. HTML et Windows Forms sont les seuls formats de sortie de rapport qui prennent entièrement en charge toutes les fonctionnalités interactives. Les autres formats HTML (par exemple MHTML) prennent en charge de nombreuses fonctionnalités interactives. S'il existe des exceptions pour MHTML, elles sont indiquées dans le tableau suivant.  
  
### Explorateur de documents  
  
|Option d'exportation|Informations de support|  
|-------------------|-------------------------|  
|Aperçu/Visionneuse de rapports, HTML|L'explorateur de documents interactif fournit un volet de navigation de liens hiérarchiques pouvant être utilisés pour accéder aux différentes sections d'un rapport.|  
|PDF|L'extension PDF restitue un plan de document sous la forme du volet Signets. Tous les éléments du plan de document sont listés l'un après l'autre dans le volet. Il inclut une hiérarchie de liens. Si une plage de pages est spécifiée, seuls les signets qui sont rendus existent dans la hiérarchie.|  
|Excel|Excel rend un explorateur de documents sous la forme de la première feuille de calcul du classeur. Il inclut une hiérarchie de liens. Lors d'un clic sur un lien dans l'explorateur de documents, la cellule cible appropriée dans la feuille de calcul correspondante est ouverte.|  
|Word|Word rend l'explorateur de documents sous la forme d'étiquettes Table des matières.|  
|Autre (par exemple, TIFF, XML et CSV)|Non disponible en MHTML, XML, CSV ou Image.|  
  
### Liens d'extraction vers d'autres rapports  
  
|Option d'exportation|Informations de support|  
|-------------------|-------------------------|  
|Aperçu/Visionneuse de rapports, HTML|Les utilisateurs cliquent sur des valeurs de données dans le rapport pour visualiser des données associées dans un autre rapport.|  
|PDF|Les liens d'extraction ne sont pas disponibles dans les PDF. Envisagez plutôt l'utilisation de liens hypertexte qui renvoient à d'autres pages pour les rapports PDF.|  
|Excel|Les liens d'extraction sont rendus dans Excel.<br /><br /> Le lien devient un lien hypertexte pointant vers le rapport référencé par le lien d'extraction. Un clic sur le lien ouvre un rapport dans une fenêtre de navigateur.|  
|Word|Les liens d'extraction sont rendus dans Word.<br /><br /> Le lien devient un lien hypertexte pointant vers le rapport référencé par le lien d'extraction. Un clic sur le lien ouvre un rapport dans une fenêtre de navigateur.|  
|Autres|Non disponible en XML, CSV ou Image.|  
  
### Éléments bascule dans un rapport  
  
|Option d'exportation|Informations de support|  
|-------------------|-------------------------|  
|Aperçu/Visionneuse de rapports, HTML|Les utilisateurs cliquent sur des icônes de développement et de réduction pour afficher des sections du rapport.|  
|PDF|Le serveur de rapports exporte la vue actuelle du rapport au format PDF. Le basculement interactif n'est pas pris en charge|  
|Excel|Les liens et éléments d'exploration qui peuvent être basculés sont rendus sous forme de plans réductibles dans Excel. Vous pouvez développer et réduire des sections du rapport dans Excel. Pour plus d’informations sur les limitations imposées par Excel, consultez [Exportation vers Microsoft Excel &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).|  
|Word|Le serveur de rapports exporte la vue actuelle du rapport au format PDF. Le basculement interactif n'est pas pris en charge|  
|Autres|Non disponible en MHTML, XML ou CSV. Lors de l'exportation au format Image, le serveur de rapports exporte l'état actuel (afficher ou masquer) du rapport en PDF. Le basculement interactif n'est pas pris en charge.|  
  
### Tri interactif  
  
|Option d'exportation|Informations de support|  
|-------------------|-------------------------|  
|Aperçu/Visionneuse de rapports, HTML|Pour les rapports tabulaires, les utilisateurs cliquent sur des flèches de tri sur une colonne pour changer le mode de tri des données.|  
|PDF|Non disponible dans le format PDF.|  
|Excel|Non disponible dans Excel.|  
|Word|Non disponible dans Word.|  
|Autres|Non disponible en MHTML, XML, CSV ou Image.|  
  
### Liens hypertexte vers du contenu ou des images Web externes  
  
|Option d'exportation|Informations de support|  
|-------------------|-------------------------|  
|Aperçu/Visionneuse de rapports, HTML|Les utilisateurs cliquent sur des liens pour ouvrir des pages Web externes dans une nouvelle fenêtre de navigateur.|  
|PDF|Les liens hypertexte sont rendus par l'extension de rendu PDF. Lorsqu'un utilisateur clique sur un lien hypertexte, les pages liées sont ouvertes dans le navigateur.|  
|Excel|Les liens hypertexte sont rendus dans Excel.|  
|Word|Les liens hypertexte sont rendus dans Word.|  
|Autres|Les liens hypertexte ne sont pas disponibles en MHTML, XML, CSV ou Image.<br /><br /> Pour MHTML et Image, les images externes sont rendues sous forme d'image statique.|  
  
### Signet ou ancrage  
  
|Option d'exportation|Informations de support|  
|-------------------|-------------------------|  
|Aperçu/Visionneuse de rapports, HTML|Les utilisateurs cliquent sur des liens pour naviguer vers une autre section du même rapport.|  
|PDF|Non disponible dans le format PDF.|  
|Excel|Les signets sont rendus dans Excel.<br /><br /> Le signet devient un lien hypertexte pointant vers le nom de l'élément du rapport.|  
|Word|Les signets sont rendus dans Word.<br /><br /> Le signet devient un lien hypertexte pointant vers l'élément du rapport marqué d'un signet. Seuls 40 caractères d'un signet ou d'un nom d'ancre sont convertis lorsque le rapport est exporté, ce qui peut créer des signets ou des noms d'ancre en double. Les espaces sont convertis en traits de soulignement (_).|  
|Autres|Non disponible en XML, CSV ou Image.|  
  
### Paramètres demandés obtenus au moment de l'exécution  
  
|Option d'exportation|Informations de support|  
|-------------------|-------------------------|  
|Aperçu/Visionneuse de rapports, HTML|Une zone d'entrée de paramètres apparaît en haut du rapport. Cette zone fait partie de la visionneuse HTML utilisée pour afficher des rapports dans un navigateur.|  
|PDF|Le serveur de rapports exporte le rapport au format PDF en utilisant les valeurs des paramètres actuellement en vigueur pour le rapport.|  
|Excel|Le serveur de rapports exporte le rapport au format Excel en utilisant les valeurs des paramètres actuellement en vigueur pour le rapport.|  
|Word|Le serveur de rapports exporte le rapport au format Word en utilisant les valeurs des paramètres actuellement en vigueur pour le rapport.|  
|Autres|Le serveur de rapports exporte le rapport à d'autres formats en utilisant les valeurs des paramètres actuellement en vigueur pour le rapport.|  
  
### Filtres appliqués au moment de l'exécution  
  
|Option d'exportation|Informations de support|  
|-------------------|-------------------------|  
|Aperçu/Visionneuse de rapports, HTML|Les données filtrées sont présentées à l'utilisateur au moment de l'exécution.|  
|PDF|Le serveur de rapports exporte le rapport au format PDF en utilisant les données filtrées dans le rapport actuel.|  
|Excel|Le serveur de rapports exporte le rapport au format Excel en utilisant les données filtrées dans le rapport actuel.|  
|Word|Le serveur de rapports exporte le rapport au format Word en utilisant les données filtrées dans le rapport actuel.|  
|Autres|Le serveur de rapports exporte le rapport à d'autres formats en utilisant les données filtrées dans le rapport actuel.|  
  
## Voir aussi  
 [Exporter des rapports &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-builder/export-reports-report-builder-and-ssrs.md)   
 [Tri interactif, Explorateurs de documents et liens &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/interactive-sort-document-maps-and-links-report-builder-and-ssrs.md)   
 [Matrices &#40;Générateur de rapports et SSRS&#41;](../Topic/Matrices%20\(Report%20Builder%20and%20SSRS\).md)   
 [Tables, matrices et listes &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/tables-matrices-and-lists-report-builder-and-ssrs.md)   
 [Graphiques &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)  
  
  