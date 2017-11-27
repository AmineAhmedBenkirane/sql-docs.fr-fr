---
title: Ensemble de lignes DMSCHEMA_MINING_FUNCTIONS | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: schema-rowsets
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: reference
apiname: DMSCHEMA_MINING_FUNCTIONS
apitype: NA
applies_to: SQL Server 2016 Preview
helpviewer_keywords: DMSCHEMA_MINING_FUNCTIONS rowset
ms.assetid: 9ace7493-a7b1-45ca-93de-3cb2f3597017
caps.latest.revision: "35"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: c33bf605db92bae91a0d05c5b4ea8feb6d4542e7
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="dmschemaminingfunctions-rowset"></a>Ensemble de lignes DMSCHEMA_MINING_FUNCTIONS
  Décrit les fonctions d’exploration de données qui sont pris en charge par les algorithmes d’exploration de données disponibles sur un serveur qui est en cours d’exécution [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
## <a name="rowset-columns"></a>Colonnes de l'ensemble de lignes  
 L'ensemble de lignes **DMSCHEMA_MINING_FUNCTIONS** contient les colonnes suivantes.  
  
|Nom de colonne|Indicateur de type|Longueur| Description|  
|-----------------|--------------------|------------|-----------------|  
|**SERVICE_NAME**|**DBTYPE_WSTR**||Nom de l'algorithme.|  
|**NOM DE LA FONCTION**|**DBTYPE_WSTR**||Nom de la fonction.|  
|**FUNCTION_SIGNATURE**|**DBTYPE_WSTR**||Signature de la fonction.|  
|**RETURNS_TABLE**|**DBTYPE_BOOL**||**FALSE** si la fonction retourne le contenu scalaire (tel que la longueur de l'argument de caractère) ; **TRUE** si la fonction retourne une table (telle qu'une table d'histogrammes).|  
|**DESCRIPTION**|**DBTYPE_WSTR**||Description conviviale de la fonction.|  
|**HELP_FILE**|**DBTYPE_WSTR**||Nom du fichier qui contient la documentation de cette fonction.|  
|**HELP_CONTEXT**|**DBTYPE_I4**||ID de contexte d'aide de cette fonction.|  
  
## <a name="restriction-columns"></a>Colonnes de restriction  
 L'ensemble de lignes **DMSCHEMA_MINING_FUNCTIONS** peut être restreint sur les colonnes répertoriées dans le tableau suivant.  
  
|Nom de colonne|Indicateur de type|État de la restriction|  
|-----------------|--------------------|-----------------------|  
|**SERVICE_NAME**|**DBTYPE_WSTR**|Ce paramètre est facultatif.|  
|**NOM DE LA FONCTION**|**DBTYPE_WSTR**|Ce paramètre est facultatif.|  
  
## <a name="see-also"></a>Voir aussi  
 [Ensembles de lignes de schéma d’exploration de données](../../../analysis-services/schema-rowsets/data-mining/data-mining-schema-rowsets.md)  
  
  
