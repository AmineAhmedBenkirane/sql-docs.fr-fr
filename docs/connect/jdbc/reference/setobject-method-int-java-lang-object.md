---
title: "Méthode setObject (int, java.lang.Object) | Documents Microsoft"
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
- SQLServerPreparedStatement.setObject (int, java.lang.Object)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 61f19faa-3006-4a1c-974c-55951e3b3000
caps.latest.revision: 22
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 2116f0662e21e4cb38d60560a680e90e6b2321d9
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="setobject-method-int-javalangobject"></a>Méthode setObject (int, java.lang.Object)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Définit la valeur du paramètre désigné à l'aide de l'objet spécifique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public final void setObject(int index,  
                            java.lang.Object obj)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *index*  
  
 Un **int** qui indique le nombre de paramètres.  
  
 *obj*  
  
 Objet.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode setObject est spécifiée par la méthode setObject dans l’interface java.sql.PreparedStatement.  
  
 Avant d’appeler cette méthode setObject, l’application peut définir le paramètre spécifié en utilisant l’une des méthodes suivantes :  
  
-   Le jeu de\<Type > méthodes de la classe SQLServerPreparedStatement ou de la classe SQLServerCallableStatement  
  
-   Les méthodes setNull de la classe SQLServerPreparedStatement ou SQLServerCallableStatement  
  
-   Le [registerOutParameter](../../../connect/jdbc/reference/registeroutparameter-method-sqlservercallablestatement.md) de la classe SQLServerCallableStatement (méthode)  
  
 Dans ce cas, le type du paramètre est défini automatiquement. Si l’application appelle cette méthode setObject avec une valeur obj NULL, le pilote part du principe que le type du paramètre est celui défini par la méthode appelée précédemment.  
  
 Si la valeur obj est NULL et aucune information de type pour ce paramètre ne peut être déterminée, cette méthode setObject convertit le paramètre spécifié en type CHAR avant de l’envoyer à la base de données.  
  
 À partir de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] version 3.0 du pilote JDBC, le comportement de cette méthode est modifié par la **sendTimeAsDatetime** propriété de connexion ([définissant les propriétés de connexion](../../../connect/jdbc/setting-the-connection-properties.md)) et [ SQLServerDataSource.setSendTimeAsDatetime](../../../connect/jdbc/reference/setsendtimeasdatetime-method-sqlserverdatasource.md).  
  
 Pour plus d’informations, consultez [java.sql.Time configurer comment les valeurs sont envoyées au serveur](../../../connect/jdbc/configuring-how-java-sql-time-values-are-sent-to-the-server.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode setObject &#40; SQLServerPreparedStatement &#41;](../../../connect/jdbc/reference/setobject-method-sqlserverpreparedstatement.md)   
 [Membres de SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)   
 [SQLServerPreparedStatement, classe](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)  
  
  
