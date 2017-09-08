---
title: SQL Server R Services | Microsoft Docs
ms.custom:
- SQL2016_New_Updated
ms.date: 06/22/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- r-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba1dea65-40ea-484a-b767-53680c954934
caps.latest.revision: 38
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 140885b86f0f6fa1a56119246c859f143f596726
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="machine-learning-services-with-python"></a>Machine Learning Services avec Python

Python est un langage qui offre une grande souplesse et puissance pour diverses tâches d’apprentissage. Les bibliothèques Open source pour Python incluent plusieurs plateformes pour les réseaux neuronaux personnalisables, ainsi que les bibliothèques pour le traitement du langage naturel. À présent, cette langue largement utilisée est prise en charge dans SQL Server 2017 CTP 2.0 et versions ultérieures.

Étant donné que les Python est intégré à la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] moteur de base de données, vous pouvez conserver analytique proches des données et éliminer les coûts et les risques de sécurité liés au déplacement des données.  Vous pouvez déployer des solutions d’apprentissage machine en fonction de Python à l’aide d’outils pratiques et familiers, tels que Visual Studio. Les applications de production peuvent obtenir des prédictions, les modèles, ou les éléments visuels à partir du runtime Python 3.5 en appelant simplement un T-SQL de procédure stockée.

Cette version inclut la distribution Anaconda Python, ainsi que la nouvelle [revoscalepy](../python/what-is-revoscalepy.md) bibliothèque, afin d’améliorer l’évolutivité et des performances de vos solutions d’apprentissage.

Vous pouvez installer tout ce dont vous avez besoin pour commencer avec Python via le programme d’installation de SQL Server 2017 :

+ **Machine Learning Services (de-de base de données) :** installer cette fonctionnalité, ainsi que le moteur de base de données SQL Server, pour activer l’exécution sécurisée des scripts R sur le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ordinateur.
  
     Lorsque vous activez cette fonctionnalité, les extensions sont installées dans le moteur de base de données pour prendre en charge l’exécution de scripts Python et un nouveau service est créé, le [!INCLUDE[rsql_launchpad](../../includes/rsql-launchpad-md.md)], pour gérer les communications entre le runtime Python et [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.

+ **Machine Learning Server (autonome) :** si vous n’avez pas besoin d’intégration de SQL Server, installez cette fonction pour obtenir un support technique de Python dans Microsoft R Server. Cela vous permet d’opérationnaliser les solutions de Python à l’aide de **mrsdeploy**.
  
     N’installez pas cette fonctionnalité sur le même ordinateur qui exécute SQL Server Machine Learning Services.


## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer les Services de base de données d’apprentissage Python](setup-python-machine-learning-services.md)

[Didacticiels de Python](../tutorials/sql-server-python-tutorials.md)
