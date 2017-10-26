---
title: "Types de données de dBASE | Documents Microsoft"
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
- Jet-based ODBC drivers [ODBC], DBasedriver
- desktop database drivers [ODBC], DBasedriver
- DBase driver [ODBC], data types
- data types [ODBC], DBase driver
- dbase data types [ODBC]
- ODBC desktop database drivers [ODBC], DBasedriver
ms.assetid: a0e31e6b-d02b-4ee2-9b37-5baf6a11c0a6
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 49fb588f5793eb3ee2fce7417632301794a65a22
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="dbase-data-types"></a>dBASE des Types de données
Le tableau suivant montre comment les types de données dBASE sont mappées aux types de données ODBC SQL. Notez que pas tous les types de données SQL ODBC sont prises en charge.  
  
|type de données dBASE|Type de données ODBC|  
|---------------------|--------------------|  
|CHAR|SQL_VARCHAR|  
|DATE|SQL_DATE|  
|FLOAT [1]|SQL_DOUBLE|  
|LOGIQUE|SQL_BIT|  
|MÉMO|SQL_LONGVARCHAR|  
|NUMÉRIQUE (BCD)|SQL_DOUBLE|  
|CLASSES OLEOBJECT [1]|SQL_LONGBINARY|  
  
 [1] durée de validité seulement dBASE version 5. *x*  
  
 Précision en dBASE III permet de nombres avec des exposants à deux chiffres et des nombres de dBASE IV avec jusqu'à des exposants à trois chiffres. Étant donné que les nombres sont stockés sous forme de texte, ils sont convertis en nombres. Si le nombre à convertir ne tient pas dans un champ, les résultats inexpliqués peuvent se produire.  
  
 DBASE permet une précision et une échelle doit être spécifiée avec un type de données numérique, il n'est pas prise en charge par le pilote dBASE ODBC. Le pilote dBASE ODBC retourne toujours une précision de 15 et une échelle de 0 pour un type de données numérique.  
  
 Une colonne créée avec le type de données numériques à l’aide des mappages de pilote ODBC dBASE au type de données ODBC de SQL_DOUBLE. Par conséquent, les données de cette colonne sont soumis à l’arrondi. Ce comportement n’est pas le même comme que les données numériques de type dans le fichier dBASE (type N), qui est Binary Coded Decimal (BCD).  
  
> [!NOTE]  
>  **SQLGetTypeInfo** retourne des types de données ODBC SQL. Toutes les conversions dans l’annexe D de la *de référence du programmeur ODBC* sont pris en charge pour les types de données ODBC SQL répertoriées plus haut dans cette rubrique.  
  
 Le tableau suivant présente des limitations sur dBASE types de données.  
  
|Type de données| Description|  
|---------------|-----------------|  
|CHAR|Création d’une colonne de type CHAR de zéro ou de longueur non spécifiée retourne en fait une colonne 254 octets.|  
|Données chiffrées|Le pilote dBASE ne prend pas en charge les tables dBASE chiffré.|  
|LOGIQUE|Le pilote dBASE ne peut pas créer un index sur une colonne logique.|  
|MÉMO|La longueur maximale d’une colonne de type MEMO est 65 500 octets.|  
  
 Vous trouverez davantage de contraintes sur les types de données dans [Limitations du Type de données](../../odbc/microsoft/data-type-limitations.md).

