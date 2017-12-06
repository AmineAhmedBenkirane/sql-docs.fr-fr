---
title: "Utilisation de fonctionnalités de SQL Server | Documents Microsoft"
ms.prod: sql-non-specified
ms.prod_service: sql-non-specified
ms.service: 
ms.component: samples
ms.technology: samples
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7cbfb4ef-1e61-4e65-9fe0-ed5adfb43415
caps.latest.revision: "3"
author: BarbKess
ms.author: barbkess
manager: jhubbard
robots: noindex,nofollow
ms.workload: Inactive
ms.openlocfilehash: 9179b95331ddcad4a704feadae2aa3f9211f8dff
ms.sourcegitcommit: b2d8a2d95ffbb6f2f98692d7760cc5523151f99d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2017
---
# <a name="wideworldimportersdw-use-of-sql-server-features-and-capabilities"></a>Utilisation de WideWorldImportersDW de fonctionnalités de SQL Server
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]WideWorldImportersDW est conçu pour illustrer la plupart des fonctionnalités clés de SQL Server qui conviennent pour l’entreposage des données et analytique. Voici une liste des fonctionnalités de SQL Server et fonctionnalités et une description de la façon dont elles sont utilisées dans WideWorldImportersDW.

## <a name="polybase"></a>PolyBase

[S’applique à SQL Server (2016 et versions ultérieures)]

PolyBase est utilisé pour combiner les informations de vente issues WideWorldImportersDW avec un jeu de données publique sur les données démographiques pour comprendre les villes peuvent présenter un intérêt pour une extension supplémentaire des ventes.

Pour activer l’utilisation de PolyBase dans la base de données, vérifiez qu’il est installé et exécutez la procédure stockée suivante dans la base de données :

    EXEC [Application].[Configuration_ApplyPolybase]

Cela crée une table externe `dbo.CityPopulationStatistics` qui fait référence à un jeu de données publique qui contient les données de la population des villes aux États-Unis, hébergé dans le stockage blob Azure. Il est conseillé de vérifier le code dans la procédure stockée pour comprendre le processus de configuration. Si vous souhaitez héberger vos propres données dans le stockage blob Azure et qu’il soit sécurisé à partir d’un accès public général, vous devez effectuer les étapes de configuration supplémentaires. La requête suivante renvoie les données à partir de ce jeu de données externes :

    SELECT CityID, StateProvinceCode, CityName, YearNumber, LatestRecordedPopulation FROM dbo.CityPopulationStatistics;

Pour comprendre les villes peuvent présenter un intérêt pour expansion supplémentaire, la requête suivante examine le taux de croissance de villes et retourne les plus grandes villes de 100 premiers avec une croissance importante, et où Wide World Importers ne dispose pas d’une présence commerciale. La requête implique une jointure entre la table distante `dbo.CityPopulationStatistics` et la table locale `Dimension.City`et un filtre de la table locale `Fact.Sales`.

    WITH PotentialCities
    AS
    (
        SELECT cps.CityName,
               cps.StateProvinceCode,
               MAX(cps.LatestRecordedPopulation) AS PopulationIn2016,
               (MAX(cps.LatestRecordedPopulation) - MIN(cps.LatestRecordedPopulation)) * 100.0
                   / MIN(cps.LatestRecordedPopulation) AS GrowthRate
        FROM dbo.CityPopulationStatistics AS cps
        WHERE cps.LatestRecordedPopulation IS NOT NULL
        AND cps.LatestRecordedPopulation <> 0
        GROUP BY cps.CityName, cps.StateProvinceCode
    ),
    InterestingCities
    AS
    (
        SELECT DISTINCT pc.CityName,
                        pc.StateProvinceCode,
                        pc.PopulationIn2016,
                        FLOOR(pc.GrowthRate) AS GrowthRate
        FROM PotentialCities AS pc
        INNER JOIN Dimension.City AS c
        ON pc.CityName = c.City
        WHERE GrowthRate > 2.0
        AND NOT EXISTS (SELECT 1 FROM Fact.Sale AS s WHERE s.[City Key] = c.[City Key])
    )
    SELECT TOP(100) CityName, StateProvinceCode, PopulationIn2016, GrowthRate
    FROM InterestingCities
    ORDER BY PopulationIn2016 DESC;

## <a name="clustered-columnstore-indexes"></a>Index columnstore cluster

(Version complète de l’exemple)

Index de Columnstore en cluster (CCI) sont utilisés avec toutes les tables de faits, pour réduire l’encombrement de stockage et améliorer les performances des requêtes. Avec l’utilisation de CCI, le stockage de base pour les tables de faits utilise la compression de la colonne.

Index non cluster sont utilisés sur l’index columnstore en cluster, pour faciliter la clé primaire et les contraintes de clé étrangère. Ces contraintes ont été ajoutées en dehors d’une multitude d’attention : le processus ETL d'où proviennent les données à partir de la base de données WideWorldImporters, qui a des contraintes pour appliquer l’intégrité. Suppression de contraintes de clé primaire et étrangère et leurs index prise en charge, réduirait l’encombrement de stockage de tables de faits.

**Taille des données**

La base de données a limité la taille des données, pour faciliter la tâche télécharger et installer l’exemple. Toutefois, pour découvrir les avantages de performances réelles des index columnstore, vous pouvez utiliser un grand jeu de données.

Vous pouvez exécuter l’instruction suivante pour augmenter la taille de la `Fact.Sales` table par une autre millions de 12 de lignes d’exemples de données. Ces lignes sont toutes insérées pour l’année 2012, qu’il n’y ait aucune interférence avec le processus ETL.

    EXECUTE [Application].[Configuration_PopulateLargeSaleTable]

Cette instruction prendra environ 5 minutes pour s’exécuter. Pour insérer plus de 12 millions de lignes, passez le nombre souhaité de lignes à insérer en tant que paramètre à cette procédure stockée.

Pour comparer les performances des requêtes avec et sans columnstore, vous pouvez supprimer ou recréez l’index columnstore en cluster.

Pour supprimer l’index :

    DROP INDEX [CCX_Fact_Order] ON [Fact].[Order]

Pour recréer :

    CREATE CLUSTERED COLUMNSTORE INDEX [CCX_Fact_Order] ON [Fact].[Order]

## <a name="partitioning"></a>Partitionnement

(Version complète de l’exemple)

Taille des données dans un entrepôt de données peut devenir très volumineux. Par conséquent, il est recommandé d’utiliser le partitionnement pour gérer le stockage des tables dans la base de données volumineux.

Toutes les tables de faits supérieure sont partitionnées par année. La seule exception est `Fact.Stock Holdings`, ce qui n’est pas basée sur la date et a taille limitée de données comparée avec les autres tables de faits.

La fonction de partition utilisé pour les tables partitionnées toutes les `PF_Date`, et le schéma de partition utilisé est `PS_Date`.

## <a name="in-memory-oltp"></a>OLTP en mémoire

(Version complète de l’exemple)

WideWorldImportersDW utilise les tables optimisées en mémoire SCHEMA_ONLY pour les tables intermédiaires. Tous les `Integration.` * `_Staging` tables sont des tables optimisées en mémoire SCHEMA_ONLY.

L’avantage de tables SCHEMA_ONLY est qu’ils ne sont pas enregistrés et ne nécessitent pas l’accès de disque. Cela améliore les performances du processus ETL. Étant donné que ces tables ne sont pas enregistrés, leur contenu est perdu en cas de panne. Toutefois, la source de données est toujours disponible, donc le processus ETL peut simplement être redémarré si une défaillance se produit.
