---
title: "updateBinaryStream (méthode) (java.io.InputStream) | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56883144-26a0-4f45-ad36-4f616369af3e
caps.latest.revision: 16
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 1fa688afc52a05664525a165930dca7ed7ac4b49
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="updatebinarystream-method-javalangstring-javaioinputstream"></a>Méthode updateBinaryStream (java.lang.String, java.io.InputStream)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Met à jour la colonne désignée avec la valeur de flux binaire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public void updateBinaryStream(java.lang.String columnLabel,  
                               java.io.InputStream x)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *columnLabel*  
  
 A **chaîne** qui contient l’étiquette de colonne.  
  
 *x*  
  
 Un objet InputStream.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode updateBinaryStream est spécifiée par la méthode updateBinaryStream dans l’interface java.sql.ResultSet.  
  
 À l’aide de cette méthode pour le **image**, **texte**, et **ntext** les types de données SQL Server peuvent avoir un impact sur les performances.  
  
 Cette méthode passe les octets à partir d’un objet InputStream sélectionné [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] colonnes binaires telles que binary, varbinary, varbinary (max), image, xml et udt. La mise à jour de colonnes de caractères n'est pas prise en charge avec cette méthode. Pour mettre à jour des colonnes de type caractère avec un InputStream, utilisez le [updateAsciiStream](../../../connect/jdbc/reference/updateasciistream-method-sqlserverresultset.md) (méthode).  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode updateBinaryStream &#40; SQLServerResultSet &#41;](../../../connect/jdbc/reference/updatebinarystream-method-sqlserverresultset.md)   
 [Membres de SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet, classe](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  

