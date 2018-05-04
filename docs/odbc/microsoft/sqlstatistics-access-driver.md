---
title: SQLStatistics (pilote Access) | Documents Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: odbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Access driver [ODBC], SQLStatistics
- SQLStatistics function [ODBC], Access Driver
ms.assetid: 6117ac77-1020-4f0c-8eed-e671c34c1f21
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f8ccb5783183d27fb01d2b94f377d71300a7446d
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="sqlstatistics-access-driver"></a>SQLStatistics (pilote Access)
> [!NOTE]  
>  Cette rubrique fournit des informations spécifiques au pilote Access. Pour obtenir des informations générales sur cette fonction, consultez la rubrique appropriée sous [référence de l’API ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
|Colonne|Commentaires|  
|------------|--------------|  
|TABLE_QUALIFIER|Le chemin d’accès à un fichier de base de données est retournée pour Microsoft Access.<br /><br /> Recherche de correspondance n’est pas pris en charge dans les *szTableQualifier* argument.|  
|TABLE_OWNER|Valeur NULL est retournée dans cette colonne, car le nom du propriétaire n’est pas pris en charge.|  
|TABLE_NAME|Nom de table et sans délimitation.<br /><br /> Recherche de correspondance n’est pas pris en charge dans les *szTableName* argument.|  
|INDEX_QUALIFIER|NULL est toujours retournée.|  
|INDEX_NAME|Index dépendant.|  
|TYPE|Uniquement SQL_TABLE_STAT ou SQL_INDEX_OTHER sera retourné pour le TYPE.|  
|SEQ_IN_INDEX|Index dépendant.|  
|COLUMN_NAME|Index dépendant.|  
|COLLATION|Index dépendant.|  
|CARDINALITY|Renvoyé uniquement pour Microsoft Access.|  
|PAGES|NULL est toujours retournée.|  
  
 Le filtrage est basé sur l’unicité (le *fUnique* argument). Le *fAccuracy* paramètre est ignoré.
