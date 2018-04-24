---
title: Agrégats petits-enfants | Documents Microsoft
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: ado
ms.technology:
- drivers
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- grandchild aggregates [ADO]
- data shaping [ADO], grandchild aggregates
ms.assetid: 4162d35f-2ce1-4218-80a5-b6933348837e
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 589bece101c52a38d11f10a5d5f8f162aa3af8ad
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="grandchild-aggregates"></a>Agrégats petits-enfants
La colonne de chapitre créée dans une clause d’une commande de la forme peut être attribuée à un *nom d’alias-chapitre* (généralement avec le mot clé AS). Vous pouvez identifier toute colonne de n’importe quel chapitre de la forme **Recordset** avec un nom qualifié complet qui identifie l’enfant contenant la colonne. Par exemple, si le chapitre parent, chap1, contient un chapitre enfant, chap2, qui possède une colonne de montant, amt, puis le nom qualifié serait Chap1.Chap2.mnt. Le nom qualifié peut ensuite être utilisé en tant qu’argument à une des fonctions d’agrégation (SUM, AVG, MAX, MIN, COUNT, STDEV ou un).  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple de mise en forme des données](../../../ado/guide/data/data-shaping-example.md)
