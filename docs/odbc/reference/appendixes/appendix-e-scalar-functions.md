---
title: "Annexe e : les fonctions scalaires | Documents Microsoft"
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
- SQL-92 functions [ODBC]
- scalar functions [ODBC]
- functions [ODBC], scalar
ms.assetid: 59c7cd5e-32d6-43ab-bac3-7010322d105a
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: aaa110a6a62ca91535e790a267ef714675719bf4
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="appendix-e-scalar-functions"></a>Annexe e : les fonctions scalaires
ODBC spécifie les types suivants de fonctions scalaires, des informations détaillées sur chacun de ces types de fonction fournis dans les sections correspondantes de cette annexe. Les descriptions fonction incluent la syntaxe associée.  
  
 Cette annexe contient les rubriques suivantes.  
  
-   [Fonctions de chaîne](../../../odbc/reference/appendixes/string-functions.md)  
  
-   [Fonctions numériques](../../../odbc/reference/appendixes/numeric-functions.md)  
  
-   [Les fonctions d’intervalle, Date et l’heure](../../../odbc/reference/appendixes/time-date-and-interval-functions.md)  
  
-   [Fonctions système](../../../odbc/reference/appendixes/system-functions.md)  
  
-   [Fonction de Conversion de Type de données explicites](../../../odbc/reference/appendixes/explicit-data-type-conversion-function.md)  
  
-   [SQL-92 CAST (fonction)](../../../odbc/reference/appendixes/sql-92-cast-function.md)  
  
 ODBC n’impose pas un type de données pour les valeurs de retournés à partir de fonctions scalaires, car les fonctions sont souvent spécifique à la source de données. Applications doivent utiliser la fonction scalaire à convertir chaque fois que possible de forcer la conversion de type de données.  
  
## <a name="odbc-and-sql-92-scalar-functions"></a>Fonctions scalaires ODBC et SQL-92.  
 Les tableaux de cette annexe incluent les fonctions qui ont été ajoutées dans ODBC 3.0 pour les aligner avec SQL-92. Ces fonctions ajoutées pour un type particulier d’une fonction scalaire, comme défini dans ODBC, sont indiquées dans chaque section.  
  
 ODBC et SQL-92 classent leurs fonctions scalaires différemment. ODBC classifie les fonctions scalaires par type d’argument ; SQL-92 les classe par valeur de retour. Par exemple, la fonction EXTRACT est classée comme une fonction expose par ODBC, car le champ de l’extraction est un mot clé datetime et l’argument de la source de l’extraction est une expression datetime ou interval. SQL-92, classe quant à eux, extraction comme une fonction scalaire numérique, car la valeur de retour est une valeur numérique.  
  
 Une application peut déterminer les fonctions scalaires, un pilote prend en charge en appelant **SQLGetInfo**. Types d’informations sont incluses pour ODBC et les classifications de SQL-92 de fonctions scalaires. Étant donné que ces classifications sont différentes, la prise en charge pour certaines fonctions scalaires peut-être être indiqué dans les types d’informations qui ne correspondent pas à ODBC et SQL-92. Par exemple, la prise en charge pour l’extraction dans ODBC est indiquée par le type d’informations SQL_TIMEDATE_FUNCTIONS ; prise en charge pour l’extraction dans SQL-92, quant à lui, est indiqué par le type d’informations SQL_SQL92_NUMERIC_VALUE_FUNCTIONS.
