---
title: "Méthode au type registerOutParameter | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SQLServerCallableStatement.registerOutParameter (java.lang.String, int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 5d00242c-4d9c-42cc-86bb-b76f5ef876b8
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 04d85c46a764e0c511635333254964a9b3545b1d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="registeroutparameter-method-javalangstring-int"></a>Méthode registerOutParameter (java.lang.String, int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Inscrit le paramètre OUT avec le nom spécifié en fonction du type JDBC.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public void registerOutParameter(java.lang.String s,  
                                 int n)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *s*  
  
 A **chaîne** qui contient le nom du paramètre.  
  
 *n*  
  
 Code de type JDBC comme défini dans java.sql.Types.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode registerOutParameter est spécifiée par la méthode registerOutParameter dans l’interface java.sql.CallableStatement.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode registerOutParameter &#40; SQLServerCallableStatement &#41;](../../../connect/jdbc/reference/registeroutparameter-method-sqlservercallablestatement.md)   
 [Membres de SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [SQLServerCallableStatement, classe](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  

