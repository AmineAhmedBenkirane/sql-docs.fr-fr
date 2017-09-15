---
title: "L’écriture de ODBC 3.x pilotes | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- upgrading drivers [ODBC]
- ODBC drivers [ODBC], upgrading
- backward compatibility [ODBC], drivers
- compatibility [ODBC], drivers
ms.assetid: 9b75f59b-623f-4711-9ca2-e751b3622e00
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 41ca6ddf1535899ed8e5e0f065cf2f5f0ca19dca
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="writing-odbc-3x-drivers"></a>L’écriture ODBC 3.x pilotes
Le tableau suivant présente la prise en charge de la fonction dans une ODBC 3. *x* pilote et une application ODBC et le mappage effectuée par le Gestionnaire de pilotes lorsque les fonctions sont appelées par rapport à un ODBC 3.* x* pilote.  
  
|Fonction|Pris en charge<br /><br /> par un<br /><br /> ODBC 3. *x*<br /><br /> pilote ?|Pris en charge<br /><br /> par un<br /><br /> ODBC 3. *x*<br /><br /> application ?|Mappé/prise en charge<br /><br /> par la version ODBC 3. *x*<br /><br /> Gestionnaire de pilotes à<br /><br /> un ODBC 3. *x* pilote ?|  
|--------------|----------------------------------------------------|---------------------------------------------------------|---------------------------------------------------------------------------------------------|  
|**SQLAllocConnect**|Non|Aucun [1]|Oui|  
|**SQLAllocEnv**|Non|Aucun [1]|Oui|  
|**SQLAllocHandle**|Oui|Oui|Non|  
|**SQLAllocStmt**|Non|Aucun [1]|Oui|  
|**SQLBindCol**|Oui|Oui|Non|  
|**SQLBindParam**|Non|Oui [2]|Oui|  
|**SQLBindParameter**|Oui|Oui|Non|  
|**SQLBrowseConnect**|Oui|Oui|Non|  
|**SQLBulkOperations**|Oui|Oui|Non|  
|**SQLCancel**|Oui|Oui|Non|  
|**SQLCloseCursor**|Oui|Oui|Non|  
|**SQLColAttribute**|Oui|Oui|Non|  
|**SQLColAttributes**|Aucun [3]|Non|Oui|  
|**SQLColumnPrivileges**|Oui|Oui|Non|  
|**SQLColumns**|Oui|Oui|Non|  
|**SQLConnect**|Oui|Oui|Non|  
|**SQLCopyDesc**|Oui|Oui|Oui [4]|  
|**SQLDataSources**|Non|Oui|Oui|  
|**SQLDescribeCol**|Oui|Oui|Non|  
|**SQLDescribeParam**|Oui|Oui|Non|  
|**SQLDisconnect**|Oui|Oui|Non|  
|**SQLDriverConnect**|Oui|Oui|Non|  
|**SQLDrivers**|Non|Oui|Oui|  
|**SQLEndTran**|Oui|Oui|Non|  
|**SQLError**|Non|Aucun [1]|Oui|  
|**SQLExecDirect**|Oui|Oui|Non|  
|**SQLExecute**|Oui|Oui|Non|  
|**SQLExtendedFetch**|Oui|Non|Non|  
|**SQLFetch**|Oui|Oui|Non|  
|**SQLFetchScroll**|Oui|Oui|Non|  
|**SQLForeignKeys**|Oui|Oui|Non|  
|**SQLFreeConnect**|Non|Oui [1]|Oui|  
|**SQLFreeEnv**|Non|Oui [1]|Oui|  
|**SQLFreeHandle**|Oui|Oui|Non|  
|**SQLFreeStmt**|Oui|Oui|Non|  
|**SQLGetConnectAttr**|Oui|Oui|Non|  
|**SQLGetConnectOption**|Aucun [5]|Aucun [1]|Oui|  
|**SQLGetCursorName**|Oui|Oui|Non|  
|**SQLGetData**|Oui|Oui|Non|  
|**SQLGetDescField**|Oui|Oui|Non|  
|**SQLGetDescRec**|Oui|Oui|Non|  
|**SQLGetDiagField**|Oui|Oui|Non|  
|**SQLGetDiagRec**|Oui|Oui|Non|  
|**Cas**|Oui|Oui|Non|  
|**SQLGetFunctions**|Aucun [6]|Oui|Oui|  
|**SQLGetInfo**|Oui|Oui|Non|  
|**SQLGetStmtAttr**|Oui|Oui|Non|  
|**SQLGetStmtOption**|Aucun [5]|Aucun [1]|Oui|  
|**SQLGetTypeInfo**|Oui|Oui|Non|  
|**SQLMoreResults**|Oui|Oui|Non|  
|**SQLNativeSql**|Oui|Oui|Non|  
|**SQLNumParams**|Oui|Oui|Non|  
|**SQLNumResultCols**|Oui|Oui|Non|  
|**SQLParamData**|Oui|Oui|Non|  
|**SQLParamOptions**|Non|Non|Oui|  
|**SQLPrepare**|Oui|Oui|Non|  
|**SQLPrimaryKeys**|Oui|Oui|Non|  
|**SQLProcedureColumns**|Oui|Oui|Non|  
|**SQLProcedures**|Oui|Oui|Non|  
|**SQLPutData**|Oui|Oui|Non|  
|**SQLRowCount**|Oui|Oui|Non|  
|**SQLSetConnectAttr**|Oui|Oui|Non|  
|**SQLSetConnectOption**|Aucun [5]|Aucun [1]|Oui|  
|**SQLSetCursorName**|Oui|Oui|Non|  
|**SQLSetDescField**|Oui|Oui|Non|  
|**SQLSetDescRec**|Oui|Oui|Non|  
|**SQLSetEnvAttr**|Oui|Oui|Non|  
|**SQLSetPos**|Oui|Oui|Non|  
|**SQLSetParam**|Non|Non|Oui|  
|**SQLSetScrollOption**|Oui|Oui|Non|  
|**SQLSetStmtAttr**|Oui|Oui|Non|  
|**SQLSetStmtOption**|Aucun [5]|Aucun [1]|Oui|  
|**SQLSpecialColumns**|Oui|Oui|Non|  
|**SQLStatistics**|Oui|Oui|Non|  
|**SQLTablePrivileges**|Oui|Oui|Non|  
|**SQLTables**|Oui|Oui|Non|  
|**SQLTransact**|Non|Aucun [1]|Oui|  
  
 [1], cette fonction est déconseillée dans ODBC 3. *x*. ODBC 3. *x* applications ne doivent pas utiliser cette fonction. Toutefois, un Open Group ou une application compatible ISO CLI peut appeler cette fonction.  
  
 [2] ODBC 3. *x* les applications doivent utiliser **SQLBindParameter** au lieu de **SQLBindParam**. Toutefois, un Open Group ou une application compatible ISO CLI peut appeler cette fonction.  
  
 [3] les rédacteurs de pilotes sont à noter que l’API ODBC 2. *x* SQL_COLUMN_PRECISION, SQL_COLUMN_SCALE et SQL_COLUMN_LENGTH doivent être pris en charge avec des attributs de colonne **SQLColAttribute**.  
  
 [4] **SQLCopyDesc** est partiellement implémentée par le Gestionnaire de pilotes lorsqu’un descripteur est copié sur les connexions qui appartiennent à différents pilotes. Les pilotes sont requis pour prendre en charge **SQLCopyDesc** entre deux de leurs propres connexions. Les fonctions telles que **SQLDrivers**, qui sont implémentées exclusivement par le Gestionnaire de pilotes, ne s’affichent pas dans cette liste.  
  
 [5] dans certaines circonstances, les pilotes peut-être prendre en charge cette fonction. Pour plus d’informations, consultez la page de référence de cette fonction.  
  
 [6], le pilote peut choisir de prendre en charge **SQLGetFunctions** si l’ensemble de fonctions que le pilote prend en charge varie en fonction de la connexion à la connexion.
