---
title: "isBeforeFirst (méthode) (SQLServerResultSet) | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname: SQLServerResultSet.isBeforeFirst
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: e0e2bd28-6949-47dc-b9dd-145ffb337069
caps.latest.revision: "11"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c15e9a81eaad27b21cd9c7ebcf835d9e1ae54023
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2017
---
# <a name="isbeforefirst-method-sqlserverresultset"></a>isBeforeFirst (méthode) (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère si le curseur se trouve avant la première ligne dans cette [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public boolean isBeforeFirst()  
```  
  
## <a name="return-value"></a>Valeur retournée  
 **true** si le curseur se trouve avant la première ligne. **false** si le curseur se trouve à toute autre position ou si le jeu de résultats ne contient aucune ligne.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode isBeforeFirst est spécifiée par la méthode isBeforeFirst dans l’interface java.sql.ResultSet.  
  
 Si cette méthode est utilisée avec des curseurs dynamiques, dont les curseurs en lecture seule avant uniquement, et si la propriété de connexion selectMethod est définie sur « cursor », une exception se produit.  
  
## <a name="see-also"></a>Voir aussi  
 [Membres de SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet, classe](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
