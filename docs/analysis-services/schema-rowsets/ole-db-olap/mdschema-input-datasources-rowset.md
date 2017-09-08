---
title: Ensemble de lignes MDSCHEMA_INPUT_DATASOURCES | Documents Microsoft
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
apiname:
- MDSCHEMA_INPUT_DATASOURCES
apitype: NA
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- MDSCHEMA_INPUT_DATASOURCES rowset
ms.assetid: 12482fd5-16e3-4171-9cb0-76d0d4f5308e
caps.latest.revision: 30
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: e105cc8151640f5d5d74d6c7c76cc52edc16a242
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="mdschemainputdatasources-rowset"></a>Ensemble de lignes MDSCHEMA_INPUT_DATASOURCES
  Décrit les sources de données définies dans la base de données.  
  
## <a name="rowset-columns"></a>Colonnes de l'ensemble de lignes  
 L'ensemble de lignes **MDSCHEMA_INPUT_DATASOURCES** contient les colonnes suivantes.  
  
|Nom de colonne|Indicateur de type|Longueur| Description|  
|-----------------|--------------------|------------|-----------------|  
|**CATALOG_NAME**|**DBTYPE_WSTR**||Nom du catalogue auquel appartient cette source de données.|  
|**SCHEMA_NAME**|**DBTYPE_WSTR**||Non pris en charge.|  
|**DATASOURCE_NAME**|**DBTYPE_WSTR**||Nom de l'objet source de données.|  
|**DATASOURCE_TYPE**|**DBTYPE_WSTR**||Type de la source de données. Les valeurs valides sont les suivantes :<br /><br /> **Relationnelle**<br /><br /> **OLAP**|  
|**CREATED_ON**|**DBTYPE_DBTIMESTAMP**||Date de création de la source de données.|  
|**LAST_SCHEMA_UPDATE**|**DBTYPE_DBTIMESTAMP**||Date et heure de la dernière modification de la source de données.|  
|**DESCRIPTION**|**DBTYPE_WSTR**||Description conviviale de l'action.|  
|**DÉLAI D’ATTENTE**|**DBTYPE_UI4**||Délai d'expiration de la source de données.|  
  
 Cet ensemble de lignes de schéma n'est pas trié.  
  
## <a name="restriction-columns"></a>Colonnes de restriction  
 L'ensemble de lignes **MDSCHEMA_INPUT_DATASOURCES** peut être restreint sur les colonnes répertoriées dans le tableau suivant.  
  
|Nom de colonne|Indicateur de type|État de la restriction|  
|-----------------|--------------------|-----------------------|  
|**CATALOG_NAME**|**DBTYPE_WSTR**|Ce paramètre est facultatif.|  
|**SCHEMA_NAME**|**DBTYPE_WSTR**|Ce paramètre est facultatif.|  
|**DATASOURCE_NAME**|**DBTYPE_WSTR**|Ce paramètre est facultatif.|  
|**DATASOURCE_TYPE**|**DBTYPE_WSTR**|Ce paramètre est facultatif.|  
  
## <a name="see-also"></a>Voir aussi  
 [OLE DB pour OLAP Schema Rowsets](../../../analysis-services/schema-rowsets/ole-db-olap/ole-db-for-olap-schema-rowsets.md)  
  
  
