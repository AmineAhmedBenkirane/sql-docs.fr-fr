---
title: Mappage de SQLFreeStmt | Documents Microsoft
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: reference
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQLFreeStmt function [ODBC], mapping
- mapping deprecated functions [ODBC], SQLFreeStmt
ms.assetid: 267d95f2-4f0c-47ab-9411-5afe105215a2
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 422a59b663d4809ba26c6cb524c6845c78e3907f
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="sqlfreestmt-mapping"></a>Mappage de SQLFreeStmt
Lorsqu’une application appelle **SQLFreeStmt** avec un *Option* argument de SQL_DROP via un ODBC 3*.x* pilote, l’appel à  
  
```  
SQLFreeStmt(hstmt, SQL_DROP)   
```  
  
 est mappée à  
  
```  
SQLFreeHandle(SQL_HANDLE_STMT,Handle)  
```  
  
 avec la *gérer* affectée à la valeur de l’argument *hstmt*.
