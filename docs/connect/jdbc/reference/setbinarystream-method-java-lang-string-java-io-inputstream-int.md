---
title: Méthode à l’entrée de flux de données - long setBinaryStream | Documents Microsoft
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
- SQLServerCallableStatement.setBinaryStream
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 567297bf-5bec-46ae-8264-29639b9b4a06
caps.latest.revision: 21
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d5d98d1f3bfba81c1d51e02c173975177f6b3713
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="setbinarystream-method--javalangstring-javaioinputstream-int"></a>Méthode setBinaryStream (java.lang.String, java.io.InputStream, int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Définit le paramètre désigné selon le flux d'entrée spécifié, qui disposera du nombre spécifique d'octets.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public void setBinaryStream(java.lang.String parameterName,  
                            java.io.InputStream value,  
                            int length)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *parameterName*  
  
 A **chaîne** qui contient le nom du paramètre.  
  
 *valeur*  
  
 Un objet InputStream.  
  
 *length*  
  
 Un **int** qui indique la longueur en octets.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode setBinaryStream est spécifiée par la méthode setBinaryStream dans l’interface java.sql.CallableStatement.  
  
 Si la longueur du flux de données est différente de celui spécifié dans le *longueur* paramètre, le pilote JDBC lève une exception lorsque la ligne est mise à jour ou insérée.  
  
 Si la longueur du flux de données est inconnue, la *longueur* paramètre peut être défini sur -1 pour indiquer que le pilote doit accepter le flux, quelle que soit sa longueur. Avec sqljdbc4.jar, nous vous recommandons d’utiliser la méthode JDBC 4.0 [méthode setBinaryStream (java.lang.String, java.io.InputStream)](../../../connect/jdbc/reference/setbinarystream-method-java-lang-string-java-io-inputstream.md) lorsque l’application veut mettre à jour la colonne à partir d’un flux dont la longueur est inconnue.  
  
## <a name="see-also"></a>Voir aussi  
 [setBinaryStream &#40;SQLServerCallableStatement&#41;](../../../connect/jdbc/reference/setbinarystream-sqlservercallablestatement.md)   
 [SQLServerCallableStatement, membres](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)  
  
  
