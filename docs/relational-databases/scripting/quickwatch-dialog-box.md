---
title: "Bo&#238;te de dialogue Espion express | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.quickwatch"
helpviewer_keywords: 
  - "Boîte de dialogue Espion express [Transact-SQL]"
ms.assetid: d6bbb373-1452-41f2-bdc5-86ae689c3dc0
caps.latest.revision: 15
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
---
# Bo&#238;te de dialogue Espion express
  Utilisez la boîte de dialogue **Espion express** pour consulter rapidement le type de données et la valeur d’une expression [!INCLUDE[tsql](../../includes/tsql-md.md)] (par exemple, une variable ou un paramètre) pendant que vous déboguez le code [!INCLUDE[tsql](../../includes/tsql-md.md)]. Pour surveiller plusieurs expressions, vous pouvez également ajouter l’expression à une fenêtre **Espion**.  
  
## Liste des tâches  
 **Pour accéder à la boîte de dialogue Espion express**  
  
-   Dans le menu **Déboguer**, cliquez sur **Espion express**.  
  
 **Pour afficher les informations relatives à une expression**  
  
1.  Dans la zone de liste **Expression**, tapez ou sélectionnez l’expression souhaitée. Les expressions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes sont prises en charge :  
  
    -   variables ;  
  
    -   Paramètres.  
  
    -   Fonctions système dont le nom commence par @@.  
  
    -   Expressions générées par l'application d'opérateurs à un ou plusieurs variables, paramètres ou fonctions système, comme @IntegerCounter + 1 ou FirstName + LastName.  
  
    -   Instructions Transact-SQL qui retournent une seule valeur, par exemple : SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.  
  
2.  Cliquez sur **Réévaluer**.  
  
 **Pour ajouter l'expression Espion express à la fenêtre Espion**  
  
-   Cliquez sur **Ajouter un espion**.  
  
 **Pour modifier la valeur de l'expression Espion express**  
  
-   Cliquez avec le bouton droit sur l’expression, puis sélectionnez **Modifier la valeur**.  
  
## Options  
 **Liste d'expressions**  
 Affiche l'expression sélectionnée. La liste déroulante contient un ensemble d'expressions que vous pouvez choisir d'afficher. Les expressions présentes dans la liste sont celles qui sont disponibles dans l’étendue du frame de pile sélectionné dans la fenêtre **Pile des appels**. Pour afficher une autre expression, entrez-la ou sélectionnez-la dans la liste. Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] prend en charge les expressions suivantes : variables, paramètres et fonctions système dont les noms commencent par @@.  
  
 **Grille Valeur**  
 Affiche les propriétés de l'expression actuellement surveillée.  
  
 **Nom**  
 Expression [!INCLUDE[tsql](../../includes/tsql-md.md)] actuellement surveillée.  
  
 **Valeur**  
 Affiche la valeur actuellement assignée à l'expression. Si l'expression n'a pas de valeur, un espace est affiché.  
  
 Si la longueur d'une expression dépasse la largeur de la colonne **Valeur** , une info-bulle affiche la valeur complète lorsque vous placez le pointeur sur la cellule **Valeur** de cette expression.  
  
 La présence d'une icône de loupe dans une cellule **Valeur** indique que le visualiseur du débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] est disponible. Dans la liste, vous pouvez spécifier **Visualiseur de texte**, **Visualiseur XML**ou **Visualiseur HTML**. Pour démarrer un visualiseur du débogueur, cliquez sur l'icône de loupe. Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] ouvre une boîte de dialogue qui affiche les données dans un format adapté au type de données.  
  
 **Type**  
 Affiche le type de données de l'expression.  
  
## Voir aussi  
 [Débogueur Transact-SQL](../../relational-databases/scripting/transact-sql-debugger.md)   
 [Informations du débogueur Transact-SQL](../../relational-databases/scripting/transact-sql-debugger-information.md)   
 [Espion (fenêtre)](../../relational-databases/scripting/watch-window.md)   
 [Variables locales (fenêtre)](../../relational-databases/scripting/locals-window.md)   
 [Fenêtre Pile des appels](../../relational-databases/scripting/call-stack-window.md)   
 [Expressions &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md)  
  
  