---
title: "Méthode updateCharacterStream (java.io.Reader, int) | Documents Microsoft"
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
apiname: SQLServerResultSet.updateCharacterStream (java.lang.String, java.io.Reader, int)
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 08cfc4e0-83f0-4f2f-ac55-b381f34fe67f
caps.latest.revision: "22"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 32cfd203e7b0d97a4141399b4ada12ad5c790c60
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2017
---
# <a name="updatecharacterstream-method-javalangstring-javaioreader-int"></a>Méthode updateCharacterStream (java.lang.String, java.io.Reader, int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Met à jour la colonne désignée avec une valeur de flux de caractères, qui dispose du nombre spécifié de caractères.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public void updateCharacterStream(java.lang.String columnName,  
                                  java.io.Reader readerValue,  
                                  int length)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *columnName*  
  
 A **chaîne** qui contient le nom de colonne.  
  
 *readerValue*  
  
 Un objet de lecteur.  
  
 *length*  
  
 Un **int** qui indique la longueur du flux de données.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode updateCharacterStream est spécifiée par la méthode updateCharacterStream dans l’interface java.sql.ResultSet.  
  
 Cette méthode passe les caractères Unicode à partir d’un objet lecteur de texte sélectionné et les colonnes binary. Cela inclut toutes les colonnes de texte et **binaire**, **varbinary**, **varbinary (max)**, **image**, et **xml**colonnes, mais pas **udt** colonnes.  
  
 Si la longueur du flux de données est différente de celui spécifié dans le *longueur* paramètre, le pilote JDBC lève une exception lorsque la ligne est mise à jour ou insérée.  
  
 Si la longueur du flux de données est inconnue, la *longueur* paramètre peut être défini sur -1 pour indiquer que le pilote doit accepter le flux, quelle que soit sa longueur. Avec sqljdbc4.jar, nous vous recommandons d’utiliser la méthode JDBC 4.0 [updateCharacterStream méthode &#40;java.lang.String, java.io.Reader &#41;](../../../connect/jdbc/reference/updatecharacterstream-method-java-lang-string-java-io-reader.md) lorsque l’application veut mettre à jour la colonne à partir d’un flux dont la longueur est inconnu.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode updateCharacterStream &#40; SQLServerResultSet &#41;](../../../connect/jdbc/reference/updatecharacterstream-method-sqlserverresultset.md)   
 [Membres de SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet, classe](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
