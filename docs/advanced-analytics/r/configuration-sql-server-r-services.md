---
title: Gestion et configuration | Documents Microsoft
ms.custom: 
ms.date: 05/31/2016
ms.reviewer: 
ms.suite: sql
ms.prod: machine-learning-services
ms.prod_service: machine-learning-services
ms.component: r
ms.technology: r-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0fd4554-60c6-4181-ac4c-2e366fb434f6
caps.latest.revision: "7"
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 075434e13ad8e988041eee360674ffcb59729312
ms.sourcegitcommit: 23433249be7ee3502c5b4d442179ea47305ceeea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2017
---
# <a name="configuration-and-management"></a>Configuration et gestion

Cet article fournit des liens vers des informations plus détaillées sur la façon de configurer un serveur pour prendre en charge des services d’apprentissage machine avec SQL Server dans les produits suivants :

+ SQL Server 2016 R Services (de-de base de données)
+ SQL Server 2017 Machine Learning Services (de-de base de données)

> [!NOTE]
> 
> Ce contenu a été écrit à l’origine pour la version SQL Server 2016, ce qui est pris en charge uniquement dans le langage R.
> 
> Dans SQL Server 2017, prend en charge de Python a été ajouté, mais l’infrastructure sous-jacente de l’architecture et de services est le même. Par conséquent, vous pouvez configurer la sécurité, mémoire, la gouvernance des ressources et autres options pour prendre en charge l’exécution de scripts Python, de la même façon que vous le feriez pour des scripts R.
> 
> Toutefois, étant donné que prise en charge de Python est une nouvelle fonctionnalité, les informations détaillées sur les optimisations potentielles de la charge de travail Python n’est pas encore disponible. Revenez plus tard.

## <a name="r-package-management"></a>Gestion des packages R

Ces rubriques décrivent comment installer de nouveaux packages R sur l’instance de SQL Server, gestion des bibliothèques de package de R et restaurer des bibliothèques de package après une restauration de base de données.

+ [Installation et gestion des packages R](installing-and-managing-r-packages.md)
+ [L’installation de nouveaux Packages R](install-additional-r-packages-on-sql-server.md)
+ [Activer la gestion de Package pour une Instance à l’aide de rôles de base de données](r-package-how-to-enable-or-disable.md)
+ [Créer un référentiel de packages Local à l’aide de miniCRAN](create-a-local-package-repository-using-minicran.md)
+ [Déterminer que les Packages R installés sur SQl Server](determine-which-packages-are-installed-on-sql-server.md)
+ [Synchronisation des Packages R entre SQL Server et le système de fichiers](package-install-uninstall-and-sync.md)
+ [Packages R sont installés dans les bibliothèques utilisateur](packages-installed-in-user-libraries.md)

## <a name="service-configuration"></a>Configuration du service

Ces rubriques expliquent comment apporter des modifications à l’architecture sous-jacente du service et comment gérer les entités de sécurité associées au service d’extensibilité.

+ [Considérations relatives à la sécurité](security-considerations-for-the-r-runtime-in-sql-server.md)
+ [Modifier le pool de comptes d’utilisateurs pour SQL Server R Services](../../advanced-analytics/r/modify-the-user-account-pool-for-sql-server-r-services.md)
+ [Configurer et gérer les extensions analytiques avancées](../../advanced-analytics/r/configure-and-manage-advanced-analytics-extensions.md)
+ [Activer la gestion de Package pour une Instance à l’aide de rôles de base de données](r-package-how-to-enable-or-disable.md)
+ [Réglage des performances pour R Services](sql-server-r-services-performance-tuning.md)

## <a name="resource-governance"></a>Gouvernance des ressources

Ces rubriques décrivent comment implémenter la gestion des ressources pour les travaux R ou Python à l’aide de la fonctionnalité de Resource Governor tenant compte dans l’édition Enterprise.

+ [Gouvernance des ressources pour R Services](../../advanced-analytics/r/resource-governance-for-r-services.md)
+ [Comment créer un Pool de ressources pour R](../../advanced-analytics/r/how-to-create-a-resource-pool-for-r.md)

Voir aussi :

+ [R d’analyse à l’aide de rapports SSMS personnalisé](monitor-r-services-using-custom-reports-in-management-studio.md)

## <a name="initial-setup"></a>Installation initiale

Vous trouverez plus d’aide relatives à l’installation initiale et la configuration dans les rubriques suivantes :

+ [FAQ d’installation et de mise à niveau](../r/upgrade-and-installation-faq-sql-server-r-services.md)
+ [Considérations relatives à la sécurité](../r/security-considerations-for-the-r-runtime-in-sql-server.md)
+ [Problèmes connus pour R Services](../../advanced-analytics/known-issues-for-sql-server-machine-learning-services.md)

