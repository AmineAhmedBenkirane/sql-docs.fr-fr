---
title: "Méthode executeUpdate (java.lang.String, int[]) | Documents Microsoft"
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
- SQLServerStatement.executeUpdate (java.lang.String, int[])
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 7b3d5b60-4285-4047-b13e-106754ca0d98
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 60e6995abe98bb45c682f251189a6a307334d87b
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="executeupdate-method-javalangstring-int"></a>Méthode executeUpdate (java.lang.String, int[])
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Exécute l’instruction SQL fournie et signale [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] que les clés générées automatiquement qui sont indiquées dans le tableau spécifié doivent être accessibles pour la récupération.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public final int executeUpdate(java.lang.String sql,  
                               int[] columnIndexes)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *SQL*  
  
 A **chaîne** qui contient une instruction SQL.  
  
 *columnIndexes*  
  
 Tableau de int qui indique les index de colonne des clés générées automatiquement qui doivent être disponibles.  
  
## <a name="return-value"></a>Valeur retournée  
 Un **int** qui indique le nombre de lignes affectées ou 0 si vous utilisez une instruction DDL.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode executeUpdate est spécifiée par la méthode executeUpdate dans l’interface java.sql.Statement.  
  
 Si l’exécution d’une procédure stockée entraîne un nombre de mises à jour qui est supérieur à un, ou qui génère plusieurs jeux de résultats, utilisez le [exécuter](../../../connect/jdbc/reference/execute-method-sqlserverstatement.md) méthode à exécuter la procédure stockée.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode executeUpdate &#40; SQLServerStatement &#41;](../../../connect/jdbc/reference/executeupdate-method-sqlserverstatement.md)   
 [Membres de SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement, classe](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  

