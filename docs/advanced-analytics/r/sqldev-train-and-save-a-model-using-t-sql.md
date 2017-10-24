---
title: "Leçon 5 : L’apprentissage et enregistrez un modèle à l’aide de T-SQL | Documents Microsoft"
ms.custom: 
ms.date: 07/26/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- r-services
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- SQL Server 2016
dev_langs:
- R
- TSQL
ms.assetid: 3282e8ed-b515-4ed5-8543-fcef68629a92
caps.latest.revision: 10
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 785e4dc3db234447c806ddc349682d08a8447923
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="lesson-5-train-and-save-a-model-using-t-sql"></a>Leçon 5 : L’apprentissage et enregistrez un modèle à l’aide de T-SQL

Cet article fait partie d’un didacticiel pour les développeurs SQL sur la façon d’utiliser R dans SQL Server.

Dans cette leçon, vous allez apprendre à former un modèle d’apprentissage automatique à l’aide de R. Vous devez former le modèle avec les fonctionnalités de données que vous venez de créer, puis enregistrez le modèle formé dans un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table. Dans ce cas, les packages R sont déjà installés avec [!INCLUDE[rsql_productname](../../includes/rsql-productname-md.md)], de sorte que tous les éléments peuvent être effectuée à partir de SQL.

## <a name="create-the-stored-procedure"></a>Créez la procédure stockée

Lors de l’appel de R à partir de T-SQL, vous utilisez la procédure stockée système, [sp_execute_external_script](../../relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql.md). Toutefois, pour les processus que vous répétez souvent, telles que le recyclage d’un modèle, il est plus facile d’encapsuler l’appel à `sp_execute_exernal_script` dans une autre procédure stockée.

1.  Commencez par créer une procédure stockée qui contient le code R pour générer le modèle de prévision d’info-bulle. Dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], ouvrez une nouvelle **requête** fenêtre et exécutez l’instruction suivante pour créer la procédure stockée _TrainTipPredictionModel_. Cette procédure stockée définit les données d’entrée et utilise un package R pour créer un modèle de régression logistique.

    ```SQL
    CREATE PROCEDURE [dbo].[TrainTipPredictionModel]
    
    AS
    BEGIN
      DECLARE @inquery nvarchar(max) = N'
        select tipped, fare_amount, passenger_count,trip_time_in_secs,trip_distance,
        pickup_datetime, dropoff_datetime,
        dbo.fnCalculateDistance(pickup_latitude, pickup_longitude,  dropoff_latitude, dropoff_longitude) as direct_distance
        from nyctaxi_sample
        tablesample (70 percent) repeatable (98052)
    '
      -- Insert the trained model into a database table
      INSERT INTO nyc_taxi_models
      EXEC sp_execute_external_script @language = N'R',
                                      @script = N'
    
    ## Create model
    logitObj <- rxLogit(tipped ~ passenger_count + trip_distance + trip_time_in_secs + direct_distance, data = InputDataSet)
    summary(logitObj)
    
    ## Serialize model and put it in data frame
    trained_model <- data.frame(model=as.raw(serialize(logitObj, NULL)));
    ',
      @input_data_1 = @inquery,
      @output_data_1_name = N'trained_model'
      ;
    
    END
    GO
    ```

    - Toutefois, pour vous assurer que certaines données disponible pour tester le modèle, 70 % des données sont sélectionnées au hasard à partir de la table de données taxi.
    
    - La requête SELECT utilise la fonction scalaire personnalisée _fnCalculateDistance_ pour calculer la distance directe entre les points de prise en charge et de dépose.  Les résultats de la requête sont stockés dans la variable d’entrée R par défaut, `InputDataset`.
  
    - Les appels de script R la `rxLogit` (fonction), qui est une des fonctions R améliorées inclus avec [!INCLUDE[rsql_productname](../../includes/rsql-productname-md.md)], pour créer le modèle de régression logistique.
  
        La variable binaire _tipped_ est utilisée comme *étiquette* ou colonne de résultat, et le modèle est adapté à l’aide de ces colonnes de caractéristiques :  _passenger_count_, _trip_distance_, _trip_time_in_secs_et _direct_distance_.
  
    -   Le modèle formé, enregistré dans la variable R `logitObj`, est sérialisé et placé dans une trame de données destinée à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Cette sortie est insérée dans la table de base de données _nyc_taxi_models_, afin que vous puissiez l’utiliser pour des prédictions.
  
2.  Exécutez l’instruction pour créer la procédure stockée, s’il n’existe pas.

## <a name="generate-the-r-model-using-the-stored-procedure"></a>Générer le modèle R à l’aide de la procédure stockée

Étant donné que la procédure stockée contient déjà une définition des données d’entrée, vous n’avez pas besoin de fournir une requête d’entrée.

1. Pour générer le modèle R, appelez la procédure stockée sans aucun autre paramètre :

    ```SQL
    EXEC TrainTipPredictionModel
    ```

2. Espion le **Messages** fenêtre de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] pour les messages qui sont redirigés vers R **stdout** flux, comme cette consignation : 

    « Messages STDOUT du script externe : lignes lues : 1193025, Total lignes traitées : 1193025, temps Total de segment : 0.093 secondes »

    Vous pouvez également voir des messages spécifiques à la fonction en question, `rxLogit`, en affichant les variables et les métriques générés dans le cadre de la création du modèle de test.

3.  Une fois l’instruction terminée, ouvrez la table *nyc_taxi_models*. Le traitement des données et l’ajustement du modèle peuvent prendre un certain temps.

    Vous pouvez voir qu’une nouvelle ligne a été ajoutée, avec le modèle sérialisé dans la colonne _model_.

    ```
    model
    ------
    0x580A00000002000302020....
    ```

À l’étape suivante, vous allez utiliser le modèle formé pour créer des prédictions.

## <a name="next-lesson"></a>Leçon suivante

[Leçon 6 : Rendez le modèle opérationnel.](../tutorials/sqldev-operationalize-the-model.md)

## <a name="previous-lesson"></a>Leçon précédente

[Leçon 4 : Créer des fonctionnalités de données à l’aide de T-SQL](..//tutorials/sqldev-create-data-features-using-t-sql.md)


