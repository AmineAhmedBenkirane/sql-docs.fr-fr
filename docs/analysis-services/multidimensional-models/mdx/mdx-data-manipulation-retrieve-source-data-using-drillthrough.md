---
title: "Utilisation de l’extraction pour récupérer la Source de données (MDX) | Documents Microsoft"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: multidimensional-models
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DRILLTHROUGH statement
- retrieving data
- queries [MDX], DRILLTHROUGH statement
- data retrieval [MDX]
ms.assetid: fe0ab170-25a9-45a8-a377-f71a67f77018
caps.latest.revision: "30"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 7d7eecd743e66ad33e029e5d575b9ab4a8b2a988
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="mdx-data-manipulation---retrieve-source-data-using-drillthrough"></a>Manipulation de données MDX - extraire à l’aide de l’extraction des données Source
  L’instruction MDX (Multidimensional Expressions) utilise l’instruction [DRILLTHROUGH](../../../mdx/mdx-data-manipulation-drillthrough.md)pour récupérer un ensemble de lignes à partir des données sources d’une cellule d’un cube.  
  
 Pour exécuter une instruction **DRILLTHROUGH** sur un cube, une action d’extraction doit être définie pour ce dernier. Pour définir une action d’extraction, dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], dans le Concepteur de cube, dans la barre d’outils du volet **Actions** , cliquez sur **Nouvelle action d’extraction**. Dans la nouvelle action d’extraction, spécifiez le nom de l’action, la cible, la condition et les colonnes retournées par une instruction **DRILLTHROUGH** .  
  
## <a name="drillthrough-statement-syntax"></a>Syntaxe de l'instruction DRILLTHROUGH  
 L’instruction **DRILLTHROUGH** utilise la syntaxe suivante :  
  
```  
<drillthrough> ::= DRILLTHROUGH [<Max_Rows>] [<First_Rowset>] <MDX select> [<Return_Columns>]  
   < Max_Rows> ::= MAXROWS <positive number>  
   <First_Rowset> ::= FIRSTROWSET <positive number>  
   <Return_Columns> ::= RETURN <member or attribute> [, <member or attribute>]  
```  
  
 La clause **SELECT** identifie la cellule du cube qui contient les données sources à récupérer. Cette clause **SELECT** est identique à une instruction **SELECT** MDX ordinaire, à la différence qu’un seul membre peut être spécifié sur chaque axe dans la clause **SELECT** . Si plusieurs membres sont spécifiés sur un axe, une erreur se produit.  
  
 La syntaxe `<Max_Rows>` spécifie le nombre maximum de lignes de chaque ensemble de lignes retourné. Si le fournisseur OLE DB utilisé pour la connexion à la source de données ne prend pas en charge **DBPROP_MAXROWS**, le paramètre `<Max_Rows>` est ignoré.  
  
 La syntaxe `<First_Rowset>` identifie la partition d’où l’ensemble de lignes est d’abord retourné.  
  
 La syntaxe `<Return_Columns>` identifie les colonnes de la base de données sous-jacente à retourner.  
  
## <a name="drillthrough-statement-example"></a>Exemple d'instruction DRILLTHROUGH  
 L’exemple suivant illustre l’utilisation de l’instruction **DRILLTHROUGH** . Dans cet exemple, l'instruction DRILLTHROUGH interroge les feuilles des dimensions Store, Product et Time le long de la dimension Stores (axe de découpage), puis retourne le groupe de mesures du service, l'ID de service et le prénom de l'employé.  
  
```  
DRILLTHROUGH  
Select {Leaves(Store), Leaves(Product), Leaves(Time),*} on 0  
From Stores  
RETURN [Department MeasureGroup].[Department Id], [Employee].[First Name]  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Manipulation de données &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/mdx-data-manipulation-manipulating-data.md)  
  
  
