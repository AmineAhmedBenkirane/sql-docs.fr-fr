---
title: "Niveau de compatibilité pour les modèles tabulaires dans Analysis Services | Documents Microsoft"
ms.custom: 
ms.date: 10/16/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: tabular-models
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: sql13.asvs.bidtoolset.versioncompat.f1
ms.assetid: 8943d78d-4a73-4be8-ad14-3d428f5abd06
caps.latest.revision: "27"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: On Demand
ms.openlocfilehash: 385d9a062dfa723e4e73317ffca6984b18f22c47
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="compatibility-level-for-analysis-services-tabular-models"></a>Niveau de compatibilité pour les modèles tabulaires Analysis Services
[!INCLUDE[ssas-appliesto-sqlas-all-aas](../../includes/ssas-appliesto-sqlas-all-aas.md)]

  Le *le niveau de compatibilité* fait référence à des comportements spécifiques à chaque version dans le moteur Analysis Services. Par exemple, DirectQuery et les métadonnées de l’objet sous forme de tableau ont des implémentations différentes en fonction du niveau de compatibilité. En général, vous devez choisir le dernier niveau de compatibilité pris en charge par vos serveurs.

  **Le dernier niveau de compatibilité est 1400** 
  
Principales fonctionnalités dans le niveau de compatibilité 1400 sont les suivantes :

*  Nouvelle infrastructure pour la connectivité de données et les importer dans les modèles tabulaires avec prise en charge de TOM APIs et de script TMSL. Cela permet la prise en charge des sources de données supplémentaires telles que le stockage Blob Azure. Données supplémentaires sources seront inclus dans de futures mises à jour.
*  Transformation de données et des fonctionnalités de combiner des données à l’aide d’expressions M et obtenir des données.
*  Mesures prennent désormais en charge une propriété de lignes de détail avec une expression DAX, l’activation des Outils BI telles que Microsoft Excel exploration aux données détaillées à partir d’un rapport. Par exemple, lorsque les utilisateurs finaux afficher le total des ventes pour une région ou le mois, ils peuvent afficher les détails de la commande associée. 
*  Sécurité au niveau objet pour les noms de table et de colonne, en plus des données au sein de celles-ci.
*  Prise en charge améliorée pour les hiérarchies irrégulières.
*  Surveillance des performances et améliorations.

  
## <a name="supported-compatibility-levels-by-version"></a>Niveaux de compatibilité pris en charge par version
  
|||  
|-|-|- 
|**Niveau de compatibilité**|**Version du serveur**| 
|1400|Azure Analysis Services, SQL Server 2017 |  
|1200|Azure Analysis Services, SQL Server 2017, SQL Server 2016| 
|1103|SQL Server 2017 *, SQL Server 2016, SQL Server 2014, SQL Server 2012 SP1|  
|1100|SQL Server 2017 *, SQL Server 2016, SQL Server 2014, SQL Server 2012 SP1, SQL Server 2012| 

\*niveaux de compatibilité 1100 et 1103 sont déconseillées dans SQL Server 2017.
  
## <a name="set-compatibility-level"></a>Définir le niveau de compatibilité 
 Lorsque vous créez un nouveau projet de modèle tabulaire dans SQL Server Data Tools (SSDT), vous pouvez spécifier le niveau de compatibilité sur les **Générateur de modèles tabulaires** boîte de dialogue. 
  
 ![ssas_tabularproject_compat1200](../../analysis-services/tabular-models/media/ssas-tabularproject-compat1200.png)  
  
 Si vous sélectionnez le **ne plus afficher ce message** option, tous les projets suivants utilise le niveau de compatibilité que vous avez spécifié en tant que la valeur par défaut. Vous pouvez modifier le niveau de compatibilité par défaut dans SSDT sous **Outils** > **Options**.  
  
 Pour mettre à niveau un projet de modèle tabulaire dans SSDT, définissez le **le niveau de compatibilité** propriété du modèle **propriétés** fenêtre. Gardez à l’esprit, le niveau de compatibilité de la mise à niveau est irréversible.
  
## <a name="check-compatibility-level-for-a-database-in-ssms"></a>Vérifier le niveau de compatibilité d'une base de données dans SSMS  
 Dans SSMS, cliquez sur le nom de la base de données > **propriétés** > **le niveau de compatibilité**.  
  
## <a name="check-supported-compatibility-level-for-a-server-in-ssms"></a>Vérifier le niveau de compatibilité pris en charge pour un serveur dans SSMS  
 Dans SSMS, cliquez avec le bouton droit sur le nom du serveur, puis choisissez **Propriétés** > **Niveau de compatibilité pris en charge**.  
  
 Cette propriété spécifie le niveau de compatibilité le plus élevé d’une base de données qui s’exécutent sur le serveur. Le niveau de compatibilité pris en charge est en lecture seule et ne peut pas être modifié.  
  
## <a name="see-also"></a>Voir aussi  
 [Niveau de compatibilité d’une base de données multidimensionnelle](../../analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services.md)   
 [Quelles sont les nouveautés dans Analysis Services](../../analysis-services/what-s-new-in-analysis-services.md)   
 [Créez un projet de modèle tabulaire](../../analysis-services/tabular-models/create-a-new-tabular-model-project-analysis-services.md)  
  
  
