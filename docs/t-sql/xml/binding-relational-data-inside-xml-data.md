---
title: "Liaison de données relationnelles à l’intérieur des données XML | Documents Microsoft"
ms.custom: 
ms.date: 07/26/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|xml
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- relational data binding [SQL Server]
- XML [SQL Server], binding relational data
- xml data type [SQL Server], relational data binding
- binding relational data [XML in SQL Server]
- variables [XML in SQL Server], relational data binding
- columns [XML in SQL Server], relational data binding
ms.assetid: 03d013a9-b53f-46c3-9628-da77f099c74a
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 87dca9b5bcd70335a6121b1be1e49f4cc352826e
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="binding-relational-data-inside-xml-data"></a>Liaison de données relationnelles dans des données XML
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Vous pouvez spécifier [xml Data Type Methods](../../t-sql/xml/xml-data-type-methods.md) contre un **xml** variable ou une colonne de type de données. Par exemple, le [de requête &#40; &#41; Méthode &#40; Type de données xml &#41; ](../../t-sql/xml/query-method-xml-data-type.md) exécute l’expression XQuery spécifiée sur une instance XML. Lorsque vous construisez des données XML de cette manière, vous pouvez inclure une valeur à partir d'une colonne de type non-XML ou une variable Transact-SQL. Ce processus est appelé liaison de données relationnelles dans des données XML.  
  
 Pour lier les données relationnelles non-XML dans des données XML, le moteur de base de données SQL Server fournit les pseudo-fonctions suivantes :  
  
-   [SQL : Column &#40; &#41; Fonction &#40; XQuery &#41; ](../../xquery/xquery-extension-functions-sql-column.md) Vous permet d’utiliser les valeurs à partir d’une colonne relationnelle dans votre expression XQuery ou DML XML.  
  
-   [SQL : variable &#40; &#41; Fonction &#40; XQuery &#41; ](../../xquery/xquery-extension-functions-sql-variable.md) . Vous permet d'utiliser la valeur d'une variable SQL dans votre expression XQuery ou DML XML.  
  
 Vous pouvez utiliser ces fonctions avec **xml** méthodes du type de données chaque fois que vous souhaitez exposer une valeur relationnelle dans du code XML.  
  
 Vous ne pouvez pas utiliser ces fonctions pour référencer des données dans des colonnes ou des variables de la **xml**, CLR défini par l’utilisateur types, datetime, smalldatetime, **texte**, **ntext**, **sql_variant**, et **image** types.  
  
 En outre, cette liaison est destinée à un emploi en lecture seule. Cela signifie que vous ne pouvez pas écrire de données dans les colonnes qui utilisent ces fonctions. Par exemple, sql:variable("@x") = «*une expression «* n’est pas autorisée.  
  
## <a name="example-cross-domain-query-using-sqlvariable"></a>Exemple : requête inter-domaines utilisant sql:variable()  
 Cet exemple montre comment **SQL :variable()** peut permettre à une application de paramétrer une requête. Le numéro ISBN est passé à l’aide d’une variable SQL @isbn. En remplaçant la constante avec **SQL :variable()**, la requête peut être utilisée pour rechercher n’importe quel numéro ISBN et pas seulement le numéro ISBN est 0-7356-1588-2.  
  
```  
DECLARE @isbn varchar(20)  
SET     @isbn = '0-7356-1588-2'  
SELECT  xCol  
FROM    T  
WHERE   xCol.exist ('/book/@ISBN[. = sql:variable("@isbn")]') = 1  
```  
  
 **SQL :Column()** peut être utilisé de manière similaire et offre des avantages supplémentaires. Pour gagner en efficacité, vous pouvez placer des index sur la colonne, en suivant les suggestions de l'optimiseur de requête basé sur les coûts. De plus, la colonne calculée peut stocker une propriété promue.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes de type de données xml](../../t-sql/xml/xml-data-type-methods.md)  
  
  
