---
title: "Méthode getCatalogs (SQLServerDatabaseMetaData) | Documents Microsoft"
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
- SQLServerDatabaseMetaData.getCatalogs
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 7f8bd0f1-f340-4bb9-b559-0a6176124033
caps.latest.revision: 22
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 6f78577e4f2698966afccba5f1f97855076434e9
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="getcatalogs-method-sqlserverdatabasemetadata"></a>Méthode getCatalogs (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère les noms de catalogues disponibles sur le serveur connecté.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public java.sql.ResultSet getCatalogs()  
```  
  
## <a name="return-value"></a>Valeur retournée  
 A [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) objet.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode getCatalogs est spécifiée par la méthode getCatalogs dans l’interface java.sql.DatabaseMetaData.  
  
> [!NOTE]  
>  Dans SQL Azure, vous devez vous connecter à la base de données master pour appeler **SQLServerDatabaseMetaData.getCatalogs**. SQL Azure ne prend pas en charge le retour de l’ensemble des catalogues à partir d’une base de données utilisateur. **SQLServerDatabaseMetaData.getCatalogs** utilise la vue sys.databases pour récupérer les catalogues. Reportez-vous à la discussion des autorisations de [sys.databases (base de données SQL Azure)](http://go.microsoft.com/fwlink/?LinkId=217396) pour comprendre **SQLServerDatabaseMetaData.getCatalogs** comportement dans SQL Azure.  
  
 Le jeu de résultats retourné par la méthode getCatalogs contient les informations suivantes :  
  
|Nom|Type| Description|  
|----------|----------|-----------------|  
|TABLE_CAT|**Chaîne**|Le nom du catalogue, y compris les bases de données système dans [!INCLUDE[msCoName](../../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)].|  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser la méthode getCatalogs pour retourner les noms de toutes les bases de données qui sont contenues dans [!INCLUDE[msCoName](../../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)], y compris les bases de données système.  
  
```  
public static void executeGetCatalogs(Connection con) {  
   try {  
      DatabaseMetaData dbmd = con.getMetaData();  
      ResultSet rs = dbmd.getCatalogs();  
      ResultSetMetaData rsmd = rs.getMetaData();  
  
      // Display the result set data.  
      int cols = rsmd.getColumnCount();  
      while(rs.next()) {  
         for (int i = 1; i <= cols; i++) {  
            System.out.println(rs.getString(i));  
         }  
      }  
      rs.close();  
   }   
  
   catch (Exception e) {  
      e.printStackTrace();  
   }  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [Membres de SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData, classe](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
