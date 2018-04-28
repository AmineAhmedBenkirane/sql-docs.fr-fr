---
title: Méthode getSearchStringEscape (SQLServerDatabaseMetaData) | Documents Microsoft
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
- SQLServerDatabaseMetaData.getSearchStringEscape
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: ea0f95d0-0238-4dc8-9f26-7ff9b65f30c3
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 812867e384e4152f0dd15c54cc84c96abb1c83ba
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="getsearchstringescape-method-sqlserverdatabasemetadata"></a>Méthode getSearchStringEscape (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère le **chaîne** qui peut être utilisé pour échapper les caractères génériques.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public java.lang.String getSearchStringEscape()  
```  
  
## <a name="return-value"></a>Valeur retournée  
 A **chaîne** qui contient la chaîne de caractères génériques d’échappement.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode getSearchStringEscape est spécifiée par la méthode getSearchStringEscape dans l’interface java.sql.DatabaseMetaData.  
  
 Cette méthode est utilisée uniquement pour les recherches de modèles de métadonnées. Elle retourne «\\». A **chaîne** modèle de recherche peut échapper des caractères génériques (« % » et « _ ») et les fournir en tant que littéraux en ajoutant une barre oblique inverse. Cela se traduit «\\% » en « [%] » et «\\\_» à « [\_] ».  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [Membres de SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData, classe](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
