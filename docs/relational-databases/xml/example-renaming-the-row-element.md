---
title: "Exemple : attribution d’un nouveau nom à l’élément &lt;row&gt; | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: xml
ms.reviewer: 
ms.suite: sql
ms.technology: dbe-xml
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: RAW mode, renaming <row> example
ms.assetid: b042292a-0b6e-40a3-b254-71c06e626706
caps.latest.revision: "9"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 9960c69603d27f873258279c45f0e29ae9f9cd10
ms.sourcegitcommit: 6c54e67818ec7b0a2e3c1f6e8aca0fdf65e6625f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2018
---
# <a name="example-renaming-the-ltrowgt-element"></a>Exemple : attribution d’un nouveau nom à l’élément &lt;row&gt;
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)] Pour chaque ligne du jeu de résultats, le mode RAW génère un élément `<row>`. Vous pouvez éventuellement spécifier un autre nom pour cet élément en spécifiant un argument facultatif pour le mode RAW, comme illustré dans cette requête. La requête retourne un élément <`ProductModel`> pour chaque ligne de l'ensemble de lignes.  
  
## <a name="example"></a> Exemple  
  
```  
SELECT ProductModelID, Name   
FROM Production.ProductModel  
WHERE ProductModelID=122  
FOR XML RAW ('ProductModel'), ELEMENTS  
GO  
```  
  
 Voici l'ensemble de résultats. La directive `ELEMENTS` étant ajoutée à la requête, le résultat est centré sur les éléments.  
  
```  
<ProductModel>  
  <ProductModelID>122</ProductModelID>  
  <Name>All-Purpose Bike Stand</Name>  
</ProductModel>   
```  
  
## <a name="see-also"></a> Voir aussi  
 [Utiliser le mode RAW avec FOR XML](../../relational-databases/xml/use-raw-mode-with-for-xml.md)  
  
  
