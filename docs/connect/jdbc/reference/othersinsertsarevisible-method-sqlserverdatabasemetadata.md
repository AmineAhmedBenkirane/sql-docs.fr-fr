---
title: "Méthode othersInsertsAreVisible (SQLServerDatabaseMetaData) | Documents Microsoft"
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
- SQLServerDatabaseMetaData.othersInsertsAreVisible
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: aa32f059-bb59-47f8-bac1-292f314df730
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 68cefb39bfd8ac0f8e79110bf2b74faa952e41db
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="othersinsertsarevisible-method-sqlserverdatabasemetadata"></a>Méthode othersInsertsAreVisible (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère si les insertions effectuées par d’autres sont visibles.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public boolean othersInsertsAreVisible(int type)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *type*  
  
 Un **int** qui indique le jeu de résultats type, qui peut prendre l’une des valeurs suivantes comme défini dans java.sql.ResultSet ou SQLServerResultSet :  
  
## <a name="javasqlresultset-types"></a>Types java.sql.ResultSet  
 TYPE_FORWARD_ONLY  
  
 TYPE_SCROLL_SENSITIVE  
  
 TYPE_SCROLL_INSENSITIVE  
  
## <a name="sqlserverresultset-types"></a>Types SQLServerResultSet  
 TYPE_SS_SCROLL_STATIC  
  
 TYPE_SS_SCROLL_KEYSET  
  
 TYPE_SS_DIRECT_FORWARD_ONLY  
  
 TYPE_SS_SERVER_CURSOR_FORWARD_ONLY  
  
 TYPE_SS_SCROLL_DYNAMIC  
  
## <a name="return-value"></a>Valeur retournée  
 **true** si les insertions sont visibles. Dans le cas contraire, la valeur est **false**.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode othersInsertsAreVisible est spécifiée par la méthode othersInsertsAreVisible dans l’interface java.sql.DatabaseMetaData.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [Membres de SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData, classe](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  

