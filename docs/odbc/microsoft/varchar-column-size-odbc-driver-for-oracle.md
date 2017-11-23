---
title: Taille de la colonne VARCHAR (le pilote ODBC pour Oracle) | Documents Microsoft
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: microsoft
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data types [ODBC], ODBC driver for Oracle
- varchar column size [ODBC]
- ODBC driver for Oracle [ODBC], data types
ms.assetid: eb4cb410-3d00-4251-8c5e-a06f36c4dac7
caps.latest.revision: "8"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: fdd09067b2a938a285264955ad0ff05c6455c00a
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="varchar-column-size-odbc-driver-for-oracle"></a>Taille de la colonne VARCHAR (le pilote ODBC pour Oracle)
> [!IMPORTANT]  
>  Cette fonctionnalité sera supprimée dans une future version de Windows. Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité. Au lieu de cela, utilisez le pilote ODBC fourni par Oracle.  
  
 Dans Oracle8, la taille maximale d’une colonne VARCHAR a augmenté de 2000 à 4 000 octets. Logiciel client Oracle 7.3.x a aucun moyen pour lier une valeur de paramètre supérieure à 2 000 octets. Par conséquent, si vous créez une table avec une colonne VARCHAR de taille supérieure à 2 000 octets, vous ne pourrez pas effectuer des insertions paramétrées, les mises à jour, les suppressions et les requêtes avec des données qui dépassent la limite de 2000-octets du logiciel client. Mesure à la fois le pilote ODBC pour Oracle et le fournisseur OLE DB pour Oracle utilisent des requêtes, les mises à jour, suppressions et insertions paramétrées, ils signalera ORA-01026 erreurs dans ce cas. Les données qui se trouve dans les limites appliquées par le logiciel client Oracle fonctionne. Pour éviter cette limite octets 2000, vous devez mettre à niveau votre logiciel client Oracle8 (8.0.4.1.1c ou une version ultérieure).
