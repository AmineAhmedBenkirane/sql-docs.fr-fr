---
title: Importer des données d’Excel vers SQL | Microsoft Docs
ms.custom: ''
ms.date: 04/02/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: ''
ms.component: import-export
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Active
ms.openlocfilehash: b935bd332e5cbfa481f9400968a7c8188e2bc603
ms.sourcegitcommit: 059fc64ba858ea2adaad2db39f306a8bff9649c2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/04/2018
---
# <a name="import-data-from-excel-to-sql-server-or-azure-sql-database"></a>Importer des données d’Excel vers SQL Server ou Azure SQL Database
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
Il existe plusieurs moyens d’importer des données provenant de fichiers Excel vers SQL Server ou Azure SQL Database. Cet article récapitule chacune de ces options et fournit des liens vers des instructions plus détaillées.
-   Vous pouvez importer des données d’Excel vers SQL en une seule étape avec l’un des outils suivants :
    -   Assistant Importation et exportation SQL Server
    -   SQL Server Integration Services (SSIS)
    -   Fonction OPENROWSET
-   Vous pouvez importer des données en deux étapes en enregistrant vos données sous forme de texte, puis en utilisant l’un des outils suivants :
    -   Instruction BULK INSERT
    -   BCP
    -   Azure Data Factory

La description complète des outils et services complexes, par exemple SSIS et Azure Data Factory, n’entre pas dans le cadre de cette vue d’ensemble. Pour plus d’informations sur la solution qui vous intéresse, suivez les liens fournis.

> [!IMPORTANT]
> Pour obtenir des informations détaillées sur la connexion à des fichiers Excel, et sur les limitations et les problèmes connus liés au chargement de données depuis ou vers des fichiers Excel, consultez [Charger des données depuis ou vers Excel avec SQL Server Integration Services (SSIS)](../../integration-services/load-data-to-from-excel-with-ssis.md).

## <a name="sql-server-import-and-export-wizard"></a>Assistant Importation et Exportation SQL Server

Importez des données directement de fichiers Excel en effectuant les étapes des pages de l’Assistant Importation et Exportation SQL Server. Si vous le souhaitez, enregistrez les paramètres d’importation/exportation sous forme de package SQL Server Integration Services (SSIS), que vous pouvez personnaliser et réutiliser.

![Établir une connexion à une source de données Excel](media/excel-connection.png)

Vous trouverez un exemple d’utilisation de l’Assistant pour importer d’Excel vers SQL Server sur la page [Bien démarrer avec cet exemple simple de l’Assistant Importation et exportation](../../integration-services/import-export-data/get-started-with-this-simple-example-of-the-import-and-export-wizard.md).

## <a name="sql-server-integration-services-ssis"></a>SQL Server Integration Services (SSIS)

Si vous connaissez SSIS et que vous ne souhaitez pas exécuter l’Assistant Importation et Exportation SQL Server, créez un package SSIS qui utilise la source Excel et la destination SQL Server dans le flux de données.

![Composants du flux de données](media/excel-to-sql-data-flow.png)

Pour plus d’informations sur ces composants SSIS, consultez les rubriques suivantes :
-   [Source Excel](../../integration-services/data-flow/excel-source.md)
-   [Destination SQL Server](../../integration-services/data-flow/sql-server-destination.md)

Pour apprendre à créer des packages SSIS, consultez le didacticiel [Guide pratique pour créer un Package ETL](../../integration-services/ssis-how-to-create-an-etl-package.md).

## <a name="openrowset-and-linked-servers"></a>OPENROWSET et serveurs liés
> [!NOTE]
> Le fournisseur ACE (anciennement fournisseur Jet) qui se connecte à des sources de données Excel est destiné à une utilisation interactive côté client. Si vous utilisez le fournisseur ACE sur le serveur, en particulier dans des processus automatisés ou qui s’exécutent en parallèle, il se peut que vous constatiez des résultats inattendus.

### <a name="distributed-queries"></a>Requêtes distribuées

Importez des données directement de fichiers Excel à l’aide de la fonction Transact-SQL `OPENROWSET` ou `OPENDATASOURCE`. Cette utilisation est appelée *requête distribuée*.

Pour pouvoir exécuter une requête distribuée, vous devez activer l’option de configuration du serveur `ad hoc distributed queries`, comme l’indique l’exemple suivant. Pour plus d’informations, consultez la page [Option de configuration du serveur : requêtes distribuées ad hoc](../../database-engine/configure-windows/ad-hoc-distributed-queries-server-configuration-option.md).

