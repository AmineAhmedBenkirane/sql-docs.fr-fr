---
title: Méthode getBinaryStream (java.lang.String) | Documents Microsoft
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
- SQLServerResultSet.getBinaryStream (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 149609b5-a6de-4e23-a440-7061775d0899
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 455c307c61112fc10992c74ca15af498aa09c5f5
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="getbinarystream-method-javalangstring"></a>Méthode getBinaryStream (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère la valeur du nom de colonne désigné dans la ligne actuelle de ce [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) objet en tant que flux binaire d’octets non interprétés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public java.io.InputStream getBinaryStream(java.lang.String columnName)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *columnName*  
  
 A **chaîne** qui contient le nom de colonne.  
  
## <a name="return-value"></a>Valeur retournée  
 Un objet InputStream.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode getBinaryStream est spécifiée par la méthode getBinaryStream dans l’interface java.sql.ResultSet.  
  
 Cette méthode peut être utilisée uniquement avec [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] de binary, varbinary, varbinary (max) et image, les types de données. Si vous essayez de l'utiliser avec d'autres types de données, une exception est levée.  
  
 Une fois que cette méthode a obtenu la valeur sous forme de flux, cette valeur peut être lue par segments à partir du flux. Cette méthode convient particulièrement à la récupération de grandes valeurs LONGVARBINARY.  
  
> [!NOTE]  
>  Toutes les données figurant dans le flux retourné doivent être lues avant d'obtenir la valeur de toute autre colonne. L'appel suivant à une méthode getter fermera implicitement le flux. En outre, un flux de données peut retourner 0 lors de la méthode InputStream.available est appelée, si les données est disponible ou non.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode getBinaryStream &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/getbinarystream-method-sqlserverresultset.md)   
 [Membres de SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet, classe](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
