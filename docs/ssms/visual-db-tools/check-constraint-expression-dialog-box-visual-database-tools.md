---
title: "Expression de contrainte de validation, boîte de dialogue (Visual Database Tools) | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vdt.dlgbox.checkconstraintexpression
ms.assetid: beb6ce43-3913-4d66-8826-8e885335b790
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: jhubbard
ms.workload: Inactive
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 2d768a6db424008daaffdcb5b14491adfa48962f
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="check-constraint-expression-dialog-box-visual-database-tools"></a>Boîte de dialogue Expression de contrainte de validation (Visual Database Tools)
Lorsque vous rattachez une contrainte de validation à une table ou une colonne, vous devez inclure une expression SQL. Entrez l'expression de contrainte de validation dans la zone fournie à cet effet.  
  
## <a name="uielement-list"></a>Liste des éléments de l'interface utilisateur  
Expression  
Entrez l'expression  
  
Vous pouvez créer une expression de contrainte simple pour valider les données en fonction d'une condition simple ou créer une expression complexe, à l'aide d'opérateurs booléens, pour valider les données en fonction de plusieurs conditions. Supposons, par exemple, que la table authors comporte une colonne zip nécessitant une chaîne de caractères de 5 chiffres. L'expression de contrainte suivante permet de s'assurer que seuls les nombres de 5 chiffres sont acceptés :  
  
```  
zip LIKE '[0-9][0-9][0-9][0-9][0-9]'  
```  
  
Ou imaginons que la table sales comporte une colonne qty dans laquelle il est nécessaire d'entrer des valeurs supérieures à 0. L'expression de contrainte suivante assure que cette colonne contiendra exclusivement des valeurs positives :  
  
```  
qty > 0  
```  
  
Ou supposons que la table orders indique le type de cartes de crédit qu'il est nécessaire de posséder pour passer une commande. La contrainte suivante garantit que seules les cartes de crédit Visa, MasterCard ou American Express sont acceptées :  
  
```  
NOT (payment_method = 'credit card') OR  
   (card_type IN ('VISA', 'MASTERCARD', 'AMERICAN EXPRESS'))  
```  
  
## <a name="to-define-a-constraint-expression"></a>Pour définir une expression de contrainte  
Sous l'onglet Vérifier les contraintes des pages de propriétés, tapez l'expression dans la zone Expression de contrainte en respectant la syntaxe suivante :  
  
<pre>{constant | column_name | function | (subquery)}  
[{operator | AND | OR | NOT}  
{constant | column_name | function | (subquery)}...]</pre>  
  
La syntaxe SQL est constituée des paramètres suivants :  
  
|Paramètre|Description|  
|-------------|---------------|  
|constant|Valeur littérale (données numériques ou caractères). N'oubliez pas d'insérer les chaînes de caractères entre guillemets simples (').|  
|column_name|Spécifie une colonne.|  
|function|Fonction intégrée.|  
|operator|Opérateur arithmétique, de comparaison, de chaîne ou au niveau du bit.|  
|AND|Utilisez AND dans les expressions booléennes pour relier deux expressions. Les résultats sont retournés lorsque les deux expressions sont vraies.<br /><br />Lorsque AND et OR sont tous deux utilisés dans une instruction, AND est traité en premier. Vous pouvez changer l'ordre d'exécution en utilisant des parenthèses.|  
|- ou -|Utilisez OR dans les expressions booléennes pour relier plusieurs expressions. Les résultats sont retournés lorsque l'une ou l'autre des expressions est vraie.<br /><br />Lorsque AND et OR sont tous deux utilisés dans une instruction, OR est évalué après AND. Vous pouvez changer l'ordre d'exécution en utilisant des parenthèses.|  
|NOT|Inverse une expression booléenne (qui peut inclure des mots clés, tels que LIKE, NULL, BETWEEN, IN et EXISTS).<br /><br />Lorsqu'une instruction contient plusieurs opérateurs logiques, NOT est traité en premier. Vous pouvez changer l'ordre d'exécution en utilisant des parenthèses.|  
  
## <a name="see-also"></a>Voir aussi  
[Contraintes uniques et contraintes de validation](http://msdn.microsoft.com/en-us/637098af-2567-48f8-90f4-b41df059833e)  
[Créer des contraintes uniques](http://msdn.microsoft.com/en-us/a86f9d6f-f242-43be-b65d-b3435b71b62a)  
  

