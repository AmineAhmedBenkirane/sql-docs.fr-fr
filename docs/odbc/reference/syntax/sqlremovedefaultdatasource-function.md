---
title: Fonction de SQLRemoveDefaultDataSource | Documents Microsoft
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SQLRemoveDefaultDataSource
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLRemoveDefaultDataSource
helpviewer_keywords:
- SQLRemoveDefaultDataSource function [ODBC]
ms.assetid: db803266-57df-4864-a41b-901247549c1f
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: ed4db21dce5cf5da5234f4906116c93f9a4ea735
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="sqlremovedefaultdatasource-function"></a>SQLRemoveDefaultDataSource (fonction)
**Mise en conformité**  
 Version introduite : ODBC 1.0, déconseillée  
  
 **Résumé**  
 Dans ODBC 3.0, le **SQLRemoveDefaultDataSource** fonction a été remplacée par un appel à [SQLConfigDataSource](../../../odbc/reference/syntax/sqlconfigdatasource-function.md) avec un *fréquents* argument de ODBC_REMOVE_DEFAULT_DSN. Si une API ODBC 2*.x* programme d’installation appelle cette fonction, le programme d’installation ODBC mappera à ce qui suit **SQLConfigDataSource** appeler :  
  
```  
SQLConfigDataSource (NULL, ODBC_REMOVE_DEFAULT_DSN, NULL, NULL)  
```

