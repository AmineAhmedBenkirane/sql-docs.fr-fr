---
title: "Fonctions d’accesseur de données | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
dev_langs:
- XML
helpviewer_keywords:
- data-accessor functions [XQuery]
ms.assetid: 31bad04f-7c74-4773-9f83-612704fdd21c
caps.latest.revision: 30
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 456d359fd407e305bc8bfb3b85bd29b7bada8382
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="data-accessor-functions"></a>Fonctions d'accesseurs de données
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Les rubriques de cette section présentent les fonctions d'accès aux données et les illustrent avec des exemples de code.  
  
## <a name="understanding-fndata-fnstring-and-text"></a>Fonctionnement de fn:data(), fn:string () et text()  
 XQuery fournit une fonction **fn :Data()** pour extraire des valeurs scalaires, typés à partir des nœuds, un test de nœud **text()** pour renvoyer les nœuds de texte et la fonction **fn :String()** qui retourne la valeur de chaîne d’un nœud. Leur utilisation peut prêter à confusion. Vous trouverez ci-après des instructions relatives à leur bonne utilisation dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. L’instance XML \<age > 12\</ l’âge > est utilisé aux fins d’illustration.  
  
-   XML non typé : l'expression de chemin d'accès /age/text() retourne le nœud de texte "12". Les fonctions fn:data(/age) et fn:string(/age) retournent la valeur de chaîne "12".  
  
-   XML typé : L’expression /age/text() renvoie une erreur statique pour tout simple typé \<âge > élément. En revanche, la fonction fn:data (/age) retourne l'entier 12. La fonction fn:string(/age) produit la chaîne "12".  
  
## <a name="in-this-section"></a>Dans cette section  
  
-   [chaîne Function &#40; XQuery &#41;](../xquery/data-accessor-functions-string-xquery.md)  
  
-   [Fonction de données &#40; XQuery &#41;](../xquery/data-accessor-functions-data-xquery.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions de chemin &#40; XQuery &#41;](../xquery/path-expressions-xquery.md)  
  
  

