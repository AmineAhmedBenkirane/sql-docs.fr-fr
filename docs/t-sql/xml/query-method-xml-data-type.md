---
title: "Méthode query() (type de données xml) | Microsoft Docs"
ms.custom: 
ms.date: 07/26/2017
ms.prod: sql-non-specified
ms.prod_service: sql-database
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
- query method
- query() method
ms.assetid: f48f6f7b-219f-463a-bf36-bc10f21afaeb
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Active
ms.openlocfilehash: 4ec43116cf548df0a6f3541ab882635331f1b395
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="query-method-xml-data-type"></a>Méthode query() (type de données xml)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Spécifie une requête Xml sur une instance du type de données **XML**. Le résultat est de type **xml**. La méthode renvoie une instance XML non typé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
query ('XQuery')  
```  
  
## <a name="arguments"></a>Arguments  
 XQuery  
 Expression XQuery de type chaîne, qui interroge les nœuds XML, tels que des éléments ou des attributs, dans une instance XML.  
  
## <a name="examples"></a>Exemples  
 Cette section propose des exemples d’utilisation de la méthode query() de type de données **xml**.  
  
### <a name="a-using-the-query-method-against-an-xml-type-variable"></a>A. Utilisation de la méthode query() sur une variable de type xml  
 L’exemple suivant déclare une variable **@myDoc** de type **xml** et lui affecte une instance XML. La méthode **query()** est ensuite utilisée pour spécifier une requête Xml portant sur le document.  
  
 La requête récupère l'élément enfant <`Features`> provenant de l'élément <`ProductDescription`>.  
  
```  
declare @myDoc xml  
set @myDoc = '<Root>  
<ProductDescription ProductID="1" ProductName="Road Bike">  
<Features>  
  <Warranty>1 year parts and labor</Warranty>  
  <Maintenance>3 year parts and labor extended maintenance is available</Maintenance>  
</Features>  
</ProductDescription>  
</Root>'  
SELECT @myDoc.query('/Root/ProductDescription/Features')  
```  
  
 Voici le résultat obtenu :  
  
```  
<Features>  
  <Warranty>1 year parts and labor</Warranty>  
  <Maintenance>3 year parts and labor extended maintenance is available</Maintenance>  
</Features>        
```  
  
### <a name="b-using-the-query-method-against-an-xml-type-column"></a>B. Utilisation de la méthode query() sur une colonne de type XML  
 Dans l’exemple suivant, la méthode **query()** est utilisée pour indiquer une requête Xml portant sur la colonne **CatalogDescription** de type **xml** tirée de la base données **AdventureWorks** :  
  
```  
SELECT CatalogDescription.query('  
declare namespace PD="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
<Product ProductModelID="{ /PD:ProductDescription[1]/@ProductModelID }" />  
') as Result  
FROM Production.ProductModel  
where CatalogDescription.exist('  
declare namespace PD="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
declare namespace wm="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain";  
     /PD:ProductDescription/PD:Features/wm:Warranty ') = 1  
```  
  
 Notez les points suivants dans la requête précédente :  
  
-   La colonne CatalogDescription est une colonne **xml** typée. En d'autres termes, elle possède une collection de schémas qui lui est associée. Dans le [prologue de la requête Xml](../../xquery/modules-and-prologs-xquery-prolog.md), le mot clé **namespace** est utilisé pour définir le préfixe utilisé plus loin dans le corps de la requête.  
  
-   La méthode **query()** construit un élément <`Product`> XML qui a un attribut **ProductModelID** dans lequel la valeur de l’attribut **ProductModelID** est récupérée à partir de la base de données. Pour plus d’informations sur la construction XML, consultez [Construction XML &#40;requête Xml&#41;](../../xquery/xml-construction-xquery.md).  
  
-   La [méthode exist() (type de données XML)](../../t-sql/xml/exist-method-xml-data-type.md) indiquée dans la clause WHERE est utilisée pour ne rechercher que les lignes contenant l’élément <`Warranty`> dans le code XML. Une fois encore, le mot clé **namespace** permet de définir deux préfixes d’espace de noms.  
  
 Voici le résultat partiel :  
  
```  
<Product ProductModelID="19"/>   
<Product ProductModelID="23"/>   
...  
```  
  
 Remarque : les méthodes query() et exist() déclarent toutes deux le préfixe PD. Quand de tels cas se présentent, vous pouvez utiliser WITH XMLNAMESPACES pour définir au préalable les préfixes et les utiliser dans la requête.  
  
```  
WITH XMLNAMESPACES (  
   'http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' AS PD,  
   'http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain' AS wm)  
SELECT CatalogDescription.query('  
<Product ProductModelID="{ /PD:ProductDescription[1]/@ProductModelID }" />  
') as Result  
FROM Production.ProductModel  
where CatalogDescription.exist('  
     /PD:ProductDescription/PD:Features/wm:Warranty ') = 1  
```  
  
## <a name="see-also"></a> Voir aussi  
 [Ajouter des espaces de noms aux requêtes avec WITH XMLNAMESPACES](../../relational-databases/xml/add-namespaces-to-queries-with-with-xmlnamespaces.md)   
 [Comparer du XML typé et du XML non typé](../../relational-databases/xml/compare-typed-xml-to-untyped-xml.md)   
 [Créer des instances de données XML](../../relational-databases/xml/create-instances-of-xml-data.md)   
 [méthodes de type de données xml](../../t-sql/xml/xml-data-type-methods.md)   
 [Langage de manipulation de données XML &#40;DML XML&#41;](../../t-sql/xml/xml-data-modification-language-xml-dml.md)  
  
  
