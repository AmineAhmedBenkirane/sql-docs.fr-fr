---
title: Rapport de Migration de données (MySQLToSQL) | Documents Microsoft
ms.prod: sql
ms.prod_service: sql-tools
ms.service: ''
ms.component: ssma-mysql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 5524a575-67dd-4ef6-9d17-3412df9b9f9c
caps.latest.revision: 4
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 6771540f45618793493baed3baa0485473d0641c
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="data-migration-report--mysqltosql"></a>Rapport de Migration de données (MySQLToSQL)
Le **rapport de Migration de données** boîte de dialogue s’affiche après la migration des données à [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)].  
  
## <a name="options"></a>Options  
**État**  
Indique l’état de la migration des données à partir de la source de la base de données cible.  
  
**De**  
La table source.  
  
**Pour**  
La table cible.  
  
**Nombre total de lignes**  
Le nombre de lignes de données dans la table source.  
  
**Nombre de lignes a été migrées**  
Le nombre de lignes de données migrés avec succès à la table cible.  
  
**Rapport**  
Le pourcentage de lignes migrés avec succès.  
  
**Détails**  
En cas d’échec de la migration des données, cliquez pour afficher les détails de la migration de la ligne sélectionnée dans le rapport. SSMA affichera la raison de l’échec.  
  
**Enregistrer le rapport**  
Enregistre le rapport à un. CSV, fichier (valeurs séparées par des virgules), qui peut être examiné à l’aide de Microsoft Excel.  
  
