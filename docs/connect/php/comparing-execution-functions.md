---
title: Comparaison des fonctions d’exécution | Documents Microsoft
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: php
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- executing queries
ms.assetid: 130fc0fd-87dd-46b2-918f-de9dc572c769
caps.latest.revision: 18
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 921f96668cab29ad6fa2e8b43b8c3908f83e01ab
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MTE
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="comparing-execution-functions"></a>Comparaison des fonctions d’exécution
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

[!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] fournit plusieurs options pour les fonctions d’exécution.  

## <a name="sqlsrv-execution-functions"></a>Exécution des fonctions SQLSRV  
Si vous utilisez le pilote SQLSRV, utilisez [sqlsrv_query](../../connect/php/sqlsrv-query.md) pour exécuter une requête unique et [sqlsrv_prepare](../../connect/php/sqlsrv-prepare.md) avec [sqlsrv_execute](../../connect/php/sqlsrv-execute.md) pour exécuter une instruction préparée plusieurs fois avec différentes valeurs de paramètre pour chaque exécution.  

## <a name="pdosqlsrv-execution-functions"></a>Exécution des fonctions PDO_SQLSRV 
Si vous utilisez le pilote PDO_SQLSRV, vous pouvez exécuter une requête avec l’une des fonctions suivantes :  
  
-   [PDO::exec](../../connect/php/pdo-exec.md)  
  
-   [PDO::Query](../../connect/php/pdo-query.md)  
  
-   [PDO::prepare](../../connect/php/pdo-prepare.md) et [PDOStatement::execute](../../connect/php/pdostatement-execute.md).  
  
## <a name="see-also"></a> Voir aussi  
[Informations de référence sur l’API du pilote SQLSRV](../../connect/php/sqlsrv-driver-api-reference.md)

[Informations de référence sur le pilote PDO_SQLSRV](../../connect/php/pdo-sqlsrv-driver-reference.md)

[Guide de programmation pour les pilotes Microsoft pour PHP pour SQL Server](../../connect/php/programming-guide-for-php-sql-driver.md)
  
