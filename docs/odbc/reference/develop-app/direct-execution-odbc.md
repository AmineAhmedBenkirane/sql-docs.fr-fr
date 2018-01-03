---
title: "Dirigent l’exécution ODBC | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: odbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL statements [ODBC], direct execution
- direct execution [ODBC]
- SQL statements [ODBC], executing
ms.assetid: dd00a535-b136-494f-913b-410838e3de7e
caps.latest.revision: "6"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 058dada1c14b901b32f721bc2d42f3cc24434f07
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="direct-execution-odbc"></a>Exécution directe ODBC
L’exécution directe est la façon la plus simple d’exécuter une instruction. Lorsque l’instruction est envoyée pour exécution, la source de données compile dans un plan d’accès, puis exécute ce plan d’accès.  
  
 L’exécution directe est couramment utilisée par les applications génériques qui génèrent et exécutent des instructions en cours d’exécution. Par exemple, le code suivant génère une instruction SQL et exécute une seule fois :  
  
```  
SQLCHAR *SQLStatement;  
  
// Build an SQL statement.  
BuildStatement(SQLStatement);  
  
// Execute the statement.  
SQLExecDirect(hstmt, SQLStatement, SQL_NTS);  
```  
  
 L’exécution directe convient le mieux pour les instructions qui seront exécutées une seule fois. Son inconvénient majeur est que l’instruction SQL est analysée chaque fois qu’elle est exécutée. En outre, l’application ne peut pas récupérer les informations sur le jeu de résultats créé par l’instruction (le cas échéant) jusqu'à ce qu’après l’exécution de l’instruction ; Cela est possible si l’instruction est préparée et exécutée en deux étapes distinctes.  
  
 Pour exécuter une instruction directement, l’application effectue les actions suivantes :  
  
1.  Définit les valeurs des paramètres. Pour plus d’informations, consultez [paramètres de l’instruction](../../../odbc/reference/develop-app/statement-parameters.md), plus loin dans cette section.  
  
2.  Appels **SQLExecDirect** et lui passe une chaîne contenant l’instruction SQL.  
  
3.  Lorsque **SQLExecDirect** est appelée, le pilote :  
  
    -   Modifie l’instruction SQL pour utiliser la grammaire SQL de la source de données sans analyse de l’instruction ; Cela inclut en remplaçant les séquences d’échappement présentés dans [les séquences d’échappement dans ODBC](../../../odbc/reference/develop-app/escape-sequences-in-odbc.md). L’application peut récupérer le formulaire de modification d’une instruction SQL en appelant **SQLNativeSql**. Les séquences d’échappement ne sont pas remplacés si la valeur de l’attribut d’instruction SQL_ATTR_NOSCAN.  
  
    -   Récupère les valeurs de paramètre en cours et les convertit si nécessaire. Pour plus d’informations, consultez [paramètres de l’instruction](../../../odbc/reference/develop-app/statement-parameters.md), plus loin dans cette section.  
  
    -   Envoie l’instruction et les valeurs de paramètre converti à la source de données pour l’exécution.  
  
    -   Retourne toutes les erreurs. Citons notamment séquencement ou état diagnostics comme SQLSTATE 24000 (état de curseur non valide), des erreurs syntaxiques comme SQLSTATE 42000 (syntaxe ou violation d’accès) et les erreurs sémantiques telles que 42 s 02 SQLSTATE (Base de table ou vue introuvable).
