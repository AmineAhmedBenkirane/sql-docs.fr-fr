---
title: "Conversion de donn&#233;es JSON en lignes et colonnes &#224; l’aide d’OPENJSON (SQL&#160;Server) | Microsoft Docs"
ms.custom: 
  - "SQL2016_New_Updated"
ms.date: "01/31/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-json"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "OPENJSON"
  - "JSON, importation"
  - "importation de JSON"
ms.assetid: 0c139901-01e2-49ef-9d62-57e08e32c68e
caps.latest.revision: 31
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 27
---
# Conversion de donn&#233;es JSON en lignes et colonnes &#224; l’aide d’OPENJSON (SQL&#160;Server)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  La fonction d’ensemble de lignes **OPENJSON** vous permet de convertir du texte JSON en un ensemble de lignes et de colonnes. Vous pouvez utiliser **OPENJSON** pour exécuter des requêtes SQL sur des collections JSON ou pour importer du texte JSON dans des tables SQL Server.  
  
> [!NOTE] La fonction **OPENJSON** est disponible uniquement sous le **niveau de compatibilité 130**. Si votre niveau de compatibilité de base de données est inférieur à 130, SQL Server ne pourra pas trouver et exécuter la fonction **OPENJSON**. Les autres fonctions JSON sont disponibles à tous les niveaux de compatibilité. Vous pouvez vérifier le niveau de compatibilité dans la vue sys.databases ou dans les propriétés de base de données.
> 
>   Vous pouvez modifier un niveau de compatibilité de base de données à l’aide de la commande suivante :   
>   ALTER DATABASE nom_base_de_données SET COMPATIBILITY_LEVEL = 130  
  
 La fonction **OPENJSON** prend un objet JSON ou une collection d’objets JSON et les transforme en une ou plusieurs lignes. Par défaut, la fonction **OPENJSON** retourne toutes les paires clé:valeur qui se trouvent au premier niveau de l’objet JSON, ou tous les éléments dans les tableaux JSON avec leurs index.  
  
 Vous pouvez spécifier le schéma des lignes retournées par la fonction **OPENJSON** avec la clause WITH. Ce schéma explicite définit la structure de la sortie.  
  
## Utiliser OPENJSON sans le schéma de résultats

L’exemple ci-dessous utilise **OPENJSON**  avec le schéma par défaut et retourne une ligne pour chaque propriété de l’objet JSON.  
 
Quand vous utilisez la fonction **OPENJSON** sans spécifier le schéma des résultats retournés (autrement dit, sans spécifier de clause WITH après OPENJSON), la fonction retourne une table avec trois colonnes : nom de propriété dans l’objet d’entrée (ou index de l’élément dans le tableau d’entrée), valeur de propriété ou élément de tableau, et type (par exemple chaîne, nombre, booléen, tableau ou objet). Les propriétés de l’objet JSON (ou des éléments de tableau) sont retournées dans des lignes distinctes.  

-   Pour plus d’informations et pour obtenir des exemples, consultez [Utiliser OPENJSON avec le schéma par défaut &#40;SQL Server&#41;](../../relational-databases/json/use-openjson-with-the-default-schema-sql-server.md).
-   Pour plus d’informations sur la syntaxe et l’utilisation, consultez [OPENJSON &#40;Transact-SQL&#41;](../../t-sql/functions/openjson-transact-sql.md). 

```tsql  
SET @json = '{"name":"John","surname":"Doe","age":45,"skills":["SQL","C#","MVC"]}';  
  
SELECT *  
FROM OPENJSON(@json);  
```  
  
**Résultats**  
  
|Clé|valeur|type|  
|---------|-----------|----------|  
|name|John|1|  
|surname|Doe|1|  
|age|45|2|  
|skills|["SQL","C#","MVC"]|4|
    
## Utiliser OPENJSON avec un schéma explicite

Voici un exemple rapide qui utilise **OPENJSON** avec un schéma spécifié de façon explicite.  
  
Quand vous spécifiez le schéma des résultats retournés dans la clause WITH de la fonction **OPENJSON**, la fonction retourne une table contenant les colonnes que vous définissez dans la clause WITH. Dans la clause WITH, vous pouvez spécifier les colonnes de sortie, leurs types et les chemins des propriétés JSON sources pour chaque valeur de sortie. **OPENJSON** itère le tableau d’objets JSON, lit la valeur du chemin spécifié pour chaque colonne, et convertit la valeur en type spécifié.  

-   Pour plus d’informations et pour obtenir des exemples, consultez [Utilisation d’OPENJSON avec un schéma explicite &#40;SQL Server&#41;](../../relational-databases/json/use-openjson-with-an-explicit-schema-sql-server.md).
-   Pour plus d’informations sur la syntaxe et l’utilisation, consultez [OPENJSON &#40;Transact-SQL&#41;](../../t-sql/functions/openjson-transact-sql.md).
  
```tsql  
SET @json =   
 N'[  
      {  
        "Order": {  
          "Number":"SO43659",  
          "Date":"2011-05-31T00:00:00"  
        },  
        "AccountNumber":"AW29825",  
        "Item": {  
          "Price":2024.9940,  
          "Quantity":1  
        }  
      },  
      {  
        "Order": {  
          "Number":"SO43661",  
          "Date":"2011-06-01T00:00:00"  
        },  
        "AccountNumber":"AW73565",  
        "Item": {  
          "Price":2024.9940,  
          "Quantity":3  
        }  
     }  
]'  
  
SELECT * FROM  
OPENJSON ( @json )  
WITH (   
             Number   varchar(200) '$.Order.Number' ,  
             Date     datetime     '$.Order.Date',  
             Customer varchar(200) '$.AccountNumber',  
             Quantity int          '$.Item.Quantity'  
)  
```  
  
**Résultats**  
  
|Number|Date|Customer|Quantité|  
|------------|----------|--------------|--------------|  
|SO43659|2011-05-31T00:00:00|AW29825|1|  
|SO43661|2011-06-01T00:00:00|AW73565|3|  
  
 Cette fonction retourne et met en forme les éléments d’un tableau JSON.  
  
-   Pour chaque élément du tableau JSON, **OPENJSON** génère une nouvelle ligne dans la table de sortie. Deux éléments du tableau JSON sont convertis en deux lignes dans la table retournée.  
  
-   Pour chaque colonne, spécifiée à l’aide de la syntaxe `colName type json_path`, la fonction **OPENJSON** convertit la valeur trouvée dans les éléments de tableau au chemin spécifié, les convertit en type spécifié, et remplit une cellule dans la table de sortie. Dans cet exemple, les valeurs de la colonne Date sont tirées de chaque objet sur un chemin `$.Order.Date` et converties en valeur datetime.  
  
Une fois que vous avez transformé la collection JSON en ensemble de lignes, vous pouvez exécuter n’importe quelle requête SQL sur les données retournées ou les insérer dans une table.  
  
## En savoir plus sur OPENJSON et la prise en charge intégrée de JSON dans SQL Server  
 [Billets de blog de Jovan Popovic, gestionnaire de programmes Microsoft](http://blogs.msdn.com/b/sqlserverstorageengine/archive/tags/json/)  
  
## Voir aussi  
 [OPENJSON &#40;Transact-SQL&#41;](../../t-sql/functions/openjson-transact-sql.md)  
  
  