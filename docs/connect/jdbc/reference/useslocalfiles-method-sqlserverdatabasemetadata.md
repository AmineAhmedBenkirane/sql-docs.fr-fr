---
title: Méthode usesLocalFiles (SQLServerDatabaseMetaData) | Documents Microsoft
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
ms.topic: conceptual
apiname:
- SQLServerDatabaseMetaData.usesLocalFiles
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 69afb3a9-ed56-4191-88b8-bc46c03b817b
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f456aa3c099556115a9dba2000498731527e5e86
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="useslocalfiles-method-sqlserverdatabasemetadata"></a>Méthode usesLocalFiles (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère les informations déterminant si cette base de données stocke les tables dans un fichier local.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public boolean usesLocalFiles()  
```  
  
## <a name="return-value"></a>Valeur retournée  
 **true** si la base de données utilise les fichiers locaux. Dans le cas contraire, la valeur est **false**.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode usesLocalFiles est spécifiée par la méthode usesLocalFiles dans l’interface java.sql.DatabaseMetaData.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [Membres de SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData, classe](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
