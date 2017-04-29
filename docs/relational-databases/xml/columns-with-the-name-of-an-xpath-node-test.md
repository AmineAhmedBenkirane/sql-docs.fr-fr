---
title: "Colonnes avec le nom d’un test de nœud XPath | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-xml
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [SQL Server], columns with
- XPath node test
ms.assetid: b48adccd-3b6b-486a-b326-20f57170186f
caps.latest.revision: 10
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 41bc7b31ff9f5185dcdfde4a90bbfe631fbef089
ms.lasthandoff: 04/11/2017

---
# <a name="columns-with-the-name-of-an-xpath-node-test"></a>Colonnes avec le nom d'un test de nœud XPath
  Si le nom de colonne est l'un des tests de nœud XPath, le contenu est mappé comme le montre le tableau ci-après. Lorsque le nom de colonne est un test de nœud XPath, le contenu est mappé au nœud correspondant. Si le type SQL de la colonne est **xml**, une erreur est retournée.  
  
|Nom de la colonne|Comportement|  
|-----------------|--------------|  
|text()|Dans le cas d'une colonne nommée text(), la valeur de chaîne contenue dans cette colonne est ajoutée en tant que nœud de texte.|  
|comment()|Dans le cas d'une colonne nommée comment(), la valeur de chaîne contenue dans cette colonne est ajoutée en tant que commentaire XML.|  
|node()|Dans le cas d'une colonne nommée node(), le résultat est le même que lorsque le nom de colonne est un caractère générique (*).|  
|processing-instruction(name)|Dans le cas d'une colonne dont le nom est une instruction de traitement, la valeur de chaîne contenue dans cette colonne est ajoutée en tant que valeur PI du nom cible de l'instruction de traitement.|  
  
 La requête suivante affiche l'utilisation des tests de nœud comme noms de colonne. Elle ajoute des nœuds de texte et des commentaires dans le document XML obtenu.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT E.BusinessEntityID "@EmpID",   
        'Example of using node tests such as text(), comment(), processing-instruction()'                as "comment()",  
        'Some PI'                   as "processing-instruction(PI)",  
        'Employee name and address data' as "text()",  
        'middle name is optional'        as "EmpName/text()",  
        FirstName                        as "EmpName/First",   
        MiddleName                       as "EmpName/Middle",   
        LastName                         as "EmpName/Last",  
        AddressLine1                     as "Address/AddrLine1",  
        AddressLine2                     as "Address/AddrLIne2",  
        City                             as "Address/City"  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P   
    ON P.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.BusinessEntityAddress AS BAE  
    ON BAE.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.Address AS A  
    ON BAE.AddressID = A.AddressID  
WHERE  E.BusinessEntityID=1  
FOR XML PATH;  
```  
  
 Voici le résultat obtenu :  
  
 `<row EmpID="1">`  
  
 `<!--Example of using node tests such as text(), comment(), processing-instruction() -->`  
  
 `<?PI Some PI?>`  
  
 `Employee name and address data`  
  
 `<EmpName>middle name is optional`  
  
 `<First>Ken</First>`  
  
 `<Last>Sánchez</Last>`  
  
 `</EmpName>`  
  
 `<Address>`  
  
 `<AddrLine1>4350 Minute Dr.</AddrLine1>`  
  
 `<City>Minneapolis</City>`  
  
 `</Address>`  
  
 `</row>`  
  
## <a name="see-also"></a>Voir aussi  
 [Utiliser le mode PATH avec FOR XML](../../relational-databases/xml/use-path-mode-with-for-xml.md)  
  
  
