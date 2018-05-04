---
title: Gestion d’instructions complexes | Documents Microsoft
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
ms.assetid: 6b807a45-a8b5-4b1c-8b7b-d8175c710ce0
caps.latest.revision: 18
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8dc009ed538571d5b66a1240adc8b4c41cbab0a6
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="handling-complex-statements"></a>Gestion d'instructions complexes
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  Lorsque vous utilisez la [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)], vous devrez peut-être gérer des instructions complexes, notamment celles générées de façon dynamique lors de l’exécution. Les instructions complexes effectuent souvent une série de tâches, telles que des mises à jour, des insertions et des suppressions. Ces types d'instructions peuvent également retourner plusieurs jeux de résultats et paramètres de sortie. Dans ce cas, le code Java exécutant les instructions pourrait ne pas connaître à l'avance les types et le nombre d'objets, ainsi que les données retournées.  
  
 Pour traiter efficacement des instructions complexes, le pilote JDBC offre plusieurs méthodes permettant d'interroger les objets et les données retournées, de façon à ce que votre application puisse les traiter correctement. La clé pour le traitement d’instructions complexes est la [exécuter](../../connect/jdbc/reference/execute-method-sqlserverstatement.md) méthode de la [SQLServerStatement](../../connect/jdbc/reference/sqlserverstatement-class.md) classe. Cette méthode retourne un **booléenne** valeur. Si la valeur est « true », le premier résultat retourné par les instructions est un jeu de résultats. Si la valeur est « false », le premier résultat retourné est un nombre de mises à jour.  
  
 Lorsque vous connaissez le type d’objet ou de données qui a été retournées, vous pouvez utiliser la [getResultSet](../../connect/jdbc/reference/getresultset-method-sqlserverstatement.md) ou [getUpdateCount](../../connect/jdbc/reference/getupdatecount-method-sqlserverstatement.md) méthode pour traiter ces données. Pour passer à l’objet ou les données retournées par l’instructions complexe, vous pouvez appeler la [getMoreResults](../../connect/jdbc/reference/getmoreresults-method.md) (méthode).  
  
 Dans l’exemple suivant, une connexion ouverte à la [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)] base de données est transmise à la fonction, une instruction complexe est générée, qui combine un appel de procédure stockée avec une instruction SQL, les instructions sont exécutées, puis un `do` boucle est utilisé pour traiter tous les jeux de résultats et mis à jour qui est retournées.  
  
 [!code[JDBC#HandlingComplexStatements1](../../connect/jdbc/codesnippet/Java/handling-complex-statements_1.java)]  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation d’instructions avec le pilote JDBC](../../connect/jdbc/using-statements-with-the-jdbc-driver.md)  
  
  
