---
title: "Méthode setCharacterStream (int, java.io.Reader, long) | Documents Microsoft"
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
ms.assetid: cb6ac7f5-81ae-4cb7-87c8-cbee40d278c5
caps.latest.revision: "27"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7724a7350ed9e8ce8b1b2ff6990eaaaf4b6d01b2
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2017
---
# <a name="setcharacterstream-method-int-javaioreader-long"></a>Méthode setCharacterStream (int, java.io.Reader, long)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Définit le paramètre désigné à l’objet java.io.Reader, qui est le nombre de caractères spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public final void setCharacterStream(int parameterIndex,  
                                    java.io.Reader reader,  
                                    long length)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *parameterIndex*  
  
 Un **int** qui indique le nombre de paramètres.  
  
 *lecteur*  
  
 L’objet java.io.Reader qui contient les données Unicode.  
  
 *length*  
  
 A **long** qui indique le nombre de caractères dans le flux de données.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode setCharacterStream est spécifiée par la méthode setCharacterStream dans l’interface java.sql.PreparedStatement.  
  
 Si la longueur du flux de données est différente de celui spécifié dans le *longueur* paramètre, le pilote JDBC lève une exception lorsque la ligne est mise à jour ou insérée.  
  
 Si la longueur du flux de données est inconnue, la *longueur* paramètre peut être défini sur -1 pour indiquer que le pilote doit accepter le flux, quelle que soit sa longueur. Avec sqljdbc4.jar, nous vous recommandons d’utiliser la méthode JDBC 4.0 [setCharacterStream méthode &#40; type int, java.io.Reader &#41;](../../../connect/jdbc/reference/setcharacterstream-method-int-java-io-reader.md) lorsque l’application veut mettre à jour la colonne à partir d’un flux dont la longueur est inconnue.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode setCharacterStream &#40; SQLServerPreparedStatement &#41;](../../../connect/jdbc/reference/setcharacterstream-method-sqlserverpreparedstatement.md)   
 [SQLServerPreparedStatement, membres](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)  
  
  
