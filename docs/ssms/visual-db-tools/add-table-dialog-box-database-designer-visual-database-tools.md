---
title: "Ajouter une table, boîte de dialogue (Concepteur de bases de données) (Visual Database Tools) | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: sql-non-specified
ms.service: 
ms.component: ssms-visual-db
ms.reviewer: 
ms.suite: sql
ms.technology: tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vdtsql.chm:65555
- vdt.dlgbox.schema.addtable
ms.assetid: 3c0b1b30-795c-4240-91d6-890b8348014a
caps.latest.revision: "4"
author: stevestein
ms.author: sstein
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 8feca58b1bbf76906ffba0e8855ec572302fde46
ms.sourcegitcommit: b2d8a2d95ffbb6f2f98692d7760cc5523151f99d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2017
---
# <a name="add-table-dialog-box-database-designer-visual-database-tools"></a>Boîte de dialogue Ajouter une table (Concepteur de bases de données)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)] Vous permet d’ajouter des tables dans le Concepteur de bases de données.  
  
> [!NOTE]  
> Si la table est publiée pour réplication, vous devez apporter vos modifications au schéma à l’aide de l’instruction Transact-SQL [ALTER TABLE](http://msdn.microsoft.com/en-us/f1745145-182d-4301-a334-18f799d361d1) ou de SMO (SQL Server Management Objects). Lorsque les modifications sont apportées au schéma à l'aide du Concepteur de tables ou du Concepteur de schémas de base de données, celui-ci tente d'abandonner la table et de la recréer. Toutefois, il est impossible d'abandonner les objets publiés, par conséquent les modifications du schéma échoueront.  
  
## <a name="uielement-list"></a>Liste des éléments de l'interface utilisateur  
**Actualiser**  
Actualise la liste des tables afin de refléter l'état actuel de la base de données.  
  
**Ajouter**  
Ajoute la ou les tables sélectionnées.  
  
> [!NOTE]  
> Si vous souhaitez ajouter plusieurs tables au schéma, vous pouvez toutes les sélectionner avant de cliquer sur **Ajouter**. Vous pouvez aussi double-cliquer sur chaque table à ajouter, puis cliquer sur **Fermer** quand vous avez terminé.  
  
**Fermer**  
Ferme la boîte de dialogue sans ajouter de tables supplémentaires.  
  
## <a name="see-also"></a>Voir aussi  
[Ajouter des tables à des schémas &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/add-tables-to-diagrams-visual-database-tools.md)  
  
