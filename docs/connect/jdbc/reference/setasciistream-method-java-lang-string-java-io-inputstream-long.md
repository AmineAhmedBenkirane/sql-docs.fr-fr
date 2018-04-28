---
title: Méthode entre setAsciiStream flux octets - long) | Documents Microsoft
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
ms.assetid: 6bc486cd-e432-4057-8789-9957ba23dd30
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b320b7f27aefc4605fc4936aa6435df79360f606
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="setasciistream-method-javalangstring-javaioinputstream-long"></a>Méthode setAsciiStream (java.lang.String, java.io.InputStream, long)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Définit le paramètre désigné dans le flux d’entréespécifié, qui disposera du nombre spécifié d’octets.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public final void setAsciiStream(java.lang.String parameterName,  
                                java.io.InputStream x,  
                                long length)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *parameterName*  
  
 A **chaîne** qui contient le nom du paramètre.  
  
 *x*  
  
 Un objet InputStream.  
  
 *length*  
  
 A **long** qui indique le nombre d’octets.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode setAsciiStream est spécifiée par la méthode setAsciiStream dans l’interface java.sql.PreparedStatement.  
  
 Si la longueur du flux de données est différente de celui spécifié dans le *longueur* paramètre, le pilote JDBC lève une exception lorsque la ligne est mise à jour ou insérée.  
  
 Si la longueur du flux de données est inconnue, la *longueur* paramètre peut être défini sur -1 pour indiquer que le pilote doit accepter le flux, quelle que soit sa longueur. Avec sqljdbc4.jar, nous vous recommandons d’utiliser la méthode JDBC 4.0 [méthode setAsciiStream (java.lang.String, java.io.InputStream)](../../../connect/jdbc/reference/setasciistream-method-java-lang-string-java-io-inputstream.md) lorsque l’application veut mettre à jour la colonne à partir d’un flux dont la longueur est inconnue.  
  
## <a name="see-also"></a>Voir aussi  
 [setAsciiStream &#40;SQLServerCallableStatement&#41;](../../../connect/jdbc/reference/setasciistream-sqlservercallablestatement.md)   
 [SQLServerCallableStatement, membres](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)  
  
  
