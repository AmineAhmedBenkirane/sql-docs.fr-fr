---
title: "Élément BaseProperty (CSDLBI) | Documents Microsoft"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: tabular-models
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
ms.assetid: d0f63e52-7330-4b2c-a929-7a517acc6921
caps.latest.revision: "6"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 79d391ef3ac0388187c91dac96859172a347effc
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="baseproperty-element-csdlbi"></a>Élément BaseProperty (CSDLBI)
  L'élément BaseProperty est un type complexe qui sert de base aux autres éléments.  
  
 Ses attributs peuvent apparaître dans les colonnes et dans les mesures.  
  
## <a name="elements-and-attributes"></a>Éléments et attributs  
 Le tableau suivant répertorie les éléments et les attributs qui définissent l'élément BaseProperty.  
  
|Nom|Est obligatoire|Description|  
|----------|-----------------|-----------------|  
|Alignment|Non|Nom donné au membre (une colonne, une mesure, une propriété de navigation, une hiérarchie ou un niveau) défini par l'implémentation du type Member.|  
|FormatString|Non|Nom complet du membre.|  
|IsRightToLeft|Non|Valeur booléenne qui indique si le champ contient du texte qui doit être lu de droite à gauche.<br /><br /> Si cet attribut est omis, la valeur par défaut (du modèle) est utilisée.|  
|SortDirection|Non|Valeur qui indique comment les valeurs des champs sont généralement triées. Le contenu de cet attribut est défini par le type simple SortDirection.<br /><br /> En cas d'omission, un ordre de tri est affecté par défaut en fonction du type de données du champ.|  
|Unités|Non|Symbole qui est appliqué aux valeurs de champ pour exprimer des unités.<br /><br /> En cas d'omission, les unités sont inconnues.|  
  
## <a name="alignment-element"></a>Élément Alignment  
 Ce type simple définit le format d'affectation des noms qui est utilisé pour lever toute ambiguïté des membres.  
  
|Valeur|Description|  
|-----------|-----------------|  
|Aucune|Utilise le nom de l'attribut.|  
|Contexte|Utilise le nom de la relation entrante.|  
|Fusion|Selon les règles de grammaire, concatène le nom de la relation entrante et le nom de l'attribut.|  
  
## <a name="sortdirection-element"></a>Élément SortDirection  
 Ce type simple définit le format d'affectation des noms qui est utilisé pour lever toute ambiguïté des membres.  
  
|Valeur|Description|  
|-----------|-----------------|  
|Aucune|Utilise le nom de l'attribut.|  
|Contexte|Utilise le nom de la relation entrante.|  
|Fusion|Concatène le nom de la relation entrante et le nom de la propriété.|  
  
## <a name="see-also"></a>Voir aussi  
 [Présentation du modèle d’objet tabulaire au niveau de compatibilité 1050 1103 via des niveaux](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)  
  
  
