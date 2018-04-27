---
title: WideWorldImportersDW - flux de travail ETL | Documents Microsoft
ms.prod: sql
ms.prod_service: sql
ms.service: ''
ms.component: samples
ms.technology:
- samples
ms.custom: ''
ms.date: 04/04/2018
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: article
author: BarbKess
ms.author: barbkess
manager: craigg
robots: noindex,nofollow
ms.workload: Inactive
ms.openlocfilehash: 65001407ac1991fe80c8b20e64aa795585a2e6c9
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="wideworldimportersdw-etl-workflow"></a>Flux de travail WideWorldImportersDW ETL
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
Le package ETL WWI_Integration est utilisé pour migrer des données à partir de la base de données WideWorldImporters à la base de données WideWorldImportersDW en tant que les modifications de données. Le package est exécuté périodiquement (généralement tous les jours).

## <a name="overview"></a>Vue d'ensemble

La conception des utilisations de package SQL Server Integration Services (SSIS) pour orchestrer les opérations en bloc T-SQL (et non en tant que transformations distinctes dans SSIS) pour garantir des performances élevées.

Les dimensions sont chargées en premier, suivies des tables de faits en. Le package peut être réexécutée à tout moment après une défaillance.

Le flux de travail est la suivante :

 ![Flux de travail WideWorldImporters ETL](media/wide-world-importers/wideworldimporters-etl-workflow.png)

Il commence par une tâche d’expression qui fonctionne à l’heure de coupure appropriée. Cette heure est l’heure actuelle moins quelques minutes. (Cela est plus fiable que la demande des données directement à l’heure actuelle). Puis, il tronque les millisecondes à partir de la.

Le traitement principal commence par le remplissage de la table de dimension de Date. Elle garantit que toutes les dates de l’année en cours ont été renseignées dans la table.

Après cela, une série de tâches de flux de données charge chaque dimension, puis chaque fait.

## <a name="prerequisites"></a>Configuration requise

- SQL Server 2016 (ou version ultérieure) avec les bases de données WideWorldImporters et WideWorldImportersDW. Il peut s’agir sur identiques ou différentes instances de SQL Server.
- SQL Server Management Studio (SSMS)
- SQL Server 2016 Integration Services (SSIS).
  - Assurez-vous que vous avez créé un catalogue SSIS. Dans le cas contraire, cliquez droit **Integration Services** dans l’Explorateur d’objets SSMS, puis choisissez **ajouter un catalogue**. Suivez les valeurs par défaut. Il vous demandera d’activer sqlclr et fournir un mot de passe.


## <a name="download"></a>Télécharger

La dernière version de l’exemple :

[wide-world-importers-release](http://go.microsoft.com/fwlink/?LinkID=800630)

Téléchargez le fichier de package SSIS **ETL.ispac quotidienne**.

Code source pour recréer la base de données est disponible à partir de l’emplacement suivant.

[importateurs de Wide world](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/wide-world-importers/wwi-integration-etl)

## <a name="install"></a>Installation

1. Déployer le package SSIS.
   - Ouvrez le package « ETL.ispac quotidienne » à partir de l’Explorateur Windows. Cette action lance l’Assistant Déploiement d’Integration Services.
   - Sous « Sélectionner la Source » suivre le déploiement de projet, par défaut avec le chemin d’accès pointant vers le package « ETL.ispac quotidienne ».
   - Sous « Sélectionner la Destination » Entrez le nom du serveur qui héberge le catalogue SSIS.
   - Sélectionnez un chemin d’accès sous le catalogue SSIS, par exemple sous un nouveau dossier « WideWorldImporters ».
   - Finalisation de l’Assistant en cliquant sur déployer.

2. Créer un travail de l’Agent SQL Server pour le processus ETL.
   - Dans SSMS, avec le bouton « SQL Server Agent » et sélectionnez Nouveau -> travaux.
   - Choisissez un nom, par exemple « WideWorldImporters ETL ».
   - Ajoutez une étape de travail de type « Package SQL Server Integration Services ».
   - Sélectionnez le serveur avec le catalogue SSIS et sélectionnez le package « ETL quotidien ».
   - Sous Configuration -> gestionnaires de connexions Vérifiez les connexions à la source et cible sont configurées correctement. La valeur par défaut consiste à connecter à l’instance locale.
   - Cliquez sur OK pour créer le travail.

3. Exécuter ou planifier la tâche.
