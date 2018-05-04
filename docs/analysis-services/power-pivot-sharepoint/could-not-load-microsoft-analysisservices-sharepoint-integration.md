---
title: N’a pas pu charger 'Microsoft.AnalysisServices.SharePoint.Integration' | Documents Microsoft
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.component: ppvt-sharepoint
ms.topic: article
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: b90fd2a99bd6321936c0cef399ec115baceced0f
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="could-not-load-microsoftanalysisservicessharepointintegration"></a>N’a pas pu charger Microsoft.AnalysisServices.SharePoint.Integration
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  Dans les environnements SharePoint 2010 qui disposent de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] pour SharePoint, cette erreur se produit si la solution au niveau de l’application pour [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] n’a pas été déployée correctement.  
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|S'applique à|[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] pour SharePoint|  
|Version du produit|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|  
|Cause|La solution Powerpivotwebapp n'est pas déployée ou n'a pas été déployée correctement.|  
|Texte du message|Impossible de charger le fichier ou l'assembly 'Microsoft.AnalysisServices.SharePoint.Integration'|  
  
## <a name="explanation"></a>Explication  
 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] pour SharePoint utilise des packages de solution pour déployer ses fonctionnalités sur un serveur SharePoint. L'une des solutions n'est pas déployée correctement. Cette erreur s’affiche donc chaque fois que vous essayez d’ouvrir la Galerie [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] ou d’autres pages d’application [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] sur un site SharePoint.  
  
## <a name="user-action"></a>Action de l'utilisateur  
 Déployez le package de solution.  
  
1.  Dans l'Administration centrale, sous Paramètres système, cliquez sur **Gérer les solutions de la batterie**.  
  
2.  Cliquez sur **Powerpivotwebapp**.  
  
3.  Cliquez sur **Déployer la solution**.  
  
4.  Choisissez l'application Web pour laquelle cette erreur se produit. S'il y a plusieurs applications Web, redéployez la solution pour chacune d'entre elles.  
  
5.  Cliquez sur **OK**.  
  
## <a name="see-also"></a>Voir aussi  
 [Déployer des solutions Power Pivot sur SharePoint](../../analysis-services/power-pivot-sharepoint/deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
