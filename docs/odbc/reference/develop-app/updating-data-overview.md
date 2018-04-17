---
title: Vue d’ensemble des données de mise à jour | Documents Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: odbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- updating data [ODBC], about updating data
- data updates [ODBC]
- updating data [ODBC]
- data updates [ODBC], about data updates
ms.assetid: 062036a4-cda6-4aaa-9765-f1ec3e0b31b1
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: e5accaa3a443f7cc850fd6b4012430043d402203
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="updating-data-overview"></a>Vue d’ensemble des données de mise à jour
Les applications peuvent mettre à jour les données en exécutant des instructions SQL ou en appelant **SQLSetPos** ou **SQLBulkOperations**. **Mise à jour**, **supprimer**, et **insérer** instructions agir directement sur la source de données et sont généralement prises en charge par les pilotes. Recherche des mises à jour et les instructions delete contient une spécification des lignes à modifier. Positionné mise à jour et supprimer des instructions et **SQLSetPos** agissent sur la source de données via un curseur et sont moins couramment pris en charge.  
  
 Si les curseurs peuvent détecter les modifications apportées à un jeu de résultats avec les méthodes décrites dans cette section varie selon le type du curseur et comment il est implémenté. Les curseurs avant uniquement ne pas réexaminer des lignes et par conséquent, ne détectent pas les modifications. Pour savoir si les curseurs de défilement peuvent détecter des modifications, consultez [curseurs permettant le défilement](../../../odbc/reference/develop-app/scrollable-cursors.md).  
  
 Cette section contient les rubriques suivantes.  
  
-   [Instructions UPDATE, DELETE et INSERT](../../../odbc/reference/develop-app/update-delete-and-insert-statements.md)  
  
-   [Instructions de mise à jour et de suppression positionnées](../../../odbc/reference/develop-app/positioned-update-and-delete-statements.md)  
  
-   [Simulation d’instructions de mise à jour et de suppression positionnées](../../../odbc/reference/develop-app/simulating-positioned-update-and-delete-statements.md)  
  
-   [Détermination du nombre de lignes affectées](../../../odbc/reference/develop-app/determining-the-number-of-affected-rows.md)  
  
-   [Mise à jour de données avec SQLSetPos](../../../odbc/reference/develop-app/updating-data-with-sqlsetpos.md)  
  
-   [Mise à jour de données avec SQLBulkOperations](../../../odbc/reference/develop-app/updating-data-with-sqlbulkoperations.md)  
  
-   [Données de type Long, et SQLSetPos et SQLBulkOperations](../../../odbc/reference/develop-app/long-data-and-sqlsetpos-and-sqlbulkoperations.md)
