---
title: "R&#233;f&#233;rences &#224; des collections DataSources et DataSets (G&#233;n&#233;rateur de rapports et SSRS) | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f951a4aa-da55-4e43-8579-4a5d4480d11f
caps.latest.revision: 7
author: "maggiesMSFT"
ms.author: "maggies"
manager: "erikre"
---
# R&#233;f&#233;rences &#224; des collections DataSources et DataSets (G&#233;n&#233;rateur de rapports et SSRS)
  La collection **DataSources** représente toutes les sources de données utilisées dans un rapport. De la même façon, la collection **DataSets** représente tous les datasets de toutes les sources de données dans un rapport. Utilisez le volet **Données du rapport** pour une vue hiérarchique des datasets du rapport organisés sous la source de données à laquelle ils font référence. Si vous incluez des références à ces collections, vous ne verrez pas de valeurs lors de l'aperçu de votre rapport. Ces collections sont disponibles uniquement après la publication du rapport sur un serveur de rapports.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## DataSources  
 La collection **DataSources** représente les sources de données référencées dans la définition d’un rapport publié. Vous pouvez choisir d'inclure ces informations dans votre rapport pour documenter la source des données de rapport. Cette collection n’est pas disponible en mode **Aperçu**. Le tableau ci-dessous décrit les variables de la collection **DataSources**.  
  
|**Variable**|**Type**|**Description**|  
|------------------|--------------|---------------------|  
|**DataSourceReference**|**Chaîne**|Chemin d'accès complet de la définition de source de données sur le serveur de rapports. Par exemple, vous pouvez inclure une liste de toutes les sources de données qu'un rapport a utilisées dans le cadre d'un historique de rapport. L'exemple suivant affiche le chemin d'accès complet de la source de données nommée AdventureWorks2012 :<br /><br /> `/DataSources/AdventureWorks2012`.|  
|**Type**|**Chaîne**|Type du fournisseur de données pour la source de données. Par exemple, `SQL`.|  
  
## DataSets  
 La collection **DataSets** représente les datasets référencés dans une définition de rapport. Vous pouvez choisir d'inclure la requête du rapport dans une zone de texte afin qu'un utilisateur intéressé par le contenu exact du rapport puisse examiner le texte de la commande d'origine. Cette collection n’est pas disponible en mode **Aperçu**. Le tableau ci-dessous décrit les membres de la collection **DataSets** .  
  
|**Membre**|**Type**|**Description**|  
|----------------|--------------|---------------------|  
|**CommandText**|**Chaîne**|Pour les sources de données de base de données, il s'agit de la requête employée pour récupérer des données à partir de la source de données. Si la requête est une expression, elle correspond à l'expression évaluée.|  
|**RewrittenCommandText**|**Chaîne**|Valeur CommandText développée du fournisseur de données. Elle est généralement utilisée pour les rapports dont les paramètres de requête sont mappés aux paramètres du rapport. Le fournisseur de données définit cette propriété lors du développement des références de paramètre du texte de commande dans les valeurs de constante sélectionnées pour les paramètres de rapport mappés.|  
  
### Utilisation d'expressions de requête  
 Vous pouvez utiliser des expressions pour définir la requête contenue dans un dataset. Vous pouvez utiliser cette fonctionnalité pour concevoir des rapports où la requête change en fonction de l'entrée de l'utilisateur, de données d'autres datasets ou d'autres variables. Pour plus d’informations sur les requêtes, consultez [Datasets incorporés dans les rapports et datasets partagés &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).  
  
## Voir aussi  
 [Expressions &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/expressions-report-builder-and-ssrs.md)   
 [Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/expression-examples-report-builder-and-ssrs.md)  
  
  