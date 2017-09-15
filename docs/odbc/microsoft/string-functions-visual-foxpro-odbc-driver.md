---
title: "(Le pilote ODBC Visual FoxPro) de fonctions de chaîne | Documents Microsoft"
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
- ODBC string functions [ODBC]
- string functions [ODBC]
- Visual FoxPro ODBC driver [ODBC], string functions
- FoxPro ODBC driver [ODBC], string functions
ms.assetid: 1974fd26-ef0d-45d5-860b-298917c8e9c3
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: f3fa7491ea354cc616d6b58de17e6fa82c785a3a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="string-functions-visual-foxpro-odbc-driver"></a>Fonctions de chaîne (pilote ODBC de Visual FoxPro)
Le tableau suivant répertorie les fonctions de manipulation de chaîne ODBC pris en charge par le pilote ODBC Visual FoxPro ; lors de la grammaire Visual FoxPro pour la même fonction diffère de la syntaxe ODBC, le Visual FoxPro équivalent est répertorié.  
  
|Grammaire ODBC|Grammaire de Visual FoxPro|  
|------------------|---------------------------|  
|ASCII *(exp_chaîne)*|ASC *(exp_chaîne)*|  
|CHAR *(code)*|CHR *(exp_chaîne)*|  
|CONCAT *(string_exp1 string_exp2)*|*string_exp1 + string_exp2*|  
|DIFFÉRENCE *(string_exp1 string_exp2)*||  
|Insérer *(string_exp1, début, longueur, string_exp2)*|STUFF *(string_exp1, début, longueur, string_exp2)*|  
|LCASE *(exp_chaîne)*|INFÉRIEUR *(exp_chaîne)*|  
|GAUCHE *(exp_chaîne, décompte)*||  
|LONGUEUR *(exp_chaîne)*|LEN *(exp_chaîne)*|  
|LTRIM *(exp_chaîne)*||  
|RÉPÉTEZ *(exp_chaîne, décompte)*|RÉPLIQUER *(exp_chaîne, décompte)*|  
|Remplacez *(string_exp1, string_exp2, exp_chaîne3)*|STRTRAN *(string_exp1, string_exp2, exp_chaîne3)*|  
|DROIT *(exp_chaîne, décompte)*||  
|La fonction RTRIM *(exp_chaîne)*||  
|SOUNDEX *(exp_chaîne)*||  
|ESPACE *(nombre)*||  
|SOUS-chaîne *(exp_chaîne, début, longueur)*|SUBSTR *(exp_chaîne, début, longueur)*|  
|UCASE *(exp_chaîne)*|SUPÉRIEUR *(exp_chaîne)*|
