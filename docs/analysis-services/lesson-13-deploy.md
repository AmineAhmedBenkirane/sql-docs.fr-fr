---
title: "Leçon 14 : Déployer | Documents Microsoft"
ms.custom: 
ms.date: 03/27/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: get-started-article
applies_to:
- SQL Server 2016
ms.assetid: 24863a8a-9017-415a-a97b-fbac76ed0675
caps.latest.revision: 25
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: f93ae84ae1ab52e5be122b0d2d397af7bf9e458a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="lesson-13-deploy"></a>Leçon 13 : déployer
[!INCLUDE[ssas-appliesto-sql2016-later-aas](../includes/ssas-appliesto-sql2016-later-aas.md)]

Dans cette leçon, vous allez configurer les propriétés de déploiement ; spécification d’un site local ou instance de serveur Windows Azure et un nom pour le modèle. Vous allez ensuite déployer le modèle à cette instance. Une fois votre modèle est déployé, les utilisateurs peuvent se connecter à ce dernier à l’aide d’une application cliente de création de rapports. Pour en savoir plus sur le déploiement, consultez [déploiement de solutions de modèle tabulaire](../analysis-services/tabular-models/tabular-model-solution-deployment-ssas-tabular.md) et [déployer vers Azure Analysis Services](https://docs.microsoft.com/azure/analysis-services/analysis-services-deploy).  
  
Durée estimée pour effectuer cette leçon : **5 minutes**  
  
## <a name="prerequisites"></a>Conditions préalables  
Cette rubrique fait partie d'un didacticiel de modélisation tabulaire, qui doit être suivi dans l'ordre. Avant d’effectuer les tâches de cette leçon, vous devez avoir terminé la leçon précédente : [leçon 12 : analyser dans Excel](../analysis-services/lesson-12-analyze-in-excel.md).  
  
## <a name="deploy-the-model"></a>Déployer le modèle  
  
#### <a name="to-configure-deployment-properties"></a>Pour configurer les propriétés de déploiement  
  
1.  Dans **l’Explorateur de solutions**, avec le bouton droit le **AW Internet Sales** de projet, puis cliquez sur **propriétés**.  
  
2.  Dans le **Pages de propriétés de AW Internet Sales** boîte de dialogue **serveur de déploiement**, dans le **serveur** , tapez le nom d’un serveur Azure Analysis Services ou d’un serveur local de l’instance en cours d’exécution en mode tabulaire. Il s’agit de l’instance de serveur que à votre modèle sera déployé.  

    ![agents-déployer-déploiement-server-propriété](../analysis-services/media/aas-deploy-deployment-server-property.png)
 
    > [!IMPORTANT]  
    > Vous devez disposer des autorisations d’administrateur sur le distant Analysis Services instance afin de déployer sur celle-ci.  
  
3.  Dans le **base de données** , tapez **Internet Sales Adventure Works**.  
  
4.  Dans le **Nom_modèle** , tapez **Adventure Works Internet Sales Model**.  
  
5.  Vérifiez vos sélections, puis cliquez sur **OK**.  
  
#### <a name="to-deploy-the-adventure-works-internet-sales-tabular-model"></a>Pour déployer le modèle tabulaire Internet Sales Adventure Works  
  
1.  Dans **l’Explorateur de solutions**, avec le bouton droit le **AW Internet Sales** projet > **Build**.  

2.  Cliquez sur le **AW Internet Sales** projet > **déployer**.

    Lors du déploiement vers Azure Analysis Services, vous allez probablement être invité à entrer votre compte. Permet d’entrer votre compte professionnel et un mot de passe, par exemple nancy@adventureworks.com. Ce compte doit être dans les administrateurs sur l’instance de serveur.
  
    La boîte de dialogue Déployer apparaît et affiche l'état de déploiement des métadonnées ainsi que de chaque table incluse dans le modèle.  
    
    ![état déployer des agents](../analysis-services/media/aas-deploy-status.png)
  
3. Une fois le déploiement correctement effectué, cliquez sur **Fermer**.  
  
## <a name="conclusion"></a>Conclusion  
Félicitations ! Vous avez terminé de créer et déployer votre premier modèle tabulaire Analysis Services. Ce didacticiel vous a guidés dans les tâches courantes pour créer un modèle tabulaire. Maintenant que votre modèle Internet Sales Adventure Works est déployé, vous pouvez utiliser SQL Server Management Studio pour gérer le modèle, créer des scripts de processus et un plan de sauvegarde. Les utilisateurs peuvent également maintenant vous connecter à l’aide d’une application cliente de création de rapports tels que Microsoft Excel ou Power BI.  

![en tant que-tabulaire-lesson13-ssms](../analysis-services/media/as-tabular-lesson13-ssms.png)
  
  
## <a name="see-also"></a>Voir aussi  
[Mode DirectQuery &#40;SSAS Tabulaire&#41;](../analysis-services/tabular-models/directquery-mode-ssas-tabular.md)  
[Configurer les propriétés par défaut de modélisation des données et de déploiement &#40;SSAS Tabulaire&#41;](../analysis-services/tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md)  
[Bases de données model tabulaires #40;SSAS Tabulaire#41;](../analysis-services/tabular-models/tabular-model-databases-ssas-tabular.md)  
  
  
  ## <a name="whats-next"></a>Étape suivante
*  [Leçon supplémentaire - implémenter la sécurité dynamique à l’aide de filtres de lignes](../analysis-services/supplemental-lesson-implement-dynamic-security-by-using-row-filters.md).

*  [Supplémentaires leçon - configurer les propriétés de création de rapports pour les rapports Power View](../analysis-services/supplemental-lesson-configure-reporting-properties-for-power-view-reports.md).

