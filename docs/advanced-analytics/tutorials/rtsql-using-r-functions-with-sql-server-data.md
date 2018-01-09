---
title: "À l’aide des fonctions R avec des données SQL Server (R dans démarrage rapide de SQL) | Documents Microsoft"
ms.custom: 
ms.date: 07/26/2017
ms.reviewer: 
ms.suite: sql
ms.prod: machine-learning-services
ms.prod_service: machine-learning-services
ms.component: 
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: tutorial
dev_langs:
- R
- SQL
ms.assetid: e2fe5d90-eee9-4daf-9eae-21d17b3ef320
caps.latest.revision: "8"
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 689bc7409258de4f16dd6dd1b4717bb3af603fd6
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="using-r-functions-with-sql-server-data-r-in-sql-quickstart"></a>À l’aide des fonctions R avec des données SQL Server (R dans démarrage rapide de SQL)

Maintenant que vous maîtrisez les opérations de base de R, le moment est venu de passer aux choses sérieuses. S’il peut vous paraître compliqué d’implémenter bon nombre de fonctions statistiques avancées avec T-SQL, il suffit en fait d’une seule ligne de code R.  Avec R Services, il est facile d’incorporer des scripts utilitaires R dans une procédure stockée.

Dans ces exemples, vous allez incorporer des fonctions mathématiques et utilitaires R dans une procédure stockée SQL Server.

## <a name="create-a-stored-procedure-to-generate-random-numbers"></a>Créer une procédure stockée pour générer des nombres aléatoires

Par souci de simplicité, nous allons utiliser R `stats` package, qui est installé et chargé par défaut avec R Services. Le package contient des centaines de fonctions qui permettent d’effectuer des tâches statistiques courantes, notamment la fonction `rnorm`, qui génère un nombre spécifié de nombres aléatoires en utilisant la distribution normale, avec un écart type et une moyenne donnés.

Par exemple, ce code R retourne 100 nombres sur une moyenne de 50, compte tenu d’un écart type de 3.

```R
as.data.frame(rnorm(100, mean = 50, sd = 3));
```

Pour appeler cette ligne de code R à partir de T-SQL, exécutez sp_execute_external_script et ajoutez la fonction R dans le paramètre de script R, comme ceci :

```sql
EXEC sp_execute_external_script
      @language = N'R'
    , @script = N'
         OutputDataSet <- as.data.frame(rnorm(100, mean = 50, sd =3));'
    , @input_data_1 = N'   ;'
      WITH RESULT SETS (([Density] float NOT NULL));
```

Vous souhaitez générer plus facilement un autre ensemble de nombres aléatoires ?

C’est simple lorsqu’elles sont combinées avec SQL Server : définissez une procédure stockée qui obtient les arguments de l’utilisateur. Vous devez ensuite passer ces arguments dans le script R sous forme de variables.

```sql
CREATE PROCEDURE MyRNorm (@param1 int, @param2 int, @param3 int)
AS
    EXEC sp_execute_external_script
      @language = N'R'
    , @script = N'
         OutputDataSet <- as.data.frame(rnorm(mynumbers, mymean, mysd));'
    , @input_data_1 = N'   ;'
    , @params = N' @mynumbers int, @mymean int, @mysd int'
    , @mynumbers = @param1
    , @mymean = @param2
    , @mysd = @param3
    WITH RESULT SETS (([Density] float NOT NULL));
```

+ La première ligne définit chaque paramètre d’entrée SQL nécessaire pendant l’exécution de la procédure stockée.

+ La ligne commençant par `@params` définit toutes les variables utilisées par le code R, ainsi que les types de données SQL correspondants.

+ Les lignes qui viennent de suite après mappent les noms de paramètres SQL aux noms de variables R correspondants.

Maintenant que vous avez inclus la fonction R dans une procédure stockée, vous pouvez l’appeler facilement et passer des valeurs différentes, comme ceci :

```sql
EXEC MyRNorm @param1 = 100,@param2 = 50, @param3 = 3
```

## <a name="related-resources"></a>Ressources connexes

+ Vous souhaitez installer plusieurs packages R, pour obtenir des informations plus avancée des fonctions statistiques ? Consultez [installation et gestion des packages R](../r/installing-and-managing-r-packages.md).

+ Pour vous aider à convertir votre code R autonome dans un format qui peut être facilement paramétrable à l’aide de procédures stockées SQL Server, l’équipe Microsoft R a fourni un nouveau package de R, **sqlrutils**. Pour plus d’informations, consultez [la création d’une procédure stockée à l’aide de sqlrutils](../r/how-to-create-a-stored-procedure-using-sqlrutils.md).

## <a name="use-r-utility-functions-for-troubleshooting"></a>Utiliser les fonctions utilitaires R pour résoudre les problèmes

Par défaut, une installation de R comprend le `utils` package, qui fournit diverses fonctions utilitaires pour examiner l’environnement R actuel. Cela peut être utile si vous constatez des différences de fonctionnement du code R dans SQL Server et les environnements extérieurs.

Par exemple, vous pouvez utiliser la fonction `memory.limit()` R pour affecter de la mémoire à l’environnement R actif. Comme le package `utils` est installé par défaut mais pas chargé, vous devez utiliser la fonction `library()` pour le charger en premier lieu.

```sql
EXECUTE sp_execute_external_script
      @language = N'R'
    , @script = N'
        library(utils);
        mymemory <- memory.limit();
        OutputDataSet <- as.data.frame(mymemory);'
    , @input_data_1 = N' ;'
WITH RESULT SETS (([Col1] int not null));
```

De nombreux utilisateurs souhaitent utiliser les fonctions de synchronisation du système dans R, tels que `system.time` et `proc.time`, pour capturer le temps utilisé par les processus R et analyser les problèmes de performances.

Pour obtenir un exemple, consultez ce didacticiel : [Créer des caractéristiques de données](../tutorials/walkthrough-create-data-features.md). Dans cette procédure pas à pas, les fonctions de minutage R sont incorporées dans la solution pour comparer les performances des deux méthodes de création de caractéristiques à partir des données : Fonctions R comparées aux fonctions T-SQL.

## <a name="next-lesson"></a>Leçon suivante

Ensuite, vous allez créer un modèle prédictif en utilisant R dans SQL Server.

[Créer un modèle prédictif](../tutorials/rtsql-create-a-predictive-model-r.md)
