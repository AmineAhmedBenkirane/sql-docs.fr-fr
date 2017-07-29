---
title: "Conversion de données JSON en lignes et colonnes à l’aide d’OPENJSON (SQL Server) | Microsoft Docs"
ms.custom:
- SQL2016_New_Updated
ms.date: 07/18/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-json
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OPENJSON
- JSON, importing
- importing JSON
ms.assetid: 0c139901-01e2-49ef-9d62-57e08e32c68e
caps.latest.revision: 31
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.translationtype: HT
ms.sourcegitcommit: 50ef4db2a3c9eebcdf63ec9329eb22f1e0f001c0
ms.openlocfilehash: a7229bfe9c6924d2d7a79c861fe10c48db4b0c15
ms.contentlocale: fr-fr
ms.lasthandoff: 07/20/2017

---
# <a name="convert-json-data-to-rows-and-columns-with-openjson-sql-server"></a>Conversion de données JSON en lignes et colonnes à l’aide d’OPENJSON (SQL Server)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

La fonction d’ensemble de lignes **OPENJSON** convertit du texte JSON en un ensemble de lignes et de colonnes. Après avoir transformé une collection JSON en ensemble de lignes avec **OPENJSON**, vous pouvez exécuter n’importe quelle requête SQL sur les données retournées ou l’insérer dans une table SQL Server. 
  
La fonction **OPENJSON** prend un seul objet JSON ou une collection d’objets JSON, et les transforme en une ou plusieurs lignes. Par défaut, la fonction **OPENJSON** retourne les données suivantes :
-   À partir d’un objet JSON, toutes les paires clé-valeur qu’elle trouve au premier niveau.
-   À partir d’un tableau JSON, tous les éléments du tableau avec leurs index.  

Vous pouvez ajouter une clause **WITH** facultative afin de fournir un schéma qui définit explicitement la structure de la sortie.  
  
## <a name="option-1---openjson-with-the-default-output"></a>Option 1 : OPENJSON avec la sortie par défaut
Quand vous utilisez la fonction **OPENJSON** sans fournir un schéma explicite pour les résultats (autrement dit, sans clause **WITH** après **OPENJSON**), la fonction retourne une table comportant les trois colonnes suivantes :
1.  Le **nom** de la propriété dans l’objet d’entrée (ou l’index de l’élément dans le tableau d’entrée).
2.  La **valeur** de la propriété ou de l’élément du tableau.
3.  Le **type** (par exemple, chaîne, nombre, booléen, tableau ou objet).

**OPENJSON** retourne chaque propriété de l’objet JSON, ou chaque élément du tableau, sous la forme d’une ligne distincte.  

L’exemple ci-dessous utilise **OPENJSON** avec le schéma par défaut (autrement dit, sans la clause **WITH** facultative) et retourne une ligne pour chaque propriété de l’objet JSON.  
 
**Exemple**
```sql  
DECLARE @json NVARCHAR(MAX)

SET @json='{"name":"John","surname":"Doe","age":45,"skills":["SQL","C#","MVC"]}';

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

### <a name="more-info-about-openjson-with-the-default-schema"></a>Plus d’informations sur OPENJSON avec le schéma par défaut

Pour plus d’informations et pour obtenir des exemples, consultez [Utiliser OPENJSON avec le schéma par défaut &#40;SQL Server&#41;](../../relational-databases/json/use-openjson-with-the-default-schema-sql-server.md).

Pour plus d’informations sur la syntaxe et l’utilisation, consultez [OPENJSON &#40;Transact-SQL&#41;](../../t-sql/functions/openjson-transact-sql.md). 

    
## <a name="option-2---openjson-output-with-an-explicit-structure"></a>Option 2 : Sortie OPENJSON avec une structure explicite
Quand vous spécifiez un schéma pour les résultats à l’aide de la clause **WITH** de la fonction **OPENJSON**, la fonction retourne une table contenant uniquement les colonnes que vous définissez dans la clause **WITH**. Dans la clause **WITH** facultative, vous spécifiez un ensemble de colonnes de sortie, leurs types et les chemins des propriétés sources JSON pour chaque valeur de sortie. **OPENJSON** itère le tableau d’objets JSON, lit la valeur du chemin spécifié pour chaque colonne, puis convertit la valeur dans le type spécifié.  

L’exemple ci-dessous utilise **OPENJSON** avec un schéma pour la sortie que vous spécifiez de façon explicite dans la clause **WITH**.  
  
**Exemple**
  
```sql  
DECLARE @json NVARCHAR(MAX)
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
  
-   Pour chaque élément du tableau JSON, **OPENJSON** génère une nouvelle ligne dans la table de sortie. Les deux éléments du tableau JSON sont convertis en deux lignes dans la table retournée.  
  
-   Pour chaque colonne spécifiée à l’aide de la syntaxe `colName type json_path`, **OPENJSON** convertit la valeur trouvée dans chaque élément de tableau sur le chemin spécifié dans le type spécifié. Dans cet exemple, les valeurs de la colonne `Date` sont tirées de chaque élément sur le chemin `$.Order.Date` et converties en valeur datetime.  
  
### <a name="more-info-about-openjson-with-an-explicit-schema"></a>Plus d’informations sur OPENJSON avec un schéma explicite
Pour plus d’informations et pour obtenir des exemples, consultez [Utilisation d’OPENJSON avec un schéma explicite &#40;SQL Server&#41;](../../relational-databases/json/use-openjson-with-an-explicit-schema-sql-server.md).

Pour plus d’informations sur la syntaxe et l’utilisation, consultez [OPENJSON &#40;Transact-SQL&#41;](../../t-sql/functions/openjson-transact-sql.md).

## <a name="openjson-requires-compatibility-level-130"></a>OPENJSON exige le niveau de compatibilité 130
La fonction **OPENJSON** est disponible uniquement sous le **niveau de compatibilité 130**. Si le niveau de compatibilité de votre base de données est inférieur à 130, SQL Server ne peut pas trouver ni exécuter la fonction **OPENJSON**. Les autres fonctions JSON intégrées sont disponibles à tous les niveaux de compatibilité.

Vous pouvez vérifier le niveau de compatibilité dans la vue `sys.databases` ou dans les propriétés de base de données.

Vous pouvez modifier le niveau de compatibilité d’une base de données à l’aide de la commande suivante :   
`ALTER DATABASE <DatabaseName> SET COMPATIBILITY_LEVEL = 130`  

## <a name="learn-more-about-the-built-in-json-support-in-sql-server"></a>En savoir plus sur la fonction intégrée prise en charge de JSON dans SQL Server  
Pour un grand nombre de solutions spécifiques, utilisez des cas et des recommandations, consultez le [billets de blog sur la prise en charge intégrée de JSON](http://blogs.msdn.com/b/sqlserverstorageengine/archive/tags/json/) dans SQL Server et dans la base de données SQL Azure par programme Jovan Popovic Gestionnaire Microsoft.
  
## <a name="see-also"></a>Voir aussi  
 [OPENJSON &#40;Transact-SQL&#41;](../../t-sql/functions/openjson-transact-sql.md)  
  
  

