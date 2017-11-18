---
title: "getConnection, méthode (java.lang.String, java.lang.String) | Documents Microsoft"
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
- SQLServerDataSource.getConnection (java.lang.String, java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 78db89d6-a8a0-4116-8885-548e627220ed
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 39b7a3bb2896ff308fc58510443bd54c487c77f8
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="getconnection-method-javalangstring-javalangstring"></a>Méthode getConnection (java.lang.String, java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Tente d’établir une connexion avec les données source que ce [SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md) objet représente à l’aide du nom d’utilisateur et un mot de passe.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public java.sql.Connection getConnection(java.lang.String username,  
                                         java.lang.String password)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *nom d’utilisateur*  
  
 A **chaîne** qui contient le nom d’utilisateur.  
  
 *mot de passe*  
  
 A **chaîne** qui contient le mot de passe.  
  
## <a name="return-value"></a>Valeur retournée  
 A [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objet.  
  
## <a name="exceptions"></a>Exceptions  
 java.sql.SQLException  
  
## <a name="remarks"></a>Notes  
 Cette méthode getConnection est spécifiée par la méthode getConnection dans l’interface javax.sql.DataSource.  
  
 Appel de la getConnection méthode avec un nom d’utilisateur ou le mot de passe remplacera les propriétés de nom et mot de passe d’utilisateur qui sont définies sur la classe SQLServerDataSource lors de l’initialisation de l’objet SQLServerConnection. Par exemple, si l’appelant a appelé [setUser](../../../connect/jdbc/reference/setuser-method-sqlserverdatasource.md) et [setPassword](../../../connect/jdbc/reference/setpassword-method-sqlserverdatasource.md) sur la source de données, puis appelle getConnection et nom d’utilisateur fournit une valeur non null ou un mot de passe non null, le nom d’utilisateur et un mot de passe défini par l’instruction setUser et setPassword seront remplacés par le nom d’utilisateur et un mot de passe transmis dans getConnection.  
  
> [!NOTE]  
>  Le nom d’utilisateur et un mot de passe qui sont définies à l’intérieur de l’URL à l’aide d’un appel à la [setURL](../../../connect/jdbc/reference/seturl-method-sqlserverdatasource.md) méthode n’est pas modifiée dans ce cas.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode getConnection &#40; SQLServerDataSource &#41;](../../../connect/jdbc/reference/getconnection-method-sqlserverdatasource.md)   
 [Membres de SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource, classe](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  

