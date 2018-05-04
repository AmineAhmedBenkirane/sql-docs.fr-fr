---
title: Tableaux de valeurs de paramètres | Documents Microsoft
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
ms.topic: conceptual
helpviewer_keywords:
- arrays of parameter values [ODBC]
- parameter arrays [ODBC]
ms.assetid: 9b572c5b-1dfe-40af-bebd-051548ab6d90
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 38dc5fb0ed2286b3077e6198bc978808063b5d2f
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="arrays-of-parameter-values"></a>Tableaux de valeurs de paramètre
Il est souvent utile pour les applications passer des tableaux de paramètres. Par exemple, à l’aide de tableaux de paramètres et une commande paramétrable **insérer** instruction, une application peut insérer un nombre de lignes à la fois. Il existe plusieurs avantages à l’utilisation de tableaux. Tout d’abord, le trafic réseau est réduit, car les données de nombreuses instructions sont envoyées dans un seul paquet (si la source de données prend en charge les tableaux de paramètres en mode natif). En second lieu, certaines sources de données peuvent exécuter des instructions SQL à l’aide de tableaux plus rapidement que d’exécuter le même nombre d’instructions SQL distinctes. Enfin, lorsque les données sont stockées dans un tableau, comme c’est souvent le cas pour les données d’écran, l’application peut lier toutes les lignes dans une colonne particulière avec un seul appel à **SQLBindParameter** et les mettre à jour en exécutant une instruction unique.  
  
 Malheureusement, pas de nombreuses sources de données prend en charge les tableaux de paramètres. Toutefois, un pilote peut émuler des tableaux de paramètres en exécutant une instruction SQL une fois pour chaque jeu de valeurs de paramètre. Cela peut entraîner l’augmentation de la vitesse, car le pilote peut préparer ensuite l’instruction qu’il prévoit d’exécuter une fois pour chaque jeu de paramètres. Il peut également entraîner code plus simple de l’application.  
  
 Cette section contient les rubriques suivantes.  
  
-   [Liaison de tableaux de paramètres](../../../odbc/reference/develop-app/binding-arrays-of-parameters.md)  
  
-   [Utilisation de tableaux de paramètres](../../../odbc/reference/develop-app/using-arrays-of-parameters.md)
