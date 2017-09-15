---
title: Traitement des instructions SQL | Documents Microsoft
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
- ODBC cursor library [ODBC], statement processing
- SQL statements [ODBC], cursor library
- cursor library [ODBC], statement processing
ms.assetid: 54dad6a3-e86c-477b-ba7c-4e95e0385ec1
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 3613775e14453c2ed14e70cf122bd527217b2cd7
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="processing-sql-statements"></a>Traitement des instructions SQL
> [!IMPORTANT]  
>  Cette fonctionnalité sera supprimée dans une future version de Windows. Évitez d’utiliser cette fonctionnalité dans tout nouveau développement et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité. Microsoft recommande d’utiliser les fonctionnalités de curseur du pilote.  
  
 La bibliothèque de curseurs ODBC transmet toutes les instructions SQL directement dans le pilote, sauf les éléments suivants :  
  
-   Positionné mise à jour et supprimer des instructions  
  
-   **Sélectionnez pour la mise à jour** instructions  
  
-   Instructions SQL par lots  
  
 Pour exécuter la mise à jour positionnée et supprimer des instructions et pour positionner le curseur sur une ligne pour appeler **SQLGetData** pour cette ligne, la bibliothèque de curseurs construit une instruction de recherche qui identifie la ligne.  
  
 Cette section contient les rubriques suivantes.  
  
-   [Traitement positionné les instructions Update et Delete](../../../odbc/reference/appendixes/processing-positioned-update-and-delete-statements.md)  
  
-   [Sélectionnez pour les instructions de mise à jour de traitement](../../../odbc/reference/appendixes/processing-select-for-update-statements.md)  
  
-   [Traitement des lots d’instructions SQL](../../../odbc/reference/appendixes/processing-batches-of-sql-statements.md)  
  
-   [Construction de recherche des instructions](../../../odbc/reference/appendixes/constructing-searched-statements.md)
