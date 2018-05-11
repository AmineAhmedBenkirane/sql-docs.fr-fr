---
title: Ajouter un attribut à une Dimension | Documents Microsoft
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.component: multidimensional-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: d175c8731c3c808d33e1f9fa7f70a01a15ddbed3
ms.sourcegitcommit: 38f8824abb6760a9dc6953f10a6c91f97fa48432
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2018
---
# <a name="attribute-properties---add-an--attribute-to-a-dimension"></a>Attribut des propriétés - ajouter un attribut à une Dimension
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  Vous pouvez ajouter un attribut à une dimension soit automatiquement, soit manuellement dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
 Pour créer un attribut automatiquement, dans le volet **Structure de dimension** du Concepteur de dimensions de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], sélectionnez la colonne que vous voulez mapper avec un attribut, puis faites glisser cette colonne du volet **Vue de source de données** jusqu’au volet **Attributs** . Vous créez ainsi un attribut qui est mappé avec la colonne et en reçoit le nom. S’il existe déjà un attribut de ce nom, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] lui ajoute à la fin un numéro en commençant par « 1 » pour le premier nom en double.  
  
 Pour créer un attribut manuellement, affichez la grille dans le volet **Attributs**. Dans la colonne nom de la dernière ligne dans la grille, cliquez sur le  **\<nouvel attribut >** élément. Tapez le nom du nouvel attribut. Vous créez ainsi un attribut qui n'est pas mappé avec une colonne et dont toutes les propriétés ont leurs valeurs par défaut. Vous pouvez définir le mappage dans la fenêtre **Propriétés** de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] en configurant la propriété **KeyColumns** du nouvel attribut.  
  
 Pour plus d’informations, consultez [Définir un nouvel attribut automatiquement](../../analysis-services/multidimensional-models/attribute-properties-define-a-new-attribute-automatically.md), [Lier un attribut à une colonne de nom](../../analysis-services/multidimensional-models/attribute-properties-bind-an-attribute-to-a-name-column.md)et [Modifier la propriété KeyColumn d’un attribut](../../analysis-services/multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Dimension Attribute Properties Reference](../../analysis-services/multidimensional-models/dimension-attribute-properties-reference.md)  
  
  
