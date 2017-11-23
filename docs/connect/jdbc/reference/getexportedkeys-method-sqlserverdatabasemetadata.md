---
title: "Méthode getExportedKeys (SQLServerDatabaseMetaData) | Documents Microsoft"
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
apiname: SQLServerDatabaseMetaData.getExportedKeys
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 26888e61-b243-4a1b-922c-c0a451dcff4d
caps.latest.revision: "15"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 78a2ace3784458d21546379f7073091832af1496
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2017
---
# <a name="getexportedkeys-method-sqlserverdatabasemetadata"></a>Méthode getExportedKeys (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère une description des colonnes de clés étrangères qui référencent les colonnes de clés primaires de la table donnée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public java.sql.ResultSet getExportedKeys(java.lang.String cat,  
                                          java.lang.String schema,  
                                          java.lang.String table)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *CAT*  
  
 A **chaîne** qui contient le nom du catalogue.  
  
 *schéma*  
  
 A **chaîne** qui contient le nom du schéma.  
  
 *table*  
  
 A **chaîne** qui contient le nom de table.  
  
## <a name="return-value"></a>Valeur retournée  
 A [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) objet.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode getExportedKeys est spécifiée par la méthode getExportedKeys dans l’interface java.sql.DatabaseMetaData.  
  
 Le jeu de résultats retourné par la méthode getExportedKeys contient les informations suivantes :  
  
|Nom|Type| Description|  
|----------|----------|-----------------|  
|PKTABLE_CAT|**Chaîne**|Nom du catalogue qui contient la table de clés primaires.|  
|PKTABLE_SCHEM|**Chaîne**|Nom du schéma de la table de clés primaires.|  
|PKTABLE_NAME|**Chaîne**|Nom de la table de clés primaires.|  
|PKCOLUMN_NAME|**Chaîne**|Nom de colonne de la clé primaire.|  
|FKTABLE_CAT|**Chaîne**|Nom du catalogue qui contient la table de clés étrangères.|  
|FKTABLE_SCHEM|**Chaîne**|Nom du schéma de la table de clés étrangères.|  
|FKTABLE_NAME|**Chaîne**|Nom de la table de clés étrangères.|  
|FKCOLUMN_NAME|**Chaîne**|Nom de colonne de la clé étrangère.|  
|KEY_SEQ|**courte**|Numéro séquentiel de la colonne dans une clé primaire multicolonne.|  
|UPDATE_RULE|**courte**|Action appliquée à la clé étrangère lorsque l'opération SQL correspond à une mise à jour. Il peut prendre l’une des valeurs suivantes :<br /><br /> importedKeyNoAction (3)<br /><br /> importedKeyCascade (0)<br /><br /> importedKeySetNull (2)<br /><br /> importedKeySetDefault (4)<br /><br /> importedKeyRestrict (1)|  
|DELETE_RULE|**courte**|Action appliquée à la clé étrangère lorsque l'opération SQL correspond à une suppression. Il peut prendre l’une des valeurs suivantes :<br /><br /> importedKeyNoAction (3)<br /><br /> importedKeyCascade (0)<br /><br /> importedKeySetNull (2)<br /><br /> importedKeySetDefault (4)<br /><br /> importedKeyRestrict (1)|  
|FK_NAME|**Chaîne**|Nom de la clé étrangère.|  
|PK_NAME|**Chaîne**|Nom de la clé primaire.|  
|DEFERRABILITY|**courte**|Indique si l'évaluation de la contrainte de clé étrangère peut être différée jusqu'à une opération de validation. Il peut prendre l’une des valeurs suivantes :<br /><br /> importedKeyInitiallyDeferred (5)<br /><br /> importedKeyInitiallyImmediate (6)<br /><br /> importedKeyNotDeferrable (7)|  
  
> [!NOTE]  
>  Pour plus d’informations sur les données retournées par la méthode getExportedKeys, consultez « sp_fkeys (Transact-SQL) » dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] la documentation en ligne.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser la méthode getExportedKeys pour renvoyer des informations sur toutes les clés étrangères qui référencent les clés primaires de la table Person.Contact dans le [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal_md.md)] base de données exemple.  
  
```  
public static void executeGetExportedKeys(Connection con) {  
   try {  
      DatabaseMetaData dbmd = con.getMetaData();  
      ResultSet rs = dbmd.getExportedKeys("AdventureWorks", "Person", "Contact");  
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
  
  
