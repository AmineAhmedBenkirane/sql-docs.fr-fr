---
title: "ENTRE le prédicat | Documents Microsoft"
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
- BETWEEN predicate [ODBC]
- SQL grammar [ODBC], between predicate
ms.assetid: 0cc7464b-d788-4720-98d8-411e1169185f
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 1738aa33f371a2e64ea0362cefcf59a759fdfee7
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="between-predicate"></a>ENTRE le prédicat
La syntaxe suivante :  
  
```  
expression1 BETWEEN expression2 AND expression3  
```  
  
 Retourne true uniquement si *expression1* est supérieur ou égal à *expression2* et *expression1* est inférieur ou égal à *expression3*.  
  
 La sémantique de cette syntaxe est différente pour les pilotes de base de données de bureau et le moteur Microsoft Jet. Dans Microsoft Jet SQL, *expression2* peut être supérieur à *expression3* afin que l’instruction renvoie la valeur TRUE uniquement si *expression1* est supérieur ou égal à *expression3*, et *expression1* est inférieur ou égal à *expression2*.
