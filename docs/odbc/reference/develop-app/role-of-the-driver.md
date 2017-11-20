---
title: "Rôle du pilote | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: reference
ms.reviewer: 
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- driver error checking [ODBC]
- diagnostic information [ODBC], driver error checking
ms.assetid: cac64c24-a27d-4884-96c0-ea7988351711
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 2fe0d0545bcc787275bda3ba2154088f23eeda20
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="role-of-the-driver"></a>Rôle du pilote
Le pilote vérifie toutes les erreurs et avertissements ne pas vérifiées par le Gestionnaire de pilotes et les enregistrements d’état qu’elle génère des commandes. (Une application ODBC 2. *x* pilote ne trie pas les enregistrements d’état.) Cela inclut des erreurs et avertissements de troncation de données, conversion de données, la syntaxe et des transitions d’état. Le pilote peut également vérifier les erreurs et avertissements partiellement vérifiées par le Gestionnaire de pilotes. Par exemple, bien que le Gestionnaire de pilotes vérifie si la valeur de *opération* dans **SQLSetPos** est conforme, le pilote doit vérifier si elle est prise en charge.  
  
 Le pilote mappe également *erreurs natives* : autrement dit, les erreurs retournées par la source de données, à SQLSTATE. Par exemple, le pilote peut mapper à un nombre d’erreurs natives différentes pour le syntaxe SQL non conforme à la valeur SQLSTATE 42000 (syntaxe ou violation d’accès). Le pilote retourne le numéro d’erreur natif dans le champ SQL_DIAG_NATIVE de l’enregistrement de l’état. Documentation du pilote doit indiquer comment des erreurs et avertissements sont mappées à partir de la source de données aux arguments dans **SQLGetDiagRec** et **SQLGetDiagField**.

