---
title: setEnablePrepareOnFirstPreparedStatementCall (méthode) (SQLServerDataSource) | Documents Microsoft
ms.custom: ''
ms.date: 01/19/2018
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
ms.assetid: ''
caps.latest.revision: 1
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 92f7148fa5d79ca7743d33c423a23e5ab6367958
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="setenableprepareonfirstpreparedstatementcall-method-sqlserverdatasource"></a>setEnablePrepareOnFirstPreparedStatementCall (méthode) (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Spécifie le comportement d’une instance de connexion spécifique. Si cette configuration est false, la première exécution d’une instruction préparée appelle sp_executesql et n’a pas préparer une instruction, une fois que la deuxième exécution se produit, elle appelle sp_prepexec et réellement le programme d’installation un descripteur d’instruction préparée. Suivant les exécutions appelle sp_execute. Cela évite la nécessité de sp_unprepare sur instruction préparée fermer si l’instruction est exécutée uniquement si une seule fois.  
## <a name="syntax"></a>Syntaxe  
  
```
public void setEnablePrepareOnFirstPreparedStatementCall(boolean enablePrepareOnFirstPreparedStatementCall);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *enablePrepareOnFirstPreparedStatementCall*  
  
 La nouvelle valeur de la **enablePrepareOnFirstPreparedStatementCall** propriété de connexion.  

## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
 
## <a name="remarks"></a>Notes  
 Cette méthode est disponible à partir de la version du pilote JDBC 6.4 et ultérieur.
 
## <a name="see-also"></a>Voir aussi  
 [SQLServerDataSource, membres](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource, classe](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
