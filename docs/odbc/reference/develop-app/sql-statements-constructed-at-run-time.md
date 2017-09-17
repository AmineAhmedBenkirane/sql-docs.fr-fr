---
title: "Instructions SQL construites au moment de l’exécution | Documents Microsoft"
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
- run time constructed SQL statements [ODBC]
- SQL statements [ODBC], constructing
- SQL statements [ODBC], building at run time
ms.assetid: f6554486-d49c-436a-82e3-4c158d26acd8
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 8ccd79048c250c73867752ebaf0b2b7060a6c19b
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="sql-statements-constructed-at-run-time"></a>Instructions SQL construites au moment de l’exécution
Les applications qui effectuent une analyse ad hoc couramment construisent des instructions SQL en cours d’exécution. Par exemple, une feuille de calcul peut autoriser un utilisateur de sélectionner les colonnes à partir de laquelle récupérer les données :  
  
```  
// SQL_Statements_Constructed_at_Run_Time.cpp  
#include <windows.h>  
#include <stdio.h>  
#include <sqltypes.h>  
  
int main() {  
   SQLCHAR *Statement = 0, *TableName = 0;  
   SQLCHAR **TableNamesArray, **ColumnNamesArray = 0;  
   BOOL *ColumnSelectedArray = 0;  
   BOOL  CommaNeeded;  
   SQLSMALLINT i = 0, NumColumns = 0;  
  
   // Use SQLTables to build a list of tables (TableNamesArray[]). Let the  
   // user select a table and store the selected table in TableName.  
  
   // Use SQLColumns to build a list of the columns in the selected table  
   // (ColumnNamesArray). Set NumColumns to the number of columns in the  
   // table. Let the user select one or more columns and flag these columns  
   // in ColumnSelectedArray[].  
  
   // Build a SELECT statement from the selected columns.  
   CommaNeeded = FALSE;  
   Statement = (SQLCHAR*)malloc(8);  
   strcpy_s((char*)Statement, 8, "SELECT ");  
  
   for (i = 0 ; i = NumColumns ; i++) {  
      if (ColumnSelectedArray[i]) {  
         if (CommaNeeded)  
            strcat_s((char*)Statement, sizeof(Statement), ",");  
         else  
            CommaNeeded = TRUE;  
         strcat_s((char*)Statement, sizeof(Statement), (char*)ColumnNamesArray[i]);  
      }  
   }  
  
   strcat_s((char*)Statement, 15, " FROM ");  
   // strcat_s((char*)Statement, 100, (char*)TableName);  
  
   // Execute the statement . It will be executed once, do not prepare it.  
   // SQLExecDirect(hstmt, Statement, SQL_NTS);  
}  
```  
  
 Une autre classe couramment construit des instructions SQL au moment de l’exécution d’applications sont des environnements de développement. Toutefois, les instructions qu’ils construire sont codés en dur dans l’application qu’ils développent, où ils peuvent généralement être optimisés et testés.  
  
 Les applications qui génèrent des instructions SQL en cours d’exécution peuvent fournir une grande flexibilité pour l’utilisateur. Comme le montre l’exemple précédent, qui ne prend pas encore en charge des opérations courantes telles que **où** clauses, **ORDER BY** clauses ou des jointures, construction d’instructions SQL en cours d’exécution est considérablement plus complexe que les instructions de codage en dur. En outre, ces applications de test est problématique, car ils peuvent construire un nombre arbitraire d’instructions SQL.  
  
 Un inconvénient potentiel de construction d’instructions SQL en cours d’exécution est qu’il prend beaucoup plus de temps pour construire une instruction d’utiliser une instruction codé en dur. Heureusement, il est rarement un problème. Ces applications sont susceptibles d’être beaucoup d’interface utilisateur et le temps que l’application consacre à construire des instructions SQL est généralement faible par rapport à l’heure de l’utilisateur est occupé à entrer des critères.
