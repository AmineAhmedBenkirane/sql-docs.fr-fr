---
title: "Extraction d’une ligne unique avec IRow | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-ole-db-rowsets
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- fetching rows
- IRow interface
- single row fetching [SQL Server Native Client]
- OLE DB rowsets, fetching
- rowsets [OLE DB], fetching
- SQL Server Native Client OLE DB provider, fetching
ms.assetid: 07c803ca-299a-42c5-ba02-360b9631d15f
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b92878a8f847063e2a2bf18ee6bdaa6433de3d8b
ms.sourcegitcommit: a0aa5e611a0e6ebb74ac1e2f613e8916dc7a7617
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2018
---
# <a name="fetching-a-single-row-with-irow"></a>Extraction d'une ligne unique avec IRow
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  Le **IRow** interface mise en œuvre dans le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client fournisseur OLE DB natif est simplifiée pour améliorer les performances. **IRow** permet un accès direct aux colonnes d’un objet ligne unique. Si vous savez à l’avance que le résultat d’une exécution de commande génère une ligne exactement, **IRow** extraira les colonnes de cette ligne. Si le jeu de résultats comprend plusieurs lignes, **IRow** exposera uniquement la première ligne.  
  
 Le **IRow** implémentation n’autorise pas aucune navigation de la ligne. Chaque colonne dans la ligne est accédée une seule fois, à une exception près : une colonne peut être accédée une fois pour rechercher la taille de colonne et une autre fois pour extraire les données.  
  
> [!NOTE]  
>  **IRow::Open** prend en charge le seul type DBGUID_STREAM et DBGUID_NULL d’objets à ouvrir.  
  
 Pour obtenir un objet de la ligne à l’aide **ICommand::Execute** méthode, IID_IRow doit être passé. Le **IMultipleResults** interface doit être utilisé pour gérer plusieurs jeux de résultats. **IMultipleResults** prend en charge **IRow** et **IRowset**. **IRowset** est utilisé pour les opérations en bloc.  
  
## <a name="in-this-section"></a>Dans cette section  
  
-   [Utilisation d’IRow::GetColumns](../../relational-databases/native-client-ole-db-rowsets/using-irow-getcolumns.md)  
  
-   [Extraction de données BLOB à l’aide d’IRow](http://msdn.microsoft.com/library/badbd6ac-20aa-4891-a14f-48d38e7f30de)  
  
## <a name="see-also"></a>Voir aussi  
 [Ensembles de lignes](../../relational-databases/native-client-ole-db-rowsets/rowsets.md)  
  
  
