---
title: "Prochaine Position d’extraction | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-ole-db-rowsets
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- fetching rows
- OLE DB rowsets, fetching
- next fetch position
- rowsets [OLE DB], fetching
ms.assetid: 9ef74b3f-c9c0-492f-9b93-d65738a61abd
caps.latest.revision: "30"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c0e1b54804a64941840bc62b003564e012f07088
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="fetching-rows---next-fetch-position"></a>Lignes de l’extraction - prochaine Position d’extraction
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB fournisseur assure le suivi de la prochaine position d’extraction ainsi qu’une séquence d’appels à la **GetNextRows** (méthode) (sans ignore, les modifications de direction ou appels intermédiaires de la **FindNextRow**, **recherche**, ou **RestartPosition** méthodes) lit l’ensemble de lignes sans ignorer ou répéter n’importe quelle ligne. La prochaine position d’extraction est modifiée en appelant **IRowset::GetNextRows**, **IRowset::RestartPosition**, ou **IRowsetIndex::Seek**, ou en appelant **FindNextRow** avec une valeur null *pBookmark* valeur. Appel de **FindNextRow** avec une valeur non null *pBookmark* valeur n’affecte pas la prochaine position d’extraction.  
  
## <a name="see-also"></a>Voir aussi  
 [Récupération de lignes](../../relational-databases/native-client-ole-db-rowsets/fetching-rows.md)  
  
  
