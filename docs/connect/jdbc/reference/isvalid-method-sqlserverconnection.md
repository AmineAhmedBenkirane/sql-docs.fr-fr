---
title: Méthode isValid (SQLServerConnection) | Documents Microsoft
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
ms.assetid: 3b0a8bbf-9369-4456-9ab8-1434ccacdd7e
caps.latest.revision: 15
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 169e709fa0993c651487aa5b4e67cfe76de3618e
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="isvalid-method-sqlserverconnection"></a>Méthode isValid (SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Indique si cette [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objet n’a pas été fermé et qu’il est toujours valide.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public boolean isValid(int timeout)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *Délai d’attente*  
  
 Un **int** qui spécifie le nombre de secondes d’attente de validation de la connexion.  
  
## <a name="return-value"></a>Valeur retournée  
 **true** si la connexion est valide ; **false** si la connexion n’est pas valide ou la validité de la connexion ne peut pas être déterminée avant l’expiration du délai.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode isValid est spécifiée par la méthode isValid dans l’interface java.sql.Connection.  
  
## <a name="see-also"></a>Voir aussi  
 [Membres de SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection, classe](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
