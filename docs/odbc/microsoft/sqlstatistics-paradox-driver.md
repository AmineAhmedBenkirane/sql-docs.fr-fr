---
title: SQLStatistics (pilote Paradox) | Documents Microsoft
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
ms.topic: article
helpviewer_keywords:
- Paradox driver [ODBC], SQLStatistics
- SQLStatistics function [ODBC], Paradox Driver
ms.assetid: 886cab83-d599-4fbc-9c88-e8cb833aac4b
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 99e4c95ee501908007f93b5facd2a2bf3b4963d3
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="sqlstatistics-paradox-driver"></a>SQLStatistics (pilote Paradox)
> [!NOTE]  
>  Cette rubrique fournit des informations spécifiques au pilote de Corel. Pour obtenir des informations générales sur cette fonction, consultez la rubrique appropriée sous [référence de l’API ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
|Colonne|Commentaires|  
|------------|--------------|  
|TABLE_QUALIFIER|Le chemin d’accès à un répertoire.<br /><br /> Recherche de correspondance n’est pas pris en charge dans les *szTableQualifier* argument.|  
|TABLE_OWNER|Valeur NULL est retournée dans cette colonne, car le nom du propriétaire n’est pas pris en charge.|  
|TABLE_NAME|Nom de table et sans délimitation.<br /><br /> Recherche de correspondance n’est pas pris en charge dans les *szTableName* argument.|  
|INDEX_QUALIFIER|NULL est toujours retournée.|  
|INDEX_NAME|Index dépendant.|  
|TYPE|Uniquement SQL_TABLE_STAT ou SQL_INDEX_OTHER sera retourné pour le TYPE.|  
|SEQ_IN_INDEX|Index dépendant.|  
|COLUMN_NAME|Index dépendant.|  
|COLLATION|Index dépendant.|  
|PAGES|NULL est toujours retournée.|  
  
 Le filtrage est basé sur l’unicité (le *fUnique* argument). Le *fAccuracy* paramètre est ignoré.