```sql
sp_configure 'show advanced options', 1;
RECONFIGURE;
GO
sp_configure 'Ad Hoc Distributed Queries', 1;
RECONFIGURE;
GO
```

L’exemple de code suivant utilise `OPENROWSET` pour importer les données de la feuille de calcul Excel `Data` dans une nouvelle table de base de données.

```sql
USE ImportFromExcel;
GO
SELECT * INTO Data_dq
FROM OPENROWSET('Microsoft.ACE.OLEDB.12.0',
    'Excel 12.0; Database=D:\Desktop\Data.xlsx', [Data$]);
GO
```

Voici le même exemple avec `OPENDATASOURCE`.

```sql
USE ImportFromExcel;
GO
SELECT * INTO Data_dq
FROM OPENDATASOURCE('Microsoft.ACE.OLEDB.12.0',
    'Data Source=D:\Desktop\Data.xlsx;Extended Properties=Excel 12.0')...[Data$];
GO
```

Pour *ajouter* les données importées à une table *existante* au lieu d’en créer une nouvelle, utilisez la syntaxe `INSERT INTO ... SELECT ... FROM ...` à la place de la syntaxe `SELECT ... INTO ... FROM ...` utilisée dans les exemples précédents.

Pour interroger les données Excel sans les importer, utilisez simplement la syntaxe `SELECT ... FROM ...` standard.

