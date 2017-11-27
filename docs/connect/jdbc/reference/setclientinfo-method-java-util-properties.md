---
title: "Méthode setClientInfo (java.util.Properties) | Documents Microsoft"
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
ms.assetid: b2a8ec0b-40a2-44d1-90d9-a810d4132e56
caps.latest.revision: "19"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 1628c14e94290e4f6528a09994075b5405b0e2a3
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2017
---
# <a name="setclientinfo-method-javautilproperties"></a>Méthode setClientInfo (java.util.Properties)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Définit la valeur des propriétés d'informations client de la connexion.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public void setClientInfo (java.util.Properties properties)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *propriétés*  
  
 Un objet de propriétés qui contient la liste des propriétés d’informations client à définir.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode setClientInfo est spécifiée par la méthode setClientInfo dans l’interface java.sql.Connection.  
  
 Le [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] ne prend pas en charge toutes les propriétés d’informations client. Cette méthode génère des avertissements si les *propriétés* paramètre d’entrée ne fait pas référence à un jeu de propriétés vide. En d'autres termes, cette méthode génère des avertissements pour les propriétés que l'application souhaite définir. Les applications doivent utiliser [getWarnings](../../../connect/jdbc/reference/getwarnings-method-sqlserverconnection.md) méthode de la [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) classe pour récupérer chaque avertissement.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode setClientInfo &#40; SQLServerConnection &#41;](../../../connect/jdbc/reference/setclientinfo-method-sqlserverconnection.md)   
 [Membres de SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection, classe](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
