---
title: SQLGetInfo (pilote Paradox) | Documents Microsoft
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
- Paradox driver [ODBC], SQLGetInfo
- SQLGetInfo function [ODBC], Paradox Driver
ms.assetid: 43aab762-68f4-4128-b8f5-8878ea5f1258
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 2f977d823713868a4ae6e8caf004f4a59dcfb36d
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="sqlgetinfo-paradox-driver"></a>SQLGetInfo (pilote Paradox)
> [!NOTE]  
>  Cette rubrique fournit des informations spécifiques au pilote de Corel. Pour obtenir des informations générales sur cette fonction, consultez la rubrique appropriée sous [référence de l’API ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 **SQLGetInfo** prend en charge le type d’informations SQL_FILE_USAGE. La valeur retournée est un entier 16 bits qui indique comment le pilote traite directement les fichiers dans une source de données :  
  
-   SQL_FILE_NOT_SUPPORTED : Le pilote n’est pas un pilote de niveau unique.  
  
-   SQL_FILE_TABLE : Un pilote de niveau unique traite les fichiers dans une source de données en tant que tables.  
  
-   SQL_FILE_QUALIFIER : Un pilote de niveau unique traite les fichiers dans une source de données en tant que qualificateur.  
  
 Le pilote ODBC retourne SQL_FILE_TABLE, car chaque fichier est une table.  
  
## <a name="sqlaltertable"></a>SQL_ALTER_TABLE  
 SQL_AT_ADD_COLUMN &AMP;#124; SQL_AT_DROP_COLUMN  
  
## <a name="sqlddlindex"></a>SQL_DDL_INDEX  
 SQL_DL_CREATE_INDEX  
  
 SQL_DL_DROP_INDEX  
  
## <a name="sqldbmsver"></a>SQL_DBMS_VER  
  
|ISAM|Version|Format des numéros de version|  
|----------|-------------|-------------------------------|  
|Paradox|3.x|03.00.0000|  
||4.x|04.00.0000|  
||5.x|05.00.0000|  
  
## <a name="sqlcatalogusage"></a>SQL_CATALOG_USAGE  
 SQL_QU_DML_STATEMENTS &AMP;#124; SQL_QU_TABLE_DEFINITION &AMP;#124; SQL_QU_INDEX_DEFINITION  
  
## <a name="sqltimedatefunctions"></a>SQL_TIMEDATE_FUNCTIONS  
 SQL_FN_TD_DAYOFMONTH &AMP;#124; SQL_FN_TD_DAYOFWEEK &AMP;#124; SQL_FN_TD_DAYOFYEAR &AMP;#124; SQL_FN_TD_HOUR &AMP;#124; SQL_FN_TD_MINUTE &AMP;#124; SQL_FN_TD_MONTH &AMP;#124; SQL_FN_TD_SECOND &AMP;#124; SQL_FN_TD_WEEK &AMP;#124; SQL_FN_TD_YEAR
