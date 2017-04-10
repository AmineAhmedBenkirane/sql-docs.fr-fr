---
title: "Noms de colonnes avec le chemin d&#39;acc&#232;s sp&#233;cifi&#233; sous la forme data() | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-xml"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "noms [SQL Server], colonnes avec"
ms.assetid: 0b738e44-6108-4417-a9a4-abeb7680d899
caps.latest.revision: 10
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 10
---
# Noms de colonnes avec le chemin d&#39;acc&#232;s sp&#233;cifi&#233; sous la forme data()
  Si le chemin d'accès spécifié comme nom de colonne est « data() », la valeur est traitée en tant que valeur atomique dans le document XML généré. Un espace est ajouté au document XML si l'élément suivant dans la sérialisation est également une valeur atomique. Cela est utile lorsque vous créez une liste de valeurs d'élément et d'attribut de type liste. La requête suivante extrait l'ID de modèle, le nom et la liste des produits pour le modèle concerné.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID       AS "@ProductModelID",  
       Name                 AS "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
      FOR XML PATH (''))    AS "@ProductIDs"  
FROM  Production.ProductModel  
WHERE ProductModelID= 7   
FOR XML PATH('ProductModelData');  
```  
  
 L'instruction SELECT imbriquée extrait une liste d'ID de produit. Elle spécifie « data() » comme nom de colonne pour les ID de produit. Étant donné que le mode PATH spécifie une chaîne vide pour le nom d'élément de ligne, aucun élément de ligne n'est généré. À la place, les valeurs sont renvoyées comme étant affectées à un attribut ProductIDs de l'élément de ligne <`ProductModelData`> de l'instruction SELECT parente. Voici le résultat obtenu :  
  
 `<ProductModelData ProductModelID="7"`  
  
 `ProductModelName="HL Touring Frame"`  
  
 `ProductIDs="885 887 888 889 890 891 892 893" />`  
  
## Voir aussi  
 [Utiliser le mode PATH avec FOR XML](../../relational-databases/xml/use-path-mode-with-for-xml.md)  
  
  