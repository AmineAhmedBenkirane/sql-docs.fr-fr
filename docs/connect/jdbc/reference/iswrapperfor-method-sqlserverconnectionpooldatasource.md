---
title: Méthode isWrapperFor (SQLServerConnectionPoolDataSource) | Documents Microsoft
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
ms.assetid: 09ed10eb-6e46-437b-a7c0-3c55574aad38
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9cb522667a1946bc1d05c563169cda37431e33cd
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="iswrapperfor-method-sqlserverconnectionpooldatasource"></a>Méthode isWrapperFor (SQLServerConnectionPoolDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Indique si cet objet est un wrapper pour l'interface spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public boolean isWrapperFor(Class iface)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *iface*  
  
 A **classe** définissant une interface.  
  
## <a name="return-value"></a>Valeur retournée  
 **true** si cet objet implémente l’interface ou encapsule un objet qui implémente l’interface. Dans le cas contraire, la valeur est **false**.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Le [isWrapperFor](../../../connect/jdbc/reference/iswrapperfor-method-sqlserverxadatasource.md) (méthode) et le [unwrap](../../../connect/jdbc/reference/unwrap-method-sqlserverconnectionpooldatasource.md) méthode sont définis par l’interface java.sql.Wrapper, introduite dans les spécifications de JDBC 4.0.  
  
 Si cette méthode retourne la valeur true, l’appel [unwrap](../../../connect/jdbc/reference/unwrap-method-sqlserverconnectionpooldatasource.md) avec le même argument réussit.  
  
 Pour plus d’informations, consultez [Wrappers et Interfaces](../../../connect/jdbc/wrappers-and-interfaces.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode Unwrap &#40;SQLServerConnectionPoolDataSource&#41;](../../../connect/jdbc/reference/unwrap-method-sqlserverconnectionpooldatasource.md)   
 [Méthodes SQLServerConnectionPoolDataSource](../../../connect/jdbc/reference/sqlserverconnectionpooldatasource-methods.md)   
 [Membres de SQLServerConnectionPoolDataSource](../../../connect/jdbc/reference/sqlserverconnectionpooldatasource-members.md)   
 [SQLServerConnectionPoolDataSource, classe](../../../connect/jdbc/reference/sqlserverconnectionpooldatasource-class.md)  
  
  
