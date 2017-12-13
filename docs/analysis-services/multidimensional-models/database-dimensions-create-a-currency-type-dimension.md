---
title: "Créer une Dimension de type devise | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: analysis-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dimensions [Analysis Services], currency
- currency [Analysis Services]
- converting currency
- currency dimensions [Analysis Services]
ms.assetid: b1f037d1-ce47-4e47-a1c2-5ec9e781cff6
caps.latest.revision: "16"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 9f94776235df7717712840218d811fdc08f9de09
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2017
---
# <a name="database-dimensions---create-a-currency-type-dimension"></a>Dimensions de base de données : création d’une Dimension de type devise
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], une dimension de type devise est une dimension dont les attributs représentent une liste de devises pour les rapports financiers.  
  
 Une dimension monétaire permet d'ajouter des fonctions de conversion monétaire à un cube dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Pour ajouter une conversion monétaire à un cube, utilisez l'Assistant Business Intelligence pour définir une commande de script MDX (Multidimensional Expressions) qui convertit les mesures monétaires en valeurs correspondant aux paramètres régionaux de l'application cliente. Pour créer ce script MDX, vous devez fournir les informations suivantes à l'Assistant Business Intelligence :  
  
-   Une dimension monétaire qui représente les devises sources. (Cette dimension est la dimension monétaire source.)  
  
-   Un groupe de mesures qui représente les taux de change à utiliser.  
  
 À partir de ces informations, l'Assistant Business Intelligence crée un processus de conversion monétaire qui identifie la dimension monétaire de destination appropriée (la dimension monétaire qui représente les devises de destination). Selon le nombre de conversions monétaires nécessaires à la solution décisionnelle, l'Assistant Business Intelligence peut définir plusieurs dimensions monétaires de destination. Pour plus d’informations sur la définition de conversions monétaires, consultez [Conversions monétaires &#40;Analysis Services&#41;](../../analysis-services/currency-conversions-analysis-services.md).  
  
 Pour définir une dimension comme dimension monétaire, affectez la valeur **Devise** à la propriété **Type** de la dimension.  
  
## <a name="dimension-structure"></a>Structure de la dimension  
 Une dimension monétaire contient au moins un attribut clé qui identifie les devises dans la table de la dimension monétaire. La valeur de l'attribut clé est différente dans les dimensions monétaires source et de destination :  
  
-   Pour définir un attribut comme attribut clé d’une dimension monétaire source, affectez la valeur **CurrencySource** à la propriété **Type**de l’attribut.  
  
-   Pour définir un attribut comme attribut clé d’une dimension monétaire de destination, affectez la valeur **CurrencyDestination** à la propriété **Type**de l’attribut.  
  
 Pour les rapports, les dimensions monétaires source et de destination peuvent contenir éventuellement les attributs suivants :  
  
-   Un attribut de nom de devise  
  
     Pour définir un attribut comme attribut de nom de devise, affectez la valeur **CurrencyName** à la propriété **Type**de l’attribut.  
  
-   Un attribut de source de devise  
  
     Pour définir un attribut comme attribut de source de devise, affectez la valeur **CurrencySource** à la propriété **Type**de l’attribut.  
  
-   Un code ISO (International Standards Organization) de devise  
  
     Pour définir un attribut comme attribut de code ISO de devise, affectez la valeur **CurrencyIsoCode** à la propriété **Type**de l’attribut.  
  
 Pour plus d’informations sur les types d’attributs, consultez [Configurer des types d’attributs](../../analysis-services/multidimensional-models/attribute-properties-configure-attribute-types.md).  
  
## <a name="defining-account-intelligence-with-the-business-intelligence-wizard"></a>Définition de l'intelligence comptable avec l'Assistant Business Intelligence  
 Après avoir défini une dimension de comptes et ajouté la dimension à un cube, vous pouvez utiliser l'Assistant Business Intelligence pour ajouter des fonctions d'intelligence comptable, telles que l'identification et le mappage de types de comptes, à la dimension. Pour plus d’informations, consultez [Ajouter de l’intelligence comptable à une dimension](../../analysis-services/multidimensional-models/bi-wizard-add-account-intelligence-to-a-dimension.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs et hiérarchies d'attributs](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md)   
 [Aide F1 l’Assistant Business Intelligence](http://msdn.microsoft.com/library/155ac80c-63ae-47aa-9e86-9396e3d920eb)   
 [Types de dimensions](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
