---
title: "Méthode getString (java.lang.String) | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SQLServerCallableStatement.getString (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: f67371e0-e879-4188-85fc-ecb85f0be2a9
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 1fa6d4e91089d7c25a6307756f18d6fade57cad4
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="getstring-method-javalangstring"></a>Méthode getString (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère la valeur du paramètre désigné en tant qu’un **chaîne** en fonction du nom du paramètre de langage de programmation Java.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public java.lang.String getString(java.lang.String sCol)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *sCol*  
  
 A **chaîne** qui contient le nom du paramètre.  
  
## <a name="return-value"></a>Valeur retournée  
 A **chaîne** valeur.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode getString est spécifiée par la méthode getString dans l’interface java.sql.CallableStatement.  
  
 Toutes les colonnes de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] peuvent être retournées en tant que chaîne. Cela signifie qu'une représentation de chaîne de tous les types à base de nombres et de caractères, et une représentation de chaîne hexadécimale des colonnes binaires telles que binary, varbinary, varbinary(max), image, timestamp et uniqueidentifier, peuvent être retournées.  
  
 Les types sensibles à l'emplacement tels que money, smallmoney, datetime, smalldatetime, float, real, decimal et numeric retourneront le format toString() canonique pour la valeur sous-jacente du type.  
  
 Les types définis par l'utilisateur sont retournés en tant que valeurs de chaînes hexadécimales.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode getString &#40; SQLServerCallableStatement &#41;](../../../connect/jdbc/reference/getstring-method-sqlservercallablestatement.md)   
 [Membres de SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [SQLServerCallableStatement, classe](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  

