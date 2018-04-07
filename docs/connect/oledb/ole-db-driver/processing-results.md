---
title: Le traitement des résultats | Documents Microsoft
description: Le traitement des résultats
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: oledb-driver-for-sql-server
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB Driver for SQL Server, results processing
- OLE DB, processing results
- rowsets [SQL Server], results processing
- results [OLE DB Driver for SQL Server]
author: pmasl
ms.author: Pedro.Lopes
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 6b564e696b28ca751179376f66458f7b11652ad9
ms.sourcegitcommit: 9351e8b7b68f599a95fb8e76930ab886db737e5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2018
---
# <a name="processing-results"></a>Traitement des résultats
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  Si un objet d'ensemble de ligne est produit par l'exécution d'une commande ou la génération d'un objet d'ensemble de ligne directement à partir du fournisseur, le consommateur doit extraire et accéder aux données dans l'ensemble de lignes.  
  
 Ensembles de lignes sont les objets centraux qui permettent le pilote OLE DB pour SQL Server exposer des données dans un format tabulaire. Conceptuellement, un ensemble de lignes est un jeu de lignes dans lequel chaque ligne possède des données de colonne. Un objet d’ensemble de lignes expose des interfaces telles que **IRowset** (contient des méthodes pour extraire les lignes à partir de l’ensemble de lignes de manière séquentielle), **IAccessor** (permet la définition d’un groupe de liaisons de colonne décrivant la manière de données tabulaires sont liées aux variables de programme de consommateur), **IColumnsInfo** (fournit des informations sur les colonnes dans l’ensemble de lignes), et **IRowsetInfo** (fournit des informations sur l’ensemble de lignes).  
  
 Un consommateur peut appeler le **IRowset::GetData** pour récupérer une ligne de données à partir de l’ensemble de lignes dans une mémoire tampon. Avant de **GetData** est appelée, le consommateur décrit la mémoire tampon à l’aide d’un ensemble de structures DBBINDING. Chaque liaison décrit la manière dont une colonne dans un ensemble de lignes est stockée dans une mémoire tampon de consommateur et contient les éléments suivants :  
  
-   ordinal de la colonne (ou paramètre) auquel la liaison s'applique ;  
  
-   informations concernant ce qui est lié (par exemple, valeur des données, longueur des données et leur état de liaison) ;  
  
-   informations concernant ce qui est décalé dans la mémoire tampon à chacune de ces parties ;  
  
-   longueur et type des valeurs de données telles qu'elles existent dans la mémoire tampon du consommateur.  
  
 Lors de l'obtention des données, le fournisseur utilise les informations dans chaque liaison afin de déterminer où et comment extraire des données de la mémoire tampon du consommateur. Lors de la définition des données dans la mémoire tampon du consommateur, le fournisseur utilise les informations dans chaque liaison afin de déterminer où et comment retourner des données dans la mémoire tampon du consommateur.  
  
 Une fois que les structures DBBINDING sont spécifiés, un accesseur est créé (**IAccessor::CreateAccessor**). Un accesseur est une collection de liaisons utilisée pour obtenir ou définir les données dans la mémoire tampon du consommateur.  
  
## <a name="see-also"></a>Voir aussi  
 [Création d’un pilote de base de données OLE pour l’Application de SQL Server](../../oledb/ole-db-driver/creating-a-oledb-driver-for-sql-server-application.md)   
 [Rubriques de procédures OLE DB](../../oledb/ole-db-how-to/ole-db-how-to-topics.md)  
  
  
