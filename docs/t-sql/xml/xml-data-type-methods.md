---
title: "les méthodes de Type de données XML | Documents Microsoft"
ms.custom: 
ms.date: 03/16/2017
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
- xml data type [SQL Server], methods
- methods [XML in SQL Server]
ms.assetid: d112b9c9-be9f-435c-a9e6-d21b65778fb7
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 3a08e2e0c49c707150df9f350cb9060203fd6f62
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="xml-data-type-methods"></a>Méthodes des types de données xml
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Vous pouvez utiliser la **xml** méthodes pour interroger une instance XML stockée dans une variable ou une colonne de type de données **xml** type. Les rubriques de cette section décrivent comment utiliser le **xml** méthodes du type de données.  
  
## <a name="in-this-section"></a>Dans cette section  
  
|Rubrique| Description|  
|-----------|-----------------|  
|[requête &#40; &#41; Méthode &#40; Type de données xml &#41;](../../t-sql/xml/query-method-xml-data-type.md)|Décrit comment utiliser la méthode query() pour interroger une instance XML.|  
|[valeur &#40; &#41; Méthode &#40; Type de données xml &#41;](../../t-sql/xml/value-method-xml-data-type.md)|Décrit comment utiliser la méthode value() pour récupérer une valeur de type SQL d'une instance XML.|  
|[existe &#40; &#41; Méthode &#40; Type de données xml &#41;](../../t-sql/xml/exist-method-xml-data-type.md)|Décrit comment utiliser la méthode exist() pour déterminer si une requête retourne un résultat non vide.|  
|[Modifier &#40; &#41; Méthode &#40; Type de données xml &#41;](../../t-sql/xml/modify-method-xml-data-type.md)|Décrit comment utiliser la méthode modify() pour spécifier [XML Data Modification Language &#40; XML DML &#41; ](../../t-sql/xml/xml-data-modification-language-xml-dml.md)instructions pour effectuer des mises à jour.|  
|[nœuds &#40; &#41; Méthode &#40; Type de données xml &#41;](../../t-sql/xml/nodes-method-xml-data-type.md)|Décrit comment utiliser la méthode nodes() pour fragmenter du code XML en plusieurs lignes, ce qui permet de propager des parties de documents XML dans des ensembles de lignes.|  
|[Liaison de données relationnelles dans des données XML](../../t-sql/xml/binding-relational-data-inside-xml-data.md)|Décrit comment lier des données non-XML à l'intérieur de code XML.|  
|[Instructions pour l’utilisation des méthodes de type de données XML](../../t-sql/xml/guidelines-for-using-xml-data-type-methods.md)|Décrit comment utiliser le **xml** méthodes du type de données.|  
  
 Vous appelez ces méthodes au moyen de la syntaxe d'appel de méthode de type défini par l'utilisateur. Par exemple :  
  
```  
SELECT XmlCol.query(' ... ')  
FROM   Table  
```  
  
> [!NOTE]  
>  Le **xml** méthodes du type de données **query()**, **value()**, et **exist()** retourne NULL si exécutées sur une instance XML NULL. En outre, **modify()** ne retourne rien, mais **nodes()** retourne les ensembles de lignes et un ensemble de lignes vide avec une entrée NULL.  
  
## <a name="see-also"></a>Voir aussi  
 [Comparer du XML typé et du XML non typé](../../relational-databases/xml/compare-typed-xml-to-untyped-xml.md)   
 [Créer des instances de données XML](../../relational-databases/xml/create-instances-of-xml-data.md)  
  
  
