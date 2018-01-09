---
title: "Configuration requise pour la procédure pas à pas pour la science des données pour SQL Server et R | Documents Microsoft"
ms.date: 11/10/2017
ms.reviewer: 
ms.suite: sql
ms.prod: machine-learning-services
ms.prod_service: machine-learning-services
ms.component: 
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: tutorial
applies_to: SQL Server 2016
dev_langs: R
ms.assetid: 0b0582b8-8843-4787-94a8-2e28bdc04fb2
caps.latest.revision: "13"
author: jeannt
ms.author: jeannt
manager: cgronlund
ms.workload: Inactive
ms.openlocfilehash: 7ef81e77e227cfa0fb69200996af60f9abae9b34
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="prerequisites-for-the-data-science-walkthrough-for-sql-server-and-r"></a>Configuration requise pour la procédure pas à pas pour la science des données pour SQL Server et R

Nous vous recommandons d’effectuer cette procédure pas à pas sur un ordinateur portable ou un autre ordinateur qui a les bibliothèques Microsoft R installés. Vous devez être en mesure de se connecter sur le même réseau, à un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ordinateur avec les services de machine learning et le langage R activée.

Vous pouvez exécuter la procédure pas à pas sur un ordinateur qui possède à la fois [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et un environnement de développement R, mais nous ne recommandons pas cette configuration pour un environnement de production.

## <a name="install-machine-learning-for-sql-server"></a>Installer d’apprentissage pour SQL Server

Vous devez avoir accès à une instance de SQL Server avec prise en charge pour R installé. Cette procédure pas à pas a été initialement développé pour le serveur SQL 2016 et testé sur 2017, donc vous devez être en mesure d’utiliser une des versions suivantes de SQL Server. (Il existe certaines différences mineures dans les fonctions RevoScaleR entre les versions.)

+ Apprentissage automatique (de-de base de données) de Services pour SQL Server 2017
+ SQL Server 2016 R Services

Pour plus d’informations, consultez [configurer SQL Server R Services (dans la base de données](../r/set-up-sql-server-r-services-in-database.md).

> [!IMPORTANT]
> Versions de SQL Server antérieure à 2016 ne gèrent pas intégration à R. Toutefois, vous pouvez utiliser les anciennes bases de données SQL en tant que source de données ODBC.

## <a name="install-an-r-development-environment"></a>Installez un environnement de développement R

Pour cette procédure pas à pas, nous vous recommandons d’utiliser un environnement de développement R. Voici quelques suggestions :

- **R Tools pour Visual Studio** (RTV) est un plug-in qui fournit la fonctionnalité Intellisense, le débogage et la prise en charge de Microsoft R. vous pouvez l’utiliser avec R Server et SQL Server Machine Learning Services. Pour télécharger, consultez [Outils R pour Visual Studio](https://www.visualstudio.com/vs/rtvs/).

- **Le Client Microsoft R** est un outil de développement légère qui prend en charge le développement dans R à l’aide du package RevoScaleR. Pour l’obtenir, consultez [Get Started with Microsoft R Client (Prise en main de Microsoft R Client)](https://docs.microsoft.com/machine-learning-server/r-client/what-is-microsoft-r-client).

- **RStudio** est un des environnements les plus populaires pour le développement R. Pour plus d’informations, consultez [https://www.rstudio.com/products/RStudio/](https://www.rstudio.com/products/RStudio/).

    Impossible d’effectuer ce didacticiel à l’aide d’une installation générique de RStudio ou un autre environnement ; Vous devez également installer les packages R et les bibliothèques de connectivité de Microsoft R Open. Pour plus d’informations, consultez [Configurer un client de science des données](../r/set-up-a-data-science-client.md).

- Outils de base R (R.exe, RTerm.exe, RScripts.exe) sont également installés par défaut lorsque vous installez R dans SQL Server ou de Client de R. Si vous ne souhaitez pas installer un bus IDE, vous pouvez utiliser ces outils.

## <a name="get-permissions-on-the-sql-server-instance-and-database"></a>Obtenir les autorisations requises sur l’instance de SQL Server et de la base de données

Pour vous connecter à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour exécuter des scripts et charger des données, vous devez disposer d’une connexion valide sur le serveur de base de données.  Vous pouvez utiliser un compte de connexion SQL ou l’authentification Windows intégrée. Demandez à l’administrateur de base de données pour configurer les autorisations suivantes pour le compte, dans la base de données où vous utilisez r :

- Créer une base de données, des tables, des fonctions et des procédures stockées
- Écrire des données dans des tables
- Possibilité d’exécuter le script R (`GRANT EXECUTE ANY EXTERNAL SCRIPT to <user>`)

Pour cette procédure pas à pas, nous avons utilisé la connexion SQL **RTestUser**. En règle générale, nous recommandons que vous utilisez l’authentification Windows intégrée, mais à l’aide de la connexion SQL est plus simple des fins de démonstration.

## <a name="change-list"></a>Liste des modifications

+ Cet exemple a été développé à l’aide de SQL Server 2016 R Services. Toutefois, les modifications avec rupture introduites dans les composants de Microsoft R pour 2016 SP1. Plus précisément, le _varsToDrop_ et _varsToKeep_ paramètres ont été n’est plus pris en charge pour les sources de données SQL Server. Therefre, si vous avez téléchargé une version du didacticiel avant SP1, il ne fonctionnera plus avec des builds post-SP1.

+ La version actuelle de l’exemple a été testée à l’aide d’une build de la version préliminaire de SQL Server 2017 Machine Learning Services (RC1 et RC2). En règle générale, presque toutes les étapes doivent s’exécuter sans modification entre 2016 SP1 et 2017.

## <a name="next-lesson"></a>Leçon suivante

[Préparer les données à l’aide de PowerShell](/walkthrough-prepare-the-data.md)
