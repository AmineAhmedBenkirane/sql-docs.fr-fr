---
title: "Propri&#233;t&#233;s de projet (SSAS Tabulaire) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "analysis-services/multidimensional-tabular"
  - "analysis-services/data-mining"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.asvs.bidtoolset.depservconfig.f1"
  - "sql13.asvs.bidtoolset.semmodelprojprop.f1"
ms.assetid: 333c1fc0-361c-415a-bd68-4e057f67bcb7
caps.latest.revision: 27
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
caps.handback.revision: 27
---
# Propri&#233;t&#233;s de projet (SSAS Tabulaire)
  Cette rubrique décrit les propriétés de projet de modèle. Chaque projet de modèle tabulaire propose des propriétés de serveur de déploiement et d'options de déploiement qui spécifient comment le projet et le modèle sont déployés. Par exemple, le serveur sur lequel le modèle sera déployé et le nom de la base de données model déployée. Ces paramètres sont différents des propriétés du modèle, qui affectent la base de données model de l'espace de travail. Les propriétés du projet décrites ici se trouvent dans une boîte de dialogue de propriétés modale différente de la fenêtre de propriétés utilisée pour afficher les autres types de propriétés. Pour afficher les propriétés de projet modales, dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], dans **l’Explorateur de solutions**, cliquez avec le bouton droit sur le projet, puis cliquez sur **Propriétés**.  
  
 Sections de cette rubrique :  
  
-   [Propriétés du projet](#bkmk_proj_properties)  
  
-   [Configurer les paramètres de propriété Options de déploiement et Serveur de déploiement](#bkmk_conf_proj_settings)  
  
##  <a name="bkmk_proj_properties"></a> Propriétés du projet  
 **Options de déploiement**  
  
|Propriété|Paramètre par défaut|Description|  
|--------------|---------------------|-----------------|  
|**Option de traitement**|**Par défaut**|Par défaut, Analysis Services détermine le type de traitement nécessaire lorsque des changements d'objet sont déployés. Cette approche résulte en un temps de déploiement réduit. Cependant, vous pouvez également choisir d'effectuer un traitement complet ou aucun traitement à chaque déploiement.|  
|**Déploiement transactionnel**|**False**|Spécifie si le déploiement du modèle est transactionnel ou non. Par défaut, le déploiement de tous les objets ou des objets modifiés n'est pas transactionnel avec le traitement de ces objets déployés. Le déploiement peut réussir et être conservé même si le traitement échoue. Vous pouvez modifier cette valeur pour incorporer le déploiement et le traitement dans une seule transaction.|  
|**Mode de requête**|**In-Memory**|Spécifie la source depuis laquelle les résultats de la requête sont renvoyés. Pour plus d’informations, consultez [Mode DirectQuery &#40;SSAS Tabulaire&#41;](../../analysis-services/tabular-models/directquery-mode-ssas-tabular.md).|  
  
 **Serveur de déploiement**  
  
|Propriété|Paramètre par défaut|Description|  
|--------------|---------------------|-----------------|  
|**Server**|**localhost**|Spécifie une instance d'Analysis Services. Par défaut, les modèles sont déployés dans l'instance par défaut d'Analysis Services sur l'ordinateur local. Vous pouvez modifier ce paramètre pour spécifier une instance nommée sur l'ordinateur local ou n'importe quelle autre instance sur un ordinateur distant sur lequel vous avez l'autorisation de créer des objets Analysis Services. En général, les autorisations d'administrateur.<br /><br /> Le paramètre par défaut de cette propriété peut être modifié à l'aide de la propriété Serveur de déploiement par défaut sur la page Déploiement dans les paramètres du serveur d'analyse de la boîte de dialogue Outils\Options. Pour plus d’informations, consultez [Configurer les propriétés par défaut de modélisation des données et de déploiement &#40;SSAS Tabulaire&#41;](../../analysis-services/tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md).|  
|**Édition**|**Développeur**|Spécifie l'édition du serveur Analysis Services sur lequel le modèle sera déployé. L'édition du serveur définit différentes fonctionnalités qui peuvent être incorporées dans le projet.|  
|**Base de données**|**Modèle**|Spécifie le nom de la base de données Analysis Services dans laquelle les objets de modèle seront instanciés lors du déploiement. Ce nom sera spécifié dans une connexion de données ou un fichier de connexion de données .rsds. Il est recommandé que le nom reflète le type d'analyse qui sera effectuée à l'aide du modèle, par exemple AdventureWorksSalesModel.<br /><br /> Pour empêcher les noms en double pour les modèles déployés, vous devez modifier le paramètre de nom de la propriété **Base de données** pour refléter l’objectif du modèle. Il s'agit du nom que les utilisateurs verront lorsqu'ils se connecteront au modèle en tant que source de données.|  
|**Nom du cube**|**Modèle**|Spécifie le nom du cube de base de données comme indiqué dans une connexion de données au client de création de rapports.|  
|**Version**|**13.0**|Version de l'instance d'Analysis Services où le projet sera déployé.|  
  
 **Options DirectQuery**  
  
|Propriété|Paramètre par défaut|Description|  
|--------------|---------------------|-----------------|  
|**Paramètres d'emprunt d'identité**|**Par défaut**|Spécifie les informations d'identification utilisées pour se connecter aux sources de données pour un modèle s'exécutant en mode DirectQuery. Ces informations d'identification sont différentes des informations d'identification d'emprunt d'identité utilisées en mode In-Memory par défaut. Pour plus d’informations, consultez [Emprunt d’identité &#40;SSAS Tabulaire&#41;](../../analysis-services/tabular-models/impersonation-ssas-tabular.md).|  
  
##  <a name="bkmk_conf_proj_settings"></a> Configurer les paramètres de propriété Options de déploiement et Serveur de déploiement  
  
1.  Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], dans **l’Explorateur de solutions**, cliquez avec le bouton droit sur le projet, puis sélectionnez **Propriétés**.  
  
2.  Dans la fenêtre **Propriétés** , cliquez sur une propriété, puis tapez une valeur ou cliquez sur la flèche Bas pour sélectionner une option de paramètre.  
  
## Voir aussi  
 [Configurer les propriétés par défaut de modélisation des données et de déploiement &#40;SSAS Tabulaire&#41;](../../analysis-services/tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md)   
 [Propriétés de modèle &#40;SSAS Tabulaire&#41;](../../analysis-services/tabular-models/model-properties-ssas-tabular.md)   
 [Déploiement d’une solution de modèle tabulaire &#40;SSAS Tabulaire&#41;](../../analysis-services/tabular-models/tabular-model-solution-deployment-ssas-tabular.md)  
  
  