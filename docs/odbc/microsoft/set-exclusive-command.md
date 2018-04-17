---
title: Commande exclusif SET | Documents Microsoft
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
- SET EXCLUSIVE command [ODBC]
ms.assetid: d4fe12c5-7e8b-4d20-9ea4-2bcaffb271f2
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: cd877a854c1be02365b338829cc28f1db9d44dee
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="set-exclusive-command"></a>Commande exclusif SET
Spécifie si les fichiers de la table sont ouverts pour un usage exclusif ou partagé sur un réseau.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
SET EXCLUSIVE ON | OFF  
```  
  
## <a name="arguments"></a>Arguments  
 ON  
 Limite d’accessibilité d’une table ouverte sur un réseau à l’utilisateur ayant ouvert. La table n’est pas accessible à d’autres utilisateurs sur le réseau. DÉFINIR les ON exclusif empêche également tous les autres utilisateurs ayant un accès en lecture seule.  
  
 OFF  
 (Valeur par défaut pour le pilote ; les valeurs par défaut pour Visual FoxPro sont ON pour la session de données globales et OFF pour une session de données privées). Permet à une table est ouverte sur un réseau partagé et modifiés par un utilisateur sur le réseau.  
  
## <a name="remarks"></a>Notes  
 Modification du paramètre de valeur exclusif ne change pas l’état des tables précédemment ouverts. Par exemple, si une table est ouvert avec la valeur exclusif la valeur ON et définir exclusif est modifié ultérieurement à OFF, la table conserve son état de l’usage exclusif.  
  
## <a name="see-also"></a>Voir aussi  
 [Configuration d’ODBC pour Visual FoxPro, boîte de dialogue](../../odbc/microsoft/odbc-visual-foxpro-setup-dialog-box.md)
