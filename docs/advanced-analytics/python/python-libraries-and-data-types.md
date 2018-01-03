---
title: "Bibliothèques de Python | Documents Microsoft"
ms.custom: 
ms.date: 03/30/2017
ms.reviewer: 
ms.suite: sql
ms.prod: machine-learning-services
ms.prod_service: machine-learning-services
ms.component: python
ms.technology: r-services
ms.tgt_pltfrm: 
ms.topic: article
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: f5ca6889b9f64475d5c2beeba5e15e009bc4710f
ms.sourcegitcommit: 23433249be7ee3502c5b4d442179ea47305ceeea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2017
---
# <a name="python-libraries-and-data-types"></a>Les Types de données et les bibliothèques de Python

Cette rubrique décrit les bibliothèques de Python inclus avec les produits suivants :

+ Ordinateur SQL Server Learning Services (de-de base de données)
+ Microsoft Machine Learning Server (autonome)

Cette rubrique répertorie également les types de données non pris en charge, et répertorie le type de données pour les conversions qui peuvent être effectuées implicitement les données passées entre Python et SQL Server.

## <a name="python-version"></a>Version Python

SQL Server 2017 CTP 2.0 comprend une partie de la distribution Anaconda et Python 3.6.

Un sous-ensemble des fonctionnalités RevoScaleR (rxLinMod, rxLogit, rxPredict, rxDTrees, rxBTrees, cette opération peut prendre quelques autres) est fourni à l’aide des API de Python, à l’aide d’un nouveau package Python **RevoScalePy**. Vous pouvez utiliser ce package pour travailler avec des données à l’aide des trames de données Pandas. Les fichiers XDF, ou les requêtes de données SQL.

Pour plus d’informations, consultez [revoscalepy de nouveautés ?](what-is-revoscalepy.md).

## <a name="python-and-sql-data-types"></a>Python et les Types de données SQL

Python prend en charge un nombre limité de types de données par rapport à SQL Server.

Par conséquent, lorsque vous utilisez des données à partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans les scripts Python, des données peuvent être converties implicitement en un type de données compatible. Toutefois, souvent une conversion exacte ne peut pas être effectuée automatiquement, et une erreur est retournée.

Ce tableau répertorie les conversions implicites sont fournies. Autres types de données ne sont pas pris en charge.

|SQLtype|Type de Python|
|-|-|
|**bigint**|`numeric`|
|**binaire**|`raw`|
|**bit**|`bool`|
|**char**|`str`|
|**float**|`float64`|
|**Int**|`int32`|
|**nchar**|`str`|
|**nvarchar**|`str`|
|**nvarchar(max)**|`str`|
|**real**|`float32`|
|**smallint**|`int16`|
|**tinyint**|`uint8`|
|**varbinary**|`bytes`|
|**varbinary(max)**|`bytes`|
|**varchar(n)**|`str`|
|**varchar(max)**|`str`|



