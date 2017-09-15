---
title: "Le remplissage automatique de l’IPD | Documents Microsoft"
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
- automatically populating ipd [ODBC]
- descriptors [ODBC], automatically populating ipd
- descriptors [ODBC], allocating and freeing
- ipd [ODBC]
- allocating and freeing descriptors [ODBC]
ms.assetid: 1184a7d8-d557-4140-843b-6633ae6deacc
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: d637ddfebc0563ed2591740498d519f91e34321e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="automatic-population-of-the-ipd"></a>Remplissage automatique de l’IPD
Certains pilotes sont capables de définir les champs de l’IPD après qu’une requête paramétrable a été préparée. Les champs de descripteur sont automatiquement remplis avec des informations sur le paramètre, y compris le type de données, précision, échelle et d’autres caractéristiques. Cela est équivalent à la prise en charge **SQLDescribeParam**. Ces informations peuvent être particulièrement utiles pour une application lorsqu’il n’a pas d’autre moyen pour la détection, par exemple lorsqu’une requête ad hoc est exécutée avec les paramètres de l’application ne connaît pas.  
  
 Une application détermine si le pilote prend en charge le remplissage automatique en appelant **SQLGetConnectAttr** avec un *attribut* de SQL_ATTR_AUTO_IPD. Si SQL_TRUE est retourné, le pilote prend en charge et l’application peut l’activer en affectant à l’attribut d’instruction SQL_ATTR_ENABLE_AUTO_IPD SQL_TRUE.  
  
 Lorsque le remplissage automatique est pris en charge et activé, le pilote renseigne les champs de l’IPD après une instruction SQL contenant des marqueurs de paramètres a été préparée par un appel à **SQLPrepare**. Une application peut récupérer ces informations en appelant **SQLGetDescField** ou **SQLGetDescRec**, ou **SQLDescribeParam**. L’application peut utiliser les informations pour lier la mémoire tampon d’application plus approprié pour un paramètre ou pour spécifier une conversion de données pour celui-ci.  
  
 Le remplissage automatique de l’IPD risque de produire une altération des performances. Une application peut désactiver en rétablissant l’attribut d’instruction SQL_ATTR_ENABLE_AUTO_IPD SQL_FALSE (la valeur par défaut).
