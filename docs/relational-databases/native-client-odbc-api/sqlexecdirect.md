---
title: SQLExecDirect | Documents Microsoft
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-odbc-api
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: SQLExecDirect function
ms.assetid: e7c2a5b5-83f4-4c72-9aca-7b9fb4748b11
caps.latest.revision: "13"
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 686833caa785837d269ce52b51994838f929c0d6
ms.sourcegitcommit: a0aa5e611a0e6ebb74ac1e2f613e8916dc7a7617
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2018
---
# <a name="sqlexecdirect"></a>SQLExecDirect
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  Si l’attribut d’instruction SQL_SOPT_SS_PARAM_FOCUS n’est pas égal à 0, SQLExecDirect retourne SQL_ERROR et génère un enregistrement de diagnostic avec SQLSTATE = HY024 et le message « valeur d’attribut non valide, SQL_SOPT_SS_PARAM_FOCUS (doit être le zéro au moment de l’exécution) ». Pour plus d’informations sur SQL_SOPT_SS_PARAM_FOCUS, consultez [SQLSetStmtAttr](../../relational-databases/native-client-odbc-api/sqlsetstmtattr.md).  
  
 Pour plus d’informations sur les paramètres table, consultez [paramètres table &#40; ODBC &#41;](../../relational-databases/native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).  
  
## <a name="see-also"></a>Voir aussi  
 [SQLExecDirect](http://go.microsoft.com/fwlink/?LinkId=80709)   
 [Détails d’implémentation API ODBC](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
