---
title: "Méthode getObject (int) | Documents Microsoft"
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
- SQLServerCallableStatement.getObject (jnt)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: c4b8366b-c065-48e1-b712-19e2d9834228
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 4e43c9e04aefe5b0c658ab41112cfdf764454291
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="getobject-method-int"></a>Méthode getObject (int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère la valeur du paramètre désigné en tant qu'objet dans le langage de programmation Java en fonction de l'index de paramètre.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public java.lang.Object getObject(int index)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *index*  
  
 Un **int** qui indique l’index de paramètre.  
  
## <a name="return-value"></a>Valeur retournée  
 Un **objet** valeur.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode getObject est spécifiée par la méthode getObject dans l’interface java.sql.CallableStatement.  
  
 Cette méthode retourne la valeur de la colonne fournie en tant qu'objet Java. Le type de l'objet Java sera le type d'objet Java par défaut correspondant au type SQL de la colonne, en suivant le mappage pour les types intégrés indiqué dans la spécification JDBC. Si la valeur est SQL NULL, le pilote retourne une valeur Java NULL.  
  
 Cette méthode peut aussi servir à lire des types de données abstraits spécifiques à une base de données. Dans JDBC 2.0, le comportement de la méthode getObject a été étendu afin de matérialiser les données de types SQL définis par l’utilisateur. Lorsqu’une colonne contient une valeur structurée ou distincte, le comportement de cette méthode est comme s’il s’agissait d’un appel à `getObject(columnIndex, this.getStatement().getConnection().getTypeMap())`.  
  
 À compter de la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] le pilote JDBC version 3.0 :  
  
-   Une valeur de type **date** s’affichera en tant qu’objet java.sql.Date.  
  
-   Une valeur de type **temps** s’affichera en tant qu’objet java.sql.Time.  
  
-   Une valeur de type **datetime2** s’affichera en tant qu’objet java.sql.Timestamp.  
  
-   Une valeur de type **datetimeoffset** est retournée en tant qu’objet microsoft.sql.DateTimeOffset.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode getObject &#40; SQLServerCallableStatement &#41;](../../../connect/jdbc/reference/getobject-method-sqlservercallablestatement.md)   
 [Membres de SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [SQLServerCallableStatement, classe](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  

