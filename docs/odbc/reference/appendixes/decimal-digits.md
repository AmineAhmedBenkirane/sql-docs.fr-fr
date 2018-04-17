---
title: Chiffres décimaux | Documents Microsoft
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
- size of data types [ODBC]
- decimal digits of data types [ODBC]
- data types [ODBC], decimal digits
- SQL data types [ODBC], column characteristics
ms.assetid: 07f3d1fc-b4ee-4693-b342-330b2231b6d0
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: ded2bda56c0fee5012e451dbee55a89cfa32e16a
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="decimal-digits"></a>Chiffres décimaux
Le *chiffres décimaux* de données decimal et numeric types est défini comme le nombre maximal de chiffres à droite de la virgule décimale, ou à l’échelle des données. Pour les colonnes de nombres à virgule flottante approximatifs ou les paramètres, l’échelle n’est pas définie, car le nombre de chiffres à droite de la virgule décimale n’est pas fixe. Pour les données datetime ou interval qui contient un composant « secondes », les chiffres décimaux est défini comme le nombre de chiffres à droite de la virgule décimale dans le composant « secondes » de données.  
  
 Pour les types de données SQL_DECIMAL et SQL_NUMERIC, l’échelle maximale est généralement identique à la précision maximale. Toutefois, certaines sources de données imposent une limite distincte sur l’échelle maximale. Pour déterminer les échelles minimales et maximales autorisées pour un type de données, une application appelle **SQLGetTypeInfo**.  
  
 Les chiffres décimaux définis pour chaque type de données SQL concis est indiqué dans le tableau suivant.  
  
|Type SQL|chiffres décimaux|  
|--------------|--------------------|  
|Tous les caractères et les types de données binaires [a]|n/a|  
|SQL_DECIMAL<br />SQL_NUMERIC|Le nombre défini de chiffres à droite de la virgule décimale. Par exemple, l’échelle d’une colonne définie en tant que NUMERIC(10,3) est 3. Cela peut être un nombre négatif pour prendre en charge le stockage de très grands nombres sans utiliser de notation exponentielle ; par exemple, « 12000 » peut être stockée en tant que « 12 » avec une échelle de -3.|  
|Tous les types numériques exacts que SQL_DECIMAL et SQL_NUMERIC [a]|0|  
|Tous les types de données approximatifs [a]|n/a|  
|SQL_TYPE_DATE et tous les types d’intervalle avec aucun composant « secondes » [a]|n/a|  
|Tous les types de date/heure sauf SQL_TYPE_DATE et tous les types d’intervalle avec un composant « secondes »|Le nombre de chiffres à droite du séparateur décimal dans la partie secondes de la valeur (en fractions de seconde). Ce nombre ne peut pas être négatif.|  
|SQL_GUID|n/a|  
  
 [a] la *DecimalDigits* argument de **SQLBindParameter** est ignorée pour ce type de données.  
  
 Les valeurs retournées pour les chiffres décimaux ne correspondent pas aux valeurs dans n’importe quel un champ de descripteur. Les valeurs peuvent provenir à partir de la SQL_DESC_SCALE ou le champ SQL_DESC_PRECISION, selon le type de données, comme indiqué dans le tableau suivant.  
  
|Type SQL|Champ de descripteur correspondant à<br /><br /> chiffres décimaux|  
|--------------|----------------------------------------------------------|  
|Tous les types binaires et caractères|n/a|  
|Tous les types numériques exacts|SCALE|  
|SQL_BIT|n/a|  
|Tous les types numériques approximatifs|n/a|  
|Tous les types date/heure|PRECISION|  
|Tous les types d’intervalle avec un composant « secondes »|PRECISION|  
|Tous les types d’intervalle avec aucun composant « secondes »|n/a|
