---
title: Méthode getCharacterStream (java.lang.String) | Documents Microsoft
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
- SQLServerResultSet.getCharacterStream (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: cdddc572-05c1-480d-b3e5-28270001575c
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 31da9e5f4dc9fc6faf9db080e02c9b304e2ba116
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="getcharacterstream-method-javalangstring"></a>Méthode getCharacterStream (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère la valeur du nom de colonne désigné dans la ligne actuelle de ce [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) objet en tant qu’objet java.io.Reader.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public java.io.Reader getCharacterStream(java.lang.String columnName)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *columnName*  
  
 A **chaîne** qui contient le nom de colonne.  
  
## <a name="return-value"></a>Valeur retournée  
 Un objet de lecteur.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode getCharacterStream est spécifiée par la méthode getCharacterStream dans l’interface java.sql.ResultSet.  
  
 Cette méthode est en lecture seule [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] des types de données de caractères Unicode tels que nchar, nvarchar, nvarchar (max) et ntext. Tous les autres types de données, dont les types de caractères ASCII, entraînent la levée d'une exception. Pour lire les types de données ASCII, utilisez le [getAsciiStream](../../../connect/jdbc/reference/getasciistream-method-sqlserverresultset.md) (méthode).  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode getCharacterStream &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/getcharacterstream-method-sqlserverresultset.md)   
 [Membres de SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet, classe](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
