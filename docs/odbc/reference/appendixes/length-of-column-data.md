---
title: "Longueur des données de la colonne | Documents Microsoft"
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
- column data [ODBC]
- length of column data [ODBC]
- ODBC cursor library [ODBC], cache
- cursor library [ODBC], cache
- cache [ODBC]
ms.assetid: c762c881-ebe0-4eac-84d5-f30281fc3eca
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 3ee36dbd04cd60d8b5906abc0248d07f28ff5677
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="length-of-column-data"></a>Longueur des données de colonne
> [!IMPORTANT]  
>  Cette fonctionnalité sera supprimée dans une future version de Windows. Évitez d’utiliser cette fonctionnalité dans tout nouveau développement et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité. Microsoft recommande d’utiliser les fonctionnalités de curseur du pilote.  
  
 La bibliothèque de curseurs crée une mémoire tampon dans le cache pour chaque mémoire tampon de longueur / d’indicateur lié à un jeu de résultats avec **SQLBindCol**. Il utilise les valeurs dans ces mémoires tampons pour construire un **où** clause lorsqu’il émule la mise à jour positionnée ou supprimer des instructions. Il met à jour ces mémoires tampons des tampons de lignes lorsqu’il extrait les données à partir de la source de données et quand il exécute les instructions de mise à jour positionnée.  
  
 Si le type C d’une mémoire tampon de données est SQL_C_CHAR ou SQL_C_BINARY et que la valeur de l’indicateur/longueur est SQL_NTS, la longueur de chaîne des données est placée dans la mémoire tampon de longueur / d’indicateur.  
  
> [!NOTE]  
>  La bibliothèque de curseurs ne met pas à jour son cache pour une colonne si **StrLen_or_IndPtr* dans l’ensemble de lignes correspondante mémoire tampon est SQL_DATA_AT_EXEC ou le résultat de la macro SQL_LEN_DATA_AT_EXEC.
