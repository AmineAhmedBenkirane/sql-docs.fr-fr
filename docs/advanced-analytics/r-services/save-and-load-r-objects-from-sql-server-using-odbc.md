---
title: "Enregistrer et charger des objets R &#224; partir de SQL Server &#224; l’aide d’ODBC | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "r-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "R"
ms.assetid: 6ac2e971-6b4f-4c73-ba57-29c716abd057
caps.latest.revision: 8
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
caps.handback.revision: 8
---
# Enregistrer et charger des objets R &#224; partir de SQL Server &#224; l’aide d’ODBC
SQL Server R Services peut stocker des objets R sérialisés dans une table, puis charger l’objet à partir de la table en fonction des besoins, sans que vous ayez à réexécuter le code R ou à reformer le modèle. Cette capacité à enregistrer les objets R dans une base de données est essentielle pour les scénarios tels que la formation et l’enregistrement d’un modèle, puis son utilisation ultérieure à des fins de notation ou d’analyse. 

Pour améliorer les performances de cette étape critique, le package **RevoScaleR** inclut désormais de nouvelles fonctions de sérialisation et de désérialisation qui améliorent sensiblement les performances et stockent l’objet de manière plus compacte. De plus, vous pouvez enregistrer les objets R dans SQL Server directement à partir d’un environnement R, en appelant ces nouvelles fonctions par le biais d’une connexion ODBC à l’aide de *RxOdbcData*.

## <a name="overview"></a>Vue d'ensemble

Le package **RevoScaleR** inclut désormais de nouvelles fonctions qui facilitent l’enregistrement des objets R dans SQL Server, puis la lecture des objets à partir de la table SQL Server. Ces fonctions nécessitent l’établissement d’une connexion à SQL Server à l’aide de la source de données *RxOdbcData*.

En général, les appels de fonction sont modélisés d’après un magasin de valeurs de clés simple, dans lequel la clé est le nom de l’objet et la valeur associée à la clé est l’objet varbinary R à déplacer dans ou hors d’une table. 

- Par défaut, tout objet que vous appelez à partir de R pour passer à SQL Server est sérialisé et compressé. 
- Inversement, quand vous chargez un objet à partir d’une table SQL Server pour l’utiliser dans votre code R, l’objet est désérialisé et décompressé.
- Si vous le souhaitez, vous pouvez faire en sorte que l’objet ne soit pas sérialisé, et vous pouvez choisir un nouvel algorithme de compression à utiliser à la place de l’algorithme de compression par défaut.


## <a name="new-functions"></a>Nouvelles fonctions

- `rxWriteObject` écrit un objet R dans SQL Server à l’aide de la source de données ODBC. 

- `rxReadObject` lit un objet R à partir d’une base de données SQL Server, à l’aide d’une source de données ODBC.

- `rxDeleteObject` supprime un objet R de la base de données SQL Server spécifiée dans la source de données ODBC. Si plusieurs objets sont identifiés par la combinaison clé/version, ils sont tous supprimés.

- `rxListKeys` énumère comme paires clé-valeur tous les objets disponibles. Cela vous permet de déterminer les noms et les versions des objets R.

Pour obtenir des informations détaillées sur la syntaxe de chaque fonction, utilisez l’aide de R. Des détails seront disponibles dans la [Référence de ScaleR](https://msdn.microsoft.com/microsoft-r/scaler/scaler) sur MSDN à une date ultérieure.

## <a name="how-to-store-r-objects-in-sql-server-using-odbc"></a>Guide pratique pour stocker des objets R dans SQL Server à l’aide d’ODBC

Cette procédure illustre comment utiliser les nouvelles fonctions pour créer un modèle et l’enregistrer dans SQL Server.

1. Configurez la chaîne de connexion pour SQL Server.
   ```R
   conStr <- 'Driver={SQL Server};Server=localhost;Database=storedb;Trusted_Connection=true'
   ```
2. Créez un objet de source de données *rxOdbcData* dans R à l’aide de la chaîne de connexion.
   ```R
   ds <- RxOdbcData(table="robjects", connectionString=conStr)
   ```

3. Supprimez la table si elle existe déjà et que vous ne souhaitez pas effectuer le suivi des anciennes versions des objets.

   ```R
   if(rxSqlServerTableExists(ds@table, ds@connectionString)) {
       rxSqlServerDropTable(ds@table, ds@connectionString)
       }
   ```
   
4. Définissez une table qui peut être utilisée pour stocker des objets binaires.

   ```R
   ddl <- paste(" CREATE TABLE [", ds@table, "] 
      (","  [id] varchar(200) NOT NULL,
       "," [value] varbinary(max),
       "," CONSTRAINT unique_id UNIQUE (id))", 
       sep = "") 
   ```
5. Ouvrez la connexion ODBC pour créer la table puis, quand l’instruction DDL est terminée, fermez la connexion.

   ```R
    rxOpen(ds, "w") 
    rxExecuteSQLDDL(ds, ddl) 
    rxClose(ds)
    ```
6. Générez les objets R que vous souhaitez stocker.

   ```R
   infertLogit <- rxLogit(case ~ age + parity + education + spontaneous + induced, 
     data = infert)
   ```
6. Utilisez l’objet *RxOdbcData* créé précédemment pour enregistrer le modèle dans la base de données.

   ```R
   rxWriteObject(ds, "logit.model", infertLogit)
   ```

## <a name="how-to-read-r-objects-from-sql-server-using-odbc"></a>Guide pratique pour lire des objets R à partir de SQL Server à l’aide d’ODBC

Cette procédure illustre comment utiliser les nouvelles fonctions pour charger un modèle à partir de SQL Server.

1. Configurez la chaîne de connexion pour SQL Server.

   ```R
   conStr2 <- 'Driver={SQL Server};Server=localhost;Database=storedb;Trusted_Connection=true'
   ```
2. Créez un objet de source de données *rxOdbcData* dans R à l’aide de la chaîne de connexion.

   ```R
   ds <- RxOdbcData(table="robjects", connectionString=conStr2)
   ```
3. Lisez le modèle à partir de la table en spécifiant son nom d’objet R.

   ```R
    infertLogit2 <- rxReadObject(ds, "logit.model")
   ```

## <a name="see-also"></a>Voir aussi

[Fonctionnalités et tâches R Services](../../advanced-analytics/r-services/sql-server-r-services-features-and-tasks.md)
