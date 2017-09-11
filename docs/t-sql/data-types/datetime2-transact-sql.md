---
title: datetime2 (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 07/23/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- datetime2
- datetime2_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- time [SQL Server], data types
- dates [SQL Server], data types
- date and time [SQL Server], datetime2
- data types [SQL Server], date and time
- datetime2 data type [SQL Server]
ms.assetid: 868017f3-214f-43ef-8536-cc1632a2288f
caps.latest.revision: 58
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 13766b3d0cb86780c2eca55c7f36e8fd16e973c5
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="datetime2-transact-sql"></a>datetime2 (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

Définit une date qui est associée à une heure de la journée au format 24 heures. **datetime2** peut être considéré comme une extension existants **datetime** type qui a une plus grande plage de dates, une plus grande précision fractionnaire par défaut et facultatif précision spécifiée par l’utilisateur.
  
## <a name="datetime2-description"></a>description de datetime2
  
|Propriété|Valeur|  
|--------------|-----------|  
|Syntaxe|**datetime2** [(*précision de fractions de seconde*)]|  
|Utilisation|DÉCLARER @MyDatetime2 **datetime2 (7)**<br /><br /> CRÉER la TABLE Table1 (Column1 **datetime2 (7)** )|  
|Format de littéral de chaîne par défaut<br /><br /> (utilisé pour le client de bas niveau)|AAAA-MM-JJ hh:mm:ss[.fractions de seconde]<br /><br /> Pour plus d’informations, consultez la section « Compatibilité descendante pour les Clients de bas niveau » qui suit.|  
|Plage de dates|0001-01-01 à 9999-12-31<br /><br /> Janvier 1,1 CE et le 31 décembre 9999 CE|  
|Plage temporelle|00:00:00 à 23:59:59.9999999|  
|Plage de décalages de fuseau horaire|Aucune|  
|Plages d'éléments|AAAA est un nombre de quatre chiffres, entre 0001 et 9999, qui représente une année.<br /><br /> MM est un nombre à deux chiffres, entre 01 et 12, qui représente un mois dans l'année spécifiée.<br /><br /> DD est un nombre à deux chiffres, entre 01 et 31 selon le mois, qui représente un jour du mois spécifié.<br /><br /> hh est un nombre à deux chiffres, entre 00 et 23, qui représente l'heure.<br /><br /> mm est un nombre à deux chiffres, entre 00 et 59, qui représente la minute.<br /><br /> ss est un nombre à deux chiffres, entre 00 et 59, qui représente la seconde.<br /><br /> n* est un nombre qui comprend entre zéro et sept chiffres, entre 0 et 9999999, qui représente les fractions de seconde. Dans Informatica, les fractions de seconde sont tronquées quand n > 3.|  
|Longueur de caractère|19 positions au minimum (AAAA-MM-JJ hh:mm:ss) et 27 au maximum (AAAA-MM-JJ hh:mm:ss.0000000)|  
|Précision, échelle|De 0 à 7 chiffres, avec une précision de 100 ns. La précision par défaut est de 7 chiffres.|  
|Taille de stockage|6 octets pour des précisions inférieures à 3 chiffres ; 7 octets pour des précisions égales à 3 et 4 chiffres. Toutes les autres précisions requièrent 8 octets.|  
|Analyse de précision|100 nanosecondes|  
|Valeur par défaut|1900-01-01 00:00:00|  
|Calendrier|Grégorien|  
|Précision à la fraction de seconde définie par l'utilisateur|Oui|  
|Prise en charge et conservation du décalage de fuseau horaire|Non|  
|Prise en charge de l'heure d'été|Non|  
  
Pour les métadonnées de type de données, consultez [sys.systypes &#40; Transact-SQL &#41; ](../../relational-databases/system-compatibility-views/sys-systypes-transact-sql.md) ou [TYPEPROPERTY &#40; Transact-SQL &#41; ](../../t-sql/functions/typeproperty-transact-sql.md). La précision et l'échelle sont variables pour certains types de données de date et d'heure. Pour obtenir la précision et l’échelle d’une colonne, consultez [COLUMNPROPERTY &#40; Transact-SQL &#41; ](../../t-sql/functions/columnproperty-transact-sql.md), [COL_LENGTH &#40; Transact-SQL &#41; ](../../t-sql/functions/col-length-transact-sql.md), ou [sys.columns &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/sys-columns-transact-sql.md).
  
## <a name="supported-string-literal-formats-for-datetime2"></a>Prise en charge des formats de littéraux de chaîne pour datetime2
Les tableaux suivants répertorient les formats pris en charge ISO 8601 et ODBC chaîne littérales pour **datetime2**. Pour plus d’informations sur les formats alphabétique, numériques, non séparées et d’heure pour les parties de date et heure de **datetime2**, consultez [date &#40; Transact-SQL &#41; ](../../t-sql/data-types/date-transact-sql.md) et [temps &#40; Transact-SQL &#41; ](../../t-sql/data-types/time-transact-sql.md).
  
|ISO 8601|Descriptions|  
|---|---|
|AAAA-MM-JJThh:mm:ss[.nnnnnnn]<br /><br /> AAAA-MM-JJThh:mm:ss[.nnnnnnn]|Ce format n'est pas affecté par les paramètres régionaux de session SET LANGUAGE et SET DATEFORMAT. Le **T**, le signe deux-points ( :) et le point (.) sont inclus dans le littéral de chaîne, par exemple « 2007-05-02T19:58:47.1234567 ».|  
  
|ODBC| Description|  
|---|---|
|{ ts 'aaaa-mm-jj hh:mm:ss[.fractions de seconde]' }|Spécifique à l'API ODBC :<br /><br /> Le nombre de chiffres à droite de la virgule décimale, qui représente les fractions de seconde, peut être spécifié de 0 jusqu'à 7 (100 nanosecondes).|  
  
## <a name="ansi-and-iso-8601-compliance"></a>Conformité ANSI et ISO 8601  
La compatibilité ANSI et ISO 8601 de [date](../../t-sql/data-types/date-transact-sql.md) et [temps](../../t-sql/data-types/time-transact-sql.md) s’appliquent aux **datetime2**.
  
##  <a name="backward-compatibility-for-down-level-clients"></a>Compatibilité descendante pour les clients de bas niveau  
Certains clients de bas niveau ne gèrent pas la **temps**, **date**, **datetime2** et **datetimeoffset** des types de données. Le tableau suivant présente le type de mappage entre une instance de haut niveau de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et des clients de bas niveau.
  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de données|Format de littéral de chaîne par défaut passé au client de bas niveau|ODBC de bas niveau|OLEDB de bas niveau|JDBC de bas niveau|SQLCLIENT de bas niveau|  
| --- | --- | --- | --- | --- | --- |
|**time**|hh:mm:ss [.nnnnnnn]|SQL_WVARCHAR ou SQL_VARCHAR|DBTYPE_WSTR ou DBTYPE_STR|Java.sql.String|String ou SqString|  
|**date**|AAAA-MM-JJ|SQL_WVARCHAR ou SQL_VARCHAR|DBTYPE_WSTR ou DBTYPE_STR|Java.sql.String|String ou SqString|  
|**datetime2**|AAAA-MM-JJ hh:mm:ss[.nnnnnnn]|SQL_WVARCHAR ou SQL_VARCHAR|DBTYPE_WSTR ou DBTYPE_STR|Java.sql.String|String ou SqString|  
|**datetimeoffset**|AAAA-MM-JJ HH : mm : [.nnnnnnn] [+ &#124;-] HH : mm|SQL_WVARCHAR ou SQL_VARCHAR|DBTYPE_WSTR ou DBTYPE_STR|Java.sql.String|String ou SqString|  
  
## <a name="converting-date-and-time-data"></a>Conversion des données de date et d’heure
Lorsque vous effectuez une conversion vers des types de données date et heure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rejette toutes les valeurs qu'il ne peut identifier comme dates ou heures. Pour plus d’informations sur l’utilisation des fonctions CAST et CONVERT avec des données de date et d’heure, consultez [CAST et CONVERT &#40; Transact-SQL &#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)
  
### <a name="converting-other-date-and-time-types-to-the-datetime2-data-type"></a>Conversion d’autres types de date et d’heure pour le type de données datetime2
Cette section décrit ce qui se produit lorsque les autres types de données de date et d’heure sont converties à le **datetime2** type de données.  
  
Lorsque la conversion est de **date**, jour, mois et année sont copiés.  Le composant heure est défini à 00:00:00.0000000.  Le code suivant montre les résultats de la conversion d'une valeur `date` en valeur `datetime2`.  
  
```sql
DECLARE @date date = '12-21-16';
DECLARE @datetime2 datetime2 = @date;

SELECT @datetime2 AS '@datetime2', @date AS '@date';
  
--Result  
--@datetime2                  @date
----------------------------- ----------
--2016-12-21 00:00:00.0000000 2016-12-21
```  
  
Lorsque la conversion est de **Time (n)**, le composant heure est copié et le composant date est défini sur ' 1900-01-01 ». L'exemple suivant montre les résultats de la conversion d'une valeur `time(7)` en valeur `datetime2`.  
  
```sql
DECLARE @time time(7) = '12:10:16.1234567';
DECLARE @datetime2 datetime2 = @time;

SELECT @datetime2 AS '@datetime2', @time AS '@time';
  
--Result  
--@datetime2                  @time
----------------------------- ----------------
--1900-01-01 12:10:16.1234567 12:10:16.1234567
```  
  
Lorsque la conversion est de **smalldatetime**, les heures et minutes sont copiées. Les secondes et fractions de seconde sont définies sur 0. Le code suivant montre les résultats de la conversion d'une valeur `smalldatetime` en valeur `datetime2`.  
  
```sql
DECLARE @smalldatetime smalldatetime = '12-01-16 12:32';
DECLARE @datetime2 datetime2 = @smalldatetime;

SELECT @datetime2 AS '@datetime2', @smalldatetime AS '@smalldatetime'; 
  
--Result  
--@datetime2                  @smalldatetime
----------------------------- -----------------------
--2016-12-01 12:32:00.0000000 2016-12-01 12:32:00 
```  
  
Lorsque la conversion est de **DateTimeOffset (n)**, les composants de date et d’heure sont copiées. Le fuseau horaire est tronqué. L'exemple suivant montre les résultats de la conversion d'une valeur `datetimeoffset(7)` en valeur `datetime2`.  
  
```sql
DECLARE @datetimeoffset datetimeoffset(7) = '2016-10-23 12:45:37.1234567 +10:0';
DECLARE @datetime2 datetime2 = @datetimeoffset;

SELECT @datetime2 AS '@datetime2', @datetimeoffset AS '@datetimeoffset'; 
  
--Result  
--@datetime2                  @datetimeoffset
----------------------------- ----------------------------------
--2016-10-23 12:45:37.1234567 2016-10-23 12:45:37.1234567 +10:00
```  

Lorsque la conversion est de **datetime**, la date et l’heure sont copiées.  La précision fractionnaire est étendue à 7 chiffres.  L'exemple suivant montre les résultats de la conversion d'une valeur `datetime` en valeur `datetime2`.

```sql
DECLARE @datetime datetime = '2016-10-23 12:45:37.333';
DECLARE @datetime2 datetime2 = @datetime;

SELECT @datetime2 AS '@datetime2', @datetime AS '@datetime';
   
--Result  
--@datetime2                  @datetime
------------------------- ---------------------------
--2016-10-23 12:45:37.3333333 2016-10-23 12:45:37.333
```  
  
### <a name="converting-string-literals-to-datetime2"></a>Conversion de littéraux de chaîne en datetime2  
Les conversions de littéraux de chaîne en types de date et d'heure sont autorisées si toutes les parties des chaînes sont dans des formats valides. Sinon, une erreur d'exécution est déclenchée. Les conversions implicites ou explicites qui ne spécifient pas de style à partir de types de date et d'heure en littéraux de chaîne seront au format par défaut de la session active. Le tableau suivant présente les règles de conversion d’une chaîne littérale pour le **datetime2** type de données.
  
|Littéral de chaîne d'entrée|**datetime2**|  
|---|---|
|ODBC DATE|Littéraux de chaîne ODBC sont mappées à la **datetime** type de données. Toute opération d’affectation de littéraux ODBC DATETIME en **datetime2** provoquent une conversion implicite entre types **datetime** et ce type, tel que défini par les règles de conversion.|  
|ODBC TIME|Consultez la règle DATE ODBC précédente.|  
|ODBC DATETIME|Consultez la règle DATE ODBC précédente.|  
|DATE uniquement|La partie TIME a pour valeur par défaut 00:00:00.|  
|TIME uniquement|La partie DATE a pour valeur par défaut 1900-1-1.|  
|TIMEZONE uniquement|Les valeurs par défaut sont fournies.|  
|DATE + TIME|Trivial|  
|DATE + TIMEZONE|Non autorisé.|  
|TIME + TIMEZONE|La partie DATE a pour valeur par défaut 1900-1-1. L'entrée TIMEZONE est ignorée.|  
|DATE + TIME + TIMEZONE|Le DATETIME local sera utilisé.|  
  
## <a name="examples"></a>Exemples  
L’exemple suivant compare les résultats de la conversion d’une chaîne en chaque **date** et **temps** type de données.
  
```sql
SELECT   
     CAST('2007-05-08 12:35:29. 1234567 +12:15' AS time(7)) AS 'time'   
    ,CAST('2007-05-08 12:35:29. 1234567 +12:15' AS date) AS 'date'   
    ,CAST('2007-05-08 12:35:29.123' AS smalldatetime) AS   
        'smalldatetime'   
    ,CAST('2007-05-08 12:35:29.123' AS datetime) AS 'datetime'   
    ,CAST('2007-05-08 12:35:29. 1234567 +12:15' AS datetime2(7)) AS   
        'datetime2'  
    ,CAST('2007-05-08 12:35:29.1234567 +12:15' AS datetimeoffset(7)) AS   
        'datetimeoffset';  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
|Type de données|Sortie|  
|---|---|
|**time**|12:35:29. 1234567|  
|**date**|2007-05-08|  
|**smalldatetime**|2007-05-08 12:35:00|  
|**datetime**|2007-05-08 12:35:29.123|  
|**datetime2**|2007-05-08 12:35:29. 1234567|  
|**datetimeoffset**|2007-05-08 12:35:29.1234567 +12:15|  
  
## <a name="see-also"></a>Voir aussi
[CAST et CONVERT &#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)
  
  
