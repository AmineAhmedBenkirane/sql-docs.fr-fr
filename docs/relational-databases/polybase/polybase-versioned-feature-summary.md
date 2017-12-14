---
title: "Récapitulatif des fonctionnalités avec version PolyBase | Microsoft Docs"
ms.custom: 
ms.date: 08/29/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.service: 
ms.component: polybase
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6591994d-6109-4285-9c5b-ecb355f8a111
caps.latest.revision: "10"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 70725ec64b79f538b4129993de83dfd97772a667
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2017
---
# <a name="polybase-versioned-feature-summary"></a>Récapitulatif des fonctionnalités de version PolyBase
[!INCLUDE[appliesto-ss-xxxx-asdw-pdw-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)] Récapitulatif des fonctionnalités PolyBase disponibles pour les services et produits SQL Server.  
  
## <a name="feature-summary-for-product-releases"></a>Synthèse des fonctionnalités pour les versions du produit  
 Ce tableau récapitule les principales fonctionnalités de PolyBase et des produits dans lesquels elles sont disponibles.  
  
||||||
|-|-|-|-|-|   
|**Fonctionnalité**|**SQL Server 2016**|**Azure SQL Database**|**Azure SQL Data Warehouse**|**Parallel Data Warehouse**| 
|Interroger des données Hadoop avec [!INCLUDE[tsql](../../includes/tsql-md.md)]|oui|non|non|oui|
|Importer des données depuis Hadoop|oui|non|non|oui|
|Exporter des données vers Hadoop  |oui|non|non| oui|
|Interroger, importer, exporter vers HDInsights |non|non|non|non
|Transmettre des calculs de requête à Hadoop|oui|non|non|oui|  
|Importer des données depuis le stockage d’objets blob Azure|oui|non|oui|oui| 
|Exporter des données vers le stockage d’objets blob Azure|oui|non|oui|oui|  
|Importer des données depuis Azure Data Lake Store|non|non|oui|non|    
|Exporter des données depuis Azure Data Lake Store|non|non|oui|non|
|Exécuter des requêtes PolyBase à partir des outils décisionnels de Microsoft|oui|non|oui|oui|   


## <a name="pushdown-computation-supported-t-sql-operators"></a>Opérateurs T-SQL pris en charge pour la transmission des calculs
Dans SQL Server et APS, tous les opérateurs T-SQL ne peuvent pas être transmis au cluster hadoop. Le tableau ci-dessous répertorie tous les opérateurs pris en charge et une partie des opérateurs non pris en charge. 

||||
|-|-|-| 
|**Type d’opérateur**|**Transmissible à Hadoop**|**Transmissible au Stockage Blob**|
|Projections de colonne|oui|non|
|Prédicats|oui|non|
|Agrégats|partielles|non|
|Jointures entre les tables externes|non|non|
|Jointures entre les tables externes et les tables locales|non|non|
|Tris|non|non|

Une agrégation partielle signifie qu’une agrégation finale doit se produire une fois que les données atteignent SQL Server, mais qu’une partie de l’agrégation se produit dans Hadoop. Il s’agit d’une méthode courante de calcul des agrégations dans les systèmes à traitement parallèle massif.  
## <a name="see-also"></a>Voir aussi  
 [Guide de PolyBase](../../relational-databases/polybase/polybase-guide.md)  
  
  
