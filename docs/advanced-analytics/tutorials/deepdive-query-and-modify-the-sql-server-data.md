---
title: "Interroger et modifier les données du serveur SQL | Documents Microsoft"
ms.custom: 
ms.date: 05/18/2017
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
ms.assetid: 8c7007a9-9a8f-4dcd-8068-40060d4f6444
caps.latest.revision: 17
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 4970a681733d8920b9eef6b27023f9ae1c7ce981
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="query-and-modify-the-sql-server-data"></a>Interroger et modifier les données du serveur SQL

Maintenant que vous avez chargé les données dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous pouvez utiliser les sources de données que vous avez créées comme arguments de fonctions R dans [!INCLUDE[rsql_productname](../../includes/rsql-productname-md.md)], pour obtenir des informations de base sur les variables, et générer des résumés et des histogrammes.

Dans cette étape, vous allez réutiliser les sources de données pour effectuer des analyses rapides et d’améliorer les données.

## <a name="query-the-data"></a>Interroger les données

Obtenez d’abord la liste des colonnes et leurs types de données.

1.  Utilisez la fonction **rxGetVarInfo** et spécifiez la source de données que vous souhaitez analyser.
  
    ```R
    rxGetVarInfo(data = sqlFraudDS)
    ```

    **Résultats**
    
    *Var 1 : custID, Type : entier*
    
    *Var 2 : gender, Type : entier*
    
    *Var 3 : state, Type : entier*
    
    *Var 4 : cardholder, Type : entier*
    
    *Var 5 : balance, Type : entier*
    
    *Var 6 : numTrans, Type : entier*
    
    *Var 7 : numIntlTrans, Type : entier*
    
    *Var 8 : creditLine, Type : entier*
    
    *Var 9 : fraudRisk, Type : entier*


## <a name="modify-metadata"></a>Modifier les métadonnées

Toutes les variables sont stockées sous forme d’entiers, mais certaines variables représentent des données de catégorie appelées *variables de facteur* dans R. Par exemple, la colonne *state* contient des nombres qui représentent des identificateurs pour les 50 états, plus le District de Columbia.  Pour mieux comprendre les données, vous pouvez remplacer les numéros par une liste d’abréviations des noms des états.

Dans cette étape, vous allez fournir un vecteur de chaîne qui contient les abréviations, puis mapper ces valeurs de catégorie aux identificateurs entiers d’origine. Quand la variable est prête, vous allez l’utiliser dans l’argument *colInfo* pour spécifier que cette colonne doit être gérée comme un facteur. Par la suite, les abréviations seront utilisées et la colonne gérée comme un facteur dès que ces données seront analysées ou importées.

1. Commencez par créer la variable R *stateAbb*et par définir le vecteur des chaînes que vous lui ajoutez, comme suit :
  
    ```R
    stateAbb <- c("AK", "AL", "AR", "AZ", "CA", "CO", "CT", "DC",
        "DE", "FL", "GA", "HI","IA", "ID", "IL", "IN", "KS", "KY", "LA",
        "MA", "MD", "ME", "MI", "MN", "MO", "MS", "MT", "NB", "NC", "ND",
        "NH", "NJ", "NM", "NV", "NY", "OH", "OK", "OR", "PA", "RI","SC",
        "SD", "TN", "TX", "UT", "VA", "VT", "WA", "WI", "WV", "WY")
    ```

2. Ensuite, créez un objet d’informations de colonne, nommé *ccColInfo*, qui spécifie le mappage des valeurs entières existantes aux niveaux des catégories (les abréviations du nom des états).
  
    Cette instruction crée également des variables de facteur pour gender et cardholder.
  
    ```R
    ccColInfo <- list(
    gender = list(
              type = "factor",
              levels = c("1", "2"),
              newLevels = c("Male", "Female")
              ),
    cardholder = list(
                  type = "factor",
                  levels = c("1", "2"),
                  newLevels = c("Principal", "Secondary")
                   ),
    state = list(
             type = "factor",
             levels = as.character(1:51),
             newLevels = stateAbb
             ),
    balance = list(type = "numeric")
    )
    ```
  
3. Pour créer la source de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui utilise les données mises à jour, appelez la fonction *RxSqlServerData* comme précédemment, mais ajoutez l’argument *colInfo* .
  
    ```R
    sqlFraudDS <- RxSqlServerData(connectionString = sqlConnString,
    table = sqlFraudTable, colInfo = ccColInfo,
    rowsPerRead = sqlRowsPerRead)
    ```
  
    - Pour le paramètre *table* , passez la variable *sqlFraudTable*qui contient la source de données que vous avez créée.
    - Pour le paramètre *colInfo* , passez la variable *ccColInfo* , qui contient les types de données de colonne et les niveaux de facteur.
    - Le fait de mapper la colonne vers les abréviations avant de l’utiliser comme facteur améliore également les performances. Pour plus d’informations, consultez [R et optimisation des données](https://msdn.microsoft.com/library/mt723575.aspx).
  
4.  Vous pouvez désormais utiliser la fonction rxGetVarInfo pour afficher les variables dans la nouvelle source de données.
  
    ```R
    rxGetVarInfo(data = sqlFraudDS)
    ```

    **Résultats**
    
    *Var 1 : custID, Type : entier*
    
    *Var 2 : sexe 2 niveaux facteur : Male féminin*
    
    *Var 3 : 51 niveaux des facteurs d’état : autorité de certification AZ AK AL AR... VT WA WI WV WY*
    
    *Var 4 : niveaux de facteur titulaires de cartes 2 : Principal de base de données secondaire*
    
    *Var 5 : balance, Type : entier*
    
    *Var 6 : numTrans, Type : entier*
    
    *Var 7 : numIntlTrans, Type : entier*
    
    *Var 8 : creditLine, Type : entier*
    
    *Var 9 : fraudRisk, Type : entier*

Les trois variables que vous avez spécifiées (_gender_, _state_et _cardholder_) sont maintenant traitées comme des facteurs.

## <a name="next-step"></a>Étape suivante

[Définir et utiliser les contextes de calcul](../../advanced-analytics/tutorials/deepdive-define-and-use-compute-contexts.md)

## <a name="previous-step"></a>Étape précédente

[Créer des objets de données SQL Server à l’aide de RxSqlServerData](../../advanced-analytics/tutorials/deepdive-create-sql-server-data-objects-using-rxsqlserverdata.md)




