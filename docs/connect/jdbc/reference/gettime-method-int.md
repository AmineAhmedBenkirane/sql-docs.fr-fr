---
title: "Méthode getTime (int) | Documents Microsoft"
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
- SQLServerCallableStatement.getTime (int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 6c13dea2-511f-48dc-b3db-2d3b72ccc9de
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 64cfa5a48d3eabe44f37db7e6726c497b1c61483
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="gettime-method-int"></a>Méthode getTime (int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère la valeur du paramètre désigné en tant qu'objet java.sql.Time dans le langage de programmation Java en fonction de l'index de paramètre.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public java.sql.Time getTime(int index)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *index*  
  
 Un **int** qui indique l’index de paramètre.  
  
## <a name="return-value"></a>Valeur retournée  
 Un objet de l’heure.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode getTime est spécifiée par la méthode getTime dans l’interface java.sql.CallableStatement.  
  
 Consultez le graphique intitulé « Conversions de méthode d’accesseur get » dans [présentation des Conversions de Type de données](../../../connect/jdbc/understanding-data-type-conversions.md) pour voir quelle [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] des types de données peuvent être récupérés avec cette méthode.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode getTime &#40; SQLServerCallableStatement &#41;](../../../connect/jdbc/reference/gettime-method-sqlservercallablestatement.md)   
 [Membres de SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [SQLServerCallableStatement, classe](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  

