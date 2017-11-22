---
title: Supprimer les crochets de JSON - Option WITHOUT_ARRAY_WRAPPER | Microsoft Docs
ms.custom: 
ms.date: 06/02/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: json
ms.reviewer: 
ms.suite: sql
ms.technology: dbe-json
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WITHOUT_ARRAY_WRAPPER
ms.assetid: aa86c2d1-458e-465f-abfa-75470137d054
caps.latest.revision: "11"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 8cf8eb9559743275d1a742b62fc9b399fb811483
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="remove-square-brackets-from-json---withoutarraywrapper-option"></a>Supprimer les crochets de JSON - Option WITHOUT_ARRAY_WRAPPER
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]

Pour supprimer les crochets qui entourent par défaut la sortie JSON de la clause **FOR JSON**, spécifiez l’option **WITHOUT_ARRAY_WRAPPER**. Utilisez cette option avec un résultat d’une seule ligne pour générer un seul objet JSON en tant que sortie au lieu d’un tableau avec un seul élément.

Si vous utilisez cette option avec un résultat de plusieurs lignes, la sortie résultante n’est pas un JSON valide en raison de la présence de plusieurs éléments et de l’absence de crochets.  
  
## <a name="example-single-row-result"></a>Exemple (résultat d’une seule ligne)  
L’exemple suivant montre la sortie de la clause **FOR JSON** avec et sans l’option **WITHOUT_ARRAY_WRAPPER** .  
  
 **Requête**  
  
```sql  
SELECT 2015 as year, 12 as month, 15 as day  
FOR JSON PATH, WITHOUT_ARRAY_WRAPPER 
```  

 **Résultat** avec l’option **WITHOUT_ARRAY_WRAPPER**  
  
```json  
{
    "year": 2015,
    "month": 12,
    "day": 15
} 
```  
  
 **Résultat** (par défaut) sans l’option **WITHOUT_ARRAY_WRAPPER**  
  
```json  
[{
    "year": 2015,
    "month": 12,
    "day": 15
}]
```  

## <a name="example-multiple-row-result"></a>Exemple (résultat de plusieurs lignes)
Voici un autre exemple de clause **FOR JSON** avec et sans l’option **WITHOUT_ARRAY_WRAPPER** . Cet exemple produit un résultat de plusieurs lignes. La sortie n’est pas un JSON valide en raison de la présence de plusieurs éléments et de l’absence de crochets.
  
 **Requête**  
  
```sql  
SELECT TOP 3 SalesOrderNumber, OrderDate, Status  
FROM Sales.SalesOrderHeader  
ORDER BY ModifiedDate  
FOR JSON PATH, WITHOUT_ARRAY_WRAPPER 
```  
  
 **Résultat** avec l’option **WITHOUT_ARRAY_WRAPPER**  
  
```json  
{
    "SalesOrderNumber": "SO43662",
    "OrderDate": "2011-05-31T00:00:00",
    "Status": 5
}, {
    "SalesOrderNumber": "SO43661",
    "OrderDate": "2011-05-31T00:00:00",
    "Status": 5
}, {
    "SalesOrderNumber": "SO43660",
    "OrderDate": "2011-05-31T00:00:00",
    "Status": 5
} 
```  
  
 **Résultat** (par défaut) sans l’option **WITHOUT_ARRAY_WRAPPER**  
  
```json  
[{
    "SalesOrderNumber": "SO43662",
    "OrderDate": "2011-05-31T00:00:00",
    "Status": 5
}, {
    "SalesOrderNumber": "SO43661",
    "OrderDate": "2011-05-31T00:00:00",
    "Status": 5
}, {
    "SalesOrderNumber": "SO43660",
    "OrderDate": "2011-05-31T00:00:00",
    "Status": 5
}]
```  

## <a name="learn-more-about-the-built-in-json-support-in-sql-server"></a>En savoir plus sur la prise en charge intégrée de JSON dans SQL Server  
Pour accéder à un grand nombre de solutions spécifiques, de cas d’usage et de recommandations, consultez les [billets de blog sur la prise en charge intégrée de JSON](http://blogs.msdn.com/b/sqlserverstorageengine/archive/tags/json/) dans SQL Server et Azure SQL Database, écrits par Jovan Popovic (Microsoft Program Manager).
  
## <a name="see-also"></a>Voir aussi  
 [Clause FOR &#40;Transact-SQL&#41;](../../t-sql/queries/select-for-clause-transact-sql.md)  
  
  
