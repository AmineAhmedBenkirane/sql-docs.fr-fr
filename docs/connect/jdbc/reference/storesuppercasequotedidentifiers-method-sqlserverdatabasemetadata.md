---
title: Méthode storesUpperCaseQuotedIdentifiers | Documents Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: jdbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
apiname:
- SQLServerDatabaseMetaData.storesUpperCaseQuotedIdentifiers
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 936ec140-2597-44e6-82d3-3994a676ee35
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 3c3c6a2def5e9111d5f7ce8c57b5cd6d1f2da1c7
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="storesuppercasequotedidentifiers-method-sqlserverdatabasemetadata"></a>Méthode storesUpperCaseQuotedIdentifiers (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère les informations déterminant si cette base de données traite les identificateurs SQL à casse mixte qui se trouvent entre guillemets comme non sensibles à la casse et les stocke en majuscules.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public boolean storesUpperCaseQuotedIdentifiers()  
```  
  
## <a name="return-value"></a>Valeur retournée  
 **true** si les identificateurs sont stockés en majuscules. Dans le cas contraire, la valeur est **false**.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode storesUpperCaseQuotedIdentifiers est spécifiée par la méthode storesUpperCaseQuotedIdentifiers dans l’interface java.sql.DatabaseMetaData.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [Membres de SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData, classe](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
