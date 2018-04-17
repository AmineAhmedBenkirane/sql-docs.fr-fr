---
title: Unicode | Documents Microsoft
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
- Unicode [ODBC]
- Unicode [ODBC], about Unicode
ms.assetid: 113e1c9a-8333-4805-86f2-e4b57ab816a5
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 566587b228d5f60fb7953b2cc078df0c399aad28
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="unicode"></a>Unicode
La norme Unicode définit le codage des caractères dans de nombreuses langues.  
  
 Pour plus d’informations sur la norme Unicode, consultez [du Unicode Consortium](http://www.unicode.org).  
  
 La norme Unicode définit un jeu de caractères universels. Une page de codes Windows ANSI définit un jeu de caractères, généralement contenant des caractères pour une langue. Il peut être plus difficile à écrire une application qui est requis pour utiliser les pages de codes différentes.  
  
 Unicode ne nécessite pas une page de codes. Chaque point de code est mappé à un seul caractère dans un langage quelconque.  
  
 Actuellement, la seule Unicode que ODBC prend en charge l’encodage est UCS-2, qui utilise un entier 16 bits (longueur fixe) pour représenter un caractère. Unicode permet aux applications de travailler dans différentes langues.  
  
 Le Gestionnaire de pilotes ODBC 3.5 (ou version ultérieure) prend en charge Unicode. Cela affecte les deux zones principales : appels de fonction et les types de données string. Arguments de chaîne du Gestionnaire de pilotes maps (fonction) les données de type chaîne comme requis par l’application et le pilote, qui peuvent être soit compatibles Unicode ou compatible ANSI. Ces deux zones sont décrites en détail dans les sections, [Arguments de la fonction Unicode](../../../odbc/reference/develop-app/unicode-function-arguments.md) et [les données Unicode](../../../odbc/reference/develop-app/unicode-data.md).  
  
 Le Gestionnaire de pilotes ODBC 3.5 (ou version ultérieure) prend en charge l’utilisation d’un pilote Unicode avec une application Unicode et une application ANSI. Il prend également en charge l’utilisation d’un pilote ANSI avec une application ANSI. Le Gestionnaire de pilotes fournit un mappage de Unicode en ANSI limitée pour une application Unicode fonctionne avec un pilote ANSI.  
  
 Cette section contient les rubriques suivantes.  
  
-   [Arguments des fonctions Unicode](../../../odbc/reference/develop-app/unicode-function-arguments.md)  
  
-   [Données Unicode](../../../odbc/reference/develop-app/unicode-data.md)
