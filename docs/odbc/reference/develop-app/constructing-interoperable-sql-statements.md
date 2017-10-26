---
title: "Construction d’instructions SQL interopérable | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL statements [ODBC], interoperability
- interoperability of SQL statements [ODBC], constructing statements
ms.assetid: dee6f7e2-bcc4-4c74-8c7c-12aeda8a90eb
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 070b42e5350471ec86fbc256f2005dd7c0385002
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="constructing-interoperable-sql-statements"></a>Construction d’instructions SQL interopérables
Comme indiqué dans les sections précédentes, les applications interopérables doivent utiliser la grammaire SQL ODBC. Au-delà, grâce à cette grammaire, toutefois, un nombre de problèmes supplémentaires est confronté par les applications interopérables. Par exemple, qu’une application ne s’il souhaite utiliser une fonctionnalité, telles que les jointures externes, qui n’est pas pris en charge par toutes les sources de données ?  
  
 À ce stade, le writer d’application doit rendre certaines décisions concernant les fonctionnalités de langage sont requises et facultatifs. Dans la plupart des cas, si un pilote spécifique ne prend pas en charge une fonctionnalité requise par l’application, l’application est simplement refuse d’exécuter avec ce pilote. Toutefois, si la fonctionnalité est facultative, l’application peut contourner la fonctionnalité. Par exemple, il peut désactiver les parties de l’interface qui autorise l’utilisateur à utiliser la fonctionnalité.  
  
 Pour déterminer quelles fonctionnalités sont prises en charge, les applications démarrent en appelant **SQLGetInfo** avec l’option SQL_SQL_CONFORMANCE. Le niveau de conformité SQL donne une vue générale de ce qui est pris en charge SQL à l’application. Pour affiner cette vue, l’application appelle **SQLGetInfo** avec un certain nombre d’autres options. Pour obtenir une liste complète de ces options, consultez la [SQLGetInfo](../../../odbc/reference/syntax/sqlgetinfo-function.md) description de fonction. Enfin, **SQLGetTypeInfo** retourne des informations sur les types de données pris en charge par la source de données. Les sections suivantes répertorient certains facteurs possible que les applications doivent observer lors de la construction des instructions SQL interopérables.  
  
 Cette section contient les rubriques suivantes.  
  
-   [Catalogue et l’utilisation de schéma](../../../odbc/reference/develop-app/catalog-and-schema-usage.md)  
  
-   [Position du catalogue](../../../odbc/reference/develop-app/catalog-position.md)  
  
-   [Identificateurs entre guillemets](../../../odbc/reference/develop-app/quoted-identifiers.md)  
  
-   [Cas d’identificateur](../../../odbc/reference/develop-app/identifier-case.md)  
  
-   [Séquences d’échappement](../../../odbc/reference/develop-app/escape-sequences.md)  
  
-   [Suffixes et les préfixes de littéral](../../../odbc/reference/develop-app/literal-prefixes-and-suffixes.md)  
  
-   [Marqueurs de paramètre dans les appels de procédure](../../../odbc/reference/develop-app/parameter-markers-in-procedure-calls.md)  
  
-   [Instructions DDL](../../../odbc/reference/develop-app/ddl-statements.md)

