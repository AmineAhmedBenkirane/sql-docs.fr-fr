---
title: Méthode updateDouble (java.lang.String, double) | Documents Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: jdbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
apiname:
- SQLServerResultSet.updateDouble (java.lang.String, double)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: f70971d5-34cc-4f70-8a91-5d46356b24ae
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d158e1cd1f6727e04472de55c8313f6487ce1739
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="updatedouble-method-javalangstring-double"></a>Méthode updateDouble (java.lang.String, double)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Met à jour la colonne désignée avec une **double** valeur en fonction du nom de colonne.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public void updateDouble(java.lang.String columnName,  
                         double x)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *columnName*  
  
 A **chaîne** qui contient le nom de colonne.  
  
 *x*  
  
 A **double** valeur.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode updateDouble est spécifiée par la méthode updateDouble dans l’interface java.sql.ResultSet.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode updateDouble &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/updatedouble-method-sqlserverresultset.md)   
 [Membres de SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet, classe](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