Pour plus d’informations sur les requêtes distribuées, consultez les rubriques suivantes :
-   [Requêtes distribuées](https://msdn.microsoft.com/library/ms188721(v=sql.105).aspx) (Les requêtes distribuées sont toujours prises en charge dans SQL Server 2016, mais la documentation relative à cette fonctionnalité n’a pas été mise à jour.)
-   [OPENROWSET](../../t-sql/functions/openrowset-transact-sql.md)
-   [OPENDATASOURCE](../../t-sql/functions/openquery-transact-sql.md)

### <a name="linked-servers"></a>Serveurs liés

Vous pouvez également configurer une connexion permanente au fichier Excel sous forme de *serveur lié*. L’exemple suivant importe les données de la feuille de calcul `Data` sur le serveur lié Excel existant `EXCELLINK` dans une nouvelle table de base de données nommée `Data_ls`.

```sql
USE ImportFromExcel;
GO
SELECT * INTO Data_ls FROM EXCELLINK...[Data$];
GO
```

Vous pouvez créer un serveur lié à partir de SQL Server Management Studio, ou en exécutant la procédure stockée de système `sp_addlinkedserver`, comme l’illustre l’exemple suivant.

```sql
DECLARE @RC int

DECLARE @server     nvarchar(128)
DECLARE @srvproduct nvarchar(128)
DECLARE @provider   nvarchar(128)
DECLARE @datasrc    nvarchar(4000)
DECLARE @location   nvarchar(4000)
DECLARE @provstr    nvarchar(4000)
DECLARE @catalog    nvarchar(128)

-- Set parameter values
SET @server =     'EXCELLINK'
SET @srvproduct = 'Excel'
SET @provider =   'Microsoft.ACE.OLEDB.12.0'
SET @datasrc =    'D:\Desktop\Data.xlsx'
SET @provstr =    'Excel 12.0'

EXEC @RC = [master].[dbo].[sp_addlinkedserver] @server, @srvproduct, @provider,
@datasrc, @location, @provstr, @catalog
```

Pour plus d’informations sur les serveurs liés, consultez les rubriques suivantes :
-   [Créer des serveurs liés](../../relational-databases/linked-servers/create-linked-servers-sql-server-database-engine.md)
-   [OPENQUERY](../../t-sql/functions/openquery-transact-sql.md)

Pour plus d’exemples et d’informations sur les serveurs liés et les requêtes distribuées, consultez les rubriques suivantes :
-   [Guide pratique pour utiliser Excel avec des serveurs liés et des requêtes distribuées SQL Server](https://support.microsoft.com/help/306397/how-to-use-excel-with-sql-server-linked-servers-and-distributed-queries)
-   [Comment importer des données d'Excel vers SQL Server](https://support.microsoft.com/help/321686/how-to-import-data-from-excel-to-sql-server)

## <a name="prerequisite---save-excel-data-as-text"></a>Prérequis - Enregistrer des données Excel sous forme de texte
Pour utiliser les autres méthodes décrites sur cette page (l’instruction BULK INSERT, l’outil BCP ou Azure Data Factory), vous devez d’abord exporter vos données Excel dans un fichier texte.

Dans Excel, sélectionnez **Fichier | Enregistrer sous**, puis **Texte (délimité par des tabulations) (\*.txt)** ou **CSV (séparé par des virgules) (\*.csv)** comme type de fichier de destination.

> [!TIP]
> Pour obtenir de meilleurs résultats avec les outils d’importation de données, enregistrez les feuilles qui contiennent uniquement les en-têtes de colonnes et les lignes de données. Si les données enregistrées contiennent des titres des pages, des lignes vides, des notes et ainsi de suite, il se peut que vous constatiez des résultats inattendus par la suite, lorsque vous importerez des données.

## <a name="bulk-insert-command"></a>Commande BULK INSERT

`BULK INSERT` est une commande Transact-SQL exécutable à partir de SQL Server Management Studio. L’exemple suivant charge les données du fichier délimité par des virgules `Data.csv` dans une table de base de données existante.

```sql
USE ImportFromExcel;
GO
BULK INSERT Data_bi FROM 'D:\Desktop\data.csv'
   WITH (
      FIELDTERMINATOR = ',',
      ROWTERMINATOR = '\n'
);
GO
```

Pour plus d’informations, consultez les rubriques suivantes :
-   [Importer des données en bloc à l’aide de BULK INSERT ou OPENROWSET(BULK...)](../../relational-databases/import-export/import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md)
-   [BULK INSERT](../../t-sql/statements/bulk-insert-transact-sql.md)

## <a name="bcp-tool"></a>Outil BCP

BCP est un programme que vous exécutez à partir de l’invite de commandes. L’exemple suivant charge les données du fichier délimité par des virgules `Data.csv` dans la table de base de données existante `Data_bcp`.

```sql
bcp.exe ImportFromExcel..Data_bcp in "D:\Desktop\data.csv" -T -c -t ,
```

Pour plus d’informations sur BCP, consultez les rubriques suivantes :
-   [Importer et exporter des données en bloc à l’aide de l’utilitaire BCP](../../relational-databases/import-export/import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md)
-   [Utilitaire bcp](../../tools/bcp-utility.md)
-   [Préparer des données en vue d’une exportation ou d’une importation en bloc](../../relational-databases/import-export/prepare-data-for-bulk-export-or-import-sql-server.md)

## <a name="copy-wizard-azure-data-factory"></a>Assistant Copie (Azure Data Factory)
Importez des données enregistrées dans des fichiers texte en parcourant les pages de l’Assistant Copie.

Pour plus d’informations sur l’Assistant Copie, consultez les rubriques suivantes :
-   [Assistant Copie de Data Factory](https://docs.microsoft.com/azure/data-factory/data-factory-azure-copy-wizard)
-   [Didacticiel : Créer un pipeline avec activité de copie à l’aide de l’Assistant Copie de Data Factory](https://docs.microsoft.com/azure/data-factory/data-factory-copy-data-wizard-tutorial)

## <a name="azure-data-factory"></a>Azure Data Factory
Si vous connaissez Azure Data Factory et que vous ne voulez pas exécuter l’Assistant Copie, créez un pipeline avec une activité de copie qui permet d’effectuer une copie à partir du fichier texte dans SQL Server ou Azure SQL Database.

Pour plus d’informations sur l’utilisation de ces sources et récepteurs Data Factory, consultez les rubriques suivantes :
-   [Système de fichiers](https://docs.microsoft.com/azure/data-factory/data-factory-onprem-file-system-connector)
-   [SQL Server](https://docs.microsoft.com/azure/data-factory/data-factory-sqlserver-connector)
-   [Azure SQL Database](https://docs.microsoft.com/azure/data-factory/data-factory-azure-sql-connector)

Pour apprendre à copier des données avec Azure Data Factory, consultez les rubriques suivantes :
-   [Déplacer des données grâce à l’activité de copie](https://docs.microsoft.com/azure/data-factory/data-factory-data-movement-activities)
-   [Didacticiel : Créer un pipeline avec activité de copie à l’aide du Portail Azure](https://docs.microsoft.com/azure/data-factory/data-factory-copy-data-from-azure-blob-storage-to-sql-database)

## <a name="see-also"></a> Voir aussi
[Charger des données depuis ou vers Excel avec SQL Server Integration Services (SSIS)](../../integration-services/load-data-to-from-excel-with-ssis.md)
