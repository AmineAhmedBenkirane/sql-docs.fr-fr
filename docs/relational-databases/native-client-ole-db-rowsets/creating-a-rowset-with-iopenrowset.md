---
title: Création d’un ensemble de lignes avec IOpenRowset | Documents Microsoft
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: native-client-ole-db-rowsets
ms.reviewer: ''
ms.suite: sql
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IOpenRowset interface
- rowsets [OLE DB], creating
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets, creating
ms.assetid: e8bc3de7-4b97-4de9-8df8-e11947d24045
caps.latest.revision: 30
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: fb837520fd84d79970ad387c8b798e59b8bbdd6f
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-rowset-with-iopenrowset"></a>Création d'un ensemble de lignes avec IOpenRowset
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prend en charge du fournisseur OLE DB Native Client le **IOpenRowset::OpenRowset** méthode avec les restrictions suivantes :  
  
-   Une table de base ou une vue doit être spécifié dans une base de données ID (DBID) de la structure qui le *pTableID* paramètre pointe vers.  
  
-   Le DBID *eKind* membre doit indiquer DBKIND_NAME.  
  
-   Le DBID *uName* membre doit spécifier le nom d’une vue ou d’une table de base existante en tant que chaîne de caractères Unicode.  
  
-   Le *pIndexID* paramètre de **OpenRowset** doit être NULL.  
  
 Le jeu de résultats de **IOpenRowset::OpenRowset** contient un ensemble de lignes unique. Les jeux de résultats qui contiennent un ensemble de lignes unique peuvent être pris en charge par [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] curseurs. La prise en charge des curseurs permet au développeur d'utiliser les mécanismes d'accès concurrentiel de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Ensembles de lignes](../../relational-databases/native-client-ole-db-rowsets/rowsets.md)  
  
  
