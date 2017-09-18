---
title: "setAutoCommit (méthode) (SQLServerConnection) | Documents Microsoft"
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
- SQLServerConnection.setAutoCommit
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: db1e22d2-e53f-474e-8c99-cb1fff7f491a
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: f1549693ac6b4e558c2fc86b29dc6aaa6122c235
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# setAutoCommit (méthode) (SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Définit le mode de validation automatique pour cet [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objet à l’état donné.  
  
## Syntaxe  
  
```  
  
public void setAutoCommit(boolean value)  
```  
  
#### Paramètres  
 *valeur*  
  
 **true** pour activer le mode de validation automatique pour la connexion, **false** pour la désactiver.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Notes  
 Cette méthode setAutoCommit est spécifiée par la méthode setAutoCommit dans l’interface java.sql.Connection.  
  
 Si une connexion est en mode de validation automatique, toutes ses instructions SQL sont exécutées et validées en tant que transactions individuelles. Dans le cas contraire, ses instructions SQL sont regroupées dans des transactions qui sont terminent par un appel à la [validation](../../../connect/jdbc/reference/commit-method-sqlserverconnection.md) méthode ou la [rollback](../../../connect/jdbc/reference/rollback-method-sqlserverconnection.md) (méthode). Par défaut, les nouvelles connexions sont en mode de validation automatique.  
  
 La validation se produit à la fin de l'instruction ou à l'exécution suivante, selon l'opération qui se produit en premier. Dans le cas d’instructions qui retournent un [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) de l’objet, l’instruction se termine lorsque la dernière ligne du jeu de résultats a été récupérée, ou lorsque le jeu de résultats a été fermé. Dans les cas plus avancés, une instruction unique peut retourner plusieurs résultats en plus des valeurs de paramètre de sortie. Dans ces cas, la validation se produit lorsque tous les résultats et valeurs de paramètre de sortie ont été récupérés.  
  
 Lorsque le mode de validation automatique est **false**, le pilote JDBC implicitement démarre une nouvelle transaction après chaque validation.  
  
> [!NOTE]  
>  Si cette méthode est appelée au cours d'une transaction, la transaction est validée.  
  
## Voir aussi  
 [Membres de SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection, classe](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  