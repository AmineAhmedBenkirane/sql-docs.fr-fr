---
title: "Littéral préfixes et Suffixes | Documents Microsoft"
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
- interoperability of SQL statements [ODBC], literal prefixes and suffixes
- literals [ODBC], prefixes and suffixes
ms.assetid: 29f468f2-f557-4a92-b31d-569c63cc6272
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: ff05f946dee8f6034d04c5d719ada475255ba643
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="literal-prefixes-and-suffixes"></a>Suffixes et les préfixes de littéral
Dans une instruction SQL, un *littéral* est une représentation de caractère de la valeur réelle des données. Par exemple, dans l’instruction suivante, ABC, FFFF et 10 sont des littéraux :  
  
```  
SELECT CharCol, BinaryCol, IntegerCol FROM MyTable  
   WHERE CharCol = 'ABC' AND BinaryCol = 0xFFFF AND IntegerCol = 10  
```  
  
 Littéraux pour certains types de données requièrent des suffixes et préfixes spéciaux. Dans l’exemple précédent, le littéral de caractère (ABC) nécessite un guillemet simple (') comme préfixe et un suffixe, le littéral binaire (FFFF) requiert les caractères 0 x comme préfixe et le littéral d’entier (10) ne pas exiger un préfixe ou suffixe.  
  
 Pour tous les types de données à l’exception de date et d’heure horodateurs, applications interopérables doivent utiliser les valeurs retournées dans les colonnes LITERAL_PREFIX et LITERAL_SUFFIX dans le jeu de résultats créé par **SQLGetTypeInfo**. Pour la date, time, timestamp et littéraux de l’intervalle datetime, applications interopérables doivent utiliser les séquences d’échappement présentés dans la section précédente.
