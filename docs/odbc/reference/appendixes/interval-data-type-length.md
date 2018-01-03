---
title: "Longueur de Type de données de l’intervalle | Documents Microsoft"
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
- data types [ODBC], interval data types
- length of data types [ODBC]
- interval data type [ODBC], length
ms.assetid: e9eb38d8-f9db-4401-8c62-aa394054cbbf
caps.latest.revision: "6"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 2e588cb2457099cad698d3cc34265f26bc639972
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="interval-data-type-length"></a>Longueur de Type de données intervalle
Les règles suivantes sont utilisées pour déterminer la longueur d’un type de données d’intervalle en caractères. La longueur est exprimée en nombre de caractères. Le nombre d’octets varie selon le jeu de caractères. La longueur inclut les valeurs suivantes, ajoutées :  
  
-   Deux caractères pour chaque champ dans l’intervalle qui n’est pas le champ Début.  
  
-   Dans le champ Début, le nombre de caractères qui correspond à la précision de début expresse ou implicite. Si la précision de début n’est pas spécifiée, la valeur par défaut est 2.  
  
-   Pour le séparateur entre les champs d’un caractère.  
  
-   Un, plus la précision en secondes expresse ou implicite. Si la précision en secondes n’est pas spécifiée, la valeur par défaut est 6.  
  
 Valeurs de longueur de colonne spécifique pour chaque type de données d’intervalle sont contenues dans [taille de la colonne](../../../odbc/reference/appendixes/column-size.md).
