---
title: "Méthode setBigDecimal (SQLServerCallableStatement) | Documents Microsoft"
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
- SQLServerCallableStatement.setBigDecimal
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: b50a920c-3839-40f0-9411-c60bbc2a9f34
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 0f54854c66ca0dc2d438a625e8ae4e8bd9701855
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="setbigdecimal-method-sqlservercallablestatement"></a>Méthode setBigDecimal (SQLServerCallableStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Définit le nombre de paramètre désigné à l’objet BigDecimal donné.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public void setBigDecimal(java.lang.String sCol,  
                          java.math.BigDecimal bd)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *sCol*  
  
 A **chaîne** qui contient le nom du paramètre.  
  
 *BD*  
  
 Un objet BigDecimal.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode setBigDecimal est spécifiée par la méthode setBigDecimal dans l’interface java.sql.CallableStatement.  
  
## <a name="see-also"></a>Voir aussi  
 [Membres de SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [SQLServerCallableStatement, classe](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  

