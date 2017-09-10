---
title: Ensemble de lignes DISCOVER_LOCKS | Documents Microsoft
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- DISCOVER_LOCKS rowset
ms.assetid: dea48167-212c-40b7-a416-434042a1b697
caps.latest.revision: 14
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: d50a6cb0bdc6bfdb27fdbfff4c79b25c43e27e58
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="discoverlocks-rowset"></a>Ensemble de lignes DISCOVER_LOCKS
  Fournit des informations sur les verrous actuellement en place sur le serveur.  
  
## <a name="rowset-columns"></a>Colonnes de l'ensemble de lignes  
 L'ensemble de lignes **DISCOVER_LOCKS** contient les colonnes suivantes.  
  
|Nom de colonne|Indicateur de type|Longueur| Description|  
|-----------------|--------------------|------------|-----------------|  
|**LOCK_CREATION_TIME**|**DBTYPE_DBTIMESTAMP**||Heure UTC du serveur au moment où le verrou a été demandé.|  
|**LOCK_GRANT_TIME**|**DBTYPE_DBTIMESTAMP**||Heure UTC du serveur au moment où le verrou a été accordé sur la ressource.|  
|**LOCK_ID**|**DBTYPE_GUID**||Identificateur unique du verrou, tel qu'un GUID.|  
|**LOCK_OBJECT_ID**|**DBTYPE_WSTR**||Identificateur unique de l'objet actuellement verrouillé.|  
|**LOCK_STATUS**|**DBTYPE_I4**||État du verrou.<br /><br /> 0 signifie « Attente de verrouillage de l'objet ».<br /><br /> 1 signifie « Verrou accordé ».|  
|**LOCK_TRANSACTION_ID**|**DBTYPE_GUID**||Identificateur unique de la transaction, tel qu'un GUID.|  
|**TYPE DE VERROU**|**DBTYPE_I4**||Masque de bits des types de verrouillage ; pour plus d'informations, consultez la section Remarques de cette rubrique.|  
|**SPID**|**DBTYPE_I4**||ID de session.|  
  
 Cet ensemble de lignes de schéma n'est pas trié.  
  
## <a name="restriction-columns"></a>Colonnes de restriction  
 L'ensemble de lignes **DISCOVER_LOCKS** peut être restreint sur les colonnes répertoriées dans le tableau suivant.  
  
|Nom de colonne|Indicateur de type|État de la restriction|  
|-----------------|--------------------|-----------------------|  
|SPID|DBTYPE_I4|Facultatif.|  
|LOCK_TRANSACTION_ID|DBTYPE_GUID|Facultatif.|  
|LOCK_OBJECT_ID|DBTYPE_WSTR|Facultatif.|  
|LOCK_STATUS|DBTYPE_I4|Facultatif.|  
|LOCK_TYPE|DBTYPE_I4|Facultatif.|  
|LOCK_MIN_TOTAL_MS|DBTYPE_I8|Ce paramètre est facultatif.|  
  
## <a name="remarks"></a>Notes  
  
## <a name="lock-types"></a>Types de verrouillage  
  
|Nom du verrou|Valeur|Description|  
|---------------|-----------|-----------------|  
|LOCK_NONE|0x0000000|Aucun verrou.|  
|LOCK_SESSION_LOCK|0x0000001|Session inactive ; n'interfère pas avec les autres verrous.|  
|LOCK_READ|0x0000002|Verrou de lecture durant le traitement.|  
|LOCK_WRITE|0x0000004|Verrou d'écriture durant le traitement.|  
|LOCK_COMMIT_READ|0x0000008|Verrou de validation, partagé.|  
|LOCK_COMMIT_WRITE|0x0000010|Verrou de validation, exclusif.|  
|LOCK_COMMIT_ABORTABLE|0x0000020|Abandon lors de la validation.|  
|LOCK_COMMIT_INPROGRESS|0x0000040|Validation en cours.|  
|LOCK_INVALID|0x0000080|Verrou non valide.|  
  
## <a name="see-also"></a>Voir aussi  
 [XML for Analysis ensembles de lignes de schéma](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  
