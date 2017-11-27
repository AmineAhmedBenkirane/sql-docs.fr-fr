---
title: "Enregistrer les métadonnées (SybaseToSQL) | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology: sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: b2517735-dd19-449f-8cee-08e68ca89d3a
caps.latest.revision: "3"
author: Shamikg
ms.author: Shamikg
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 165728c1100ce98d166a2ae73ee092baae9f0417
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="save-metadata--sybasetosql"></a>Enregistrer les métadonnées (SybaseToSQL)
Le **enregistrer les métadonnées** boîte de dialogue vous invite à charger les métadonnées dans votre projet SSMA avant de l’enregistrer. Ce permet d’avoir un fichier de projet complet que vous pouvez utiliser hors connexion et les envoyer à d’autres personnes, tels que les membres du support technique.  
  
Pour accéder à la **enregistrer les métadonnées** boîte de dialogue, enregistrez le projet. Si les métadonnées sont manquantes, SSMA affichera le **enregistrer les métadonnées** boîte de dialogue.  
  
## <a name="options"></a>Options  
**Nom**  
Le nom de chaque base de données dans le projet.  
  
**État**  
Indique si les métadonnées sont chargées dans le projet SSMA, ou si les métadonnées sont manquantes.  
  
SSMA charge les métadonnées dans le projet en tant que nécessaire. Métadonnées sont chargées automatiquement lorsque vous parcourir les métadonnées et convertissez des schémas.  
  
**Tout sélectionner**  
Sélectionne la listés de toutes les bases de données.  
  
**Désactiver**  
Efface la case à cocher pour toutes les bases de données avec les métadonnées manquantes. Impossible d’effacer la case à cocher si une métadonnée a été chargée.  
  
**Enregistrer**  
Enregistre le projet, le chargement des métadonnées pour les bases de données sélectionnées qui ont des métadonnées manquantes.  
  
**Annuler**  
Annule l’enregistrement opération. Métadonnées manquantes ne sont pas chargée dans le projet.  
  
