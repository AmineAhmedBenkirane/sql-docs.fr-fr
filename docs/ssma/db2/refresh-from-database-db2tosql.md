---
title: "Actualiser à partir de la base de données (DB2ToSQL) | Documents Microsoft"
ms.prod: sql-non-specified
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 613a8368-b372-443f-8252-fb6dc31a003d
caps.latest.revision: 5
author: sabotta
ms.author: carlasab
manager: lonnyb
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 5c0d2d3ad83249c4e438e01a31a41d9e8e226ce8
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="refresh-from-database-db2tosql"></a>Actualiser à partir de la base de données (DB2ToSQL)
Le **Actualiser à partir de la base de données** boîte de dialogue vous permet de sélectionner les objets à actualiser à partir de la base de données DB2. Lignes dans la boîte de dialogue sont codées par couleur en fonction de l’état des métadonnées :  
  
-   Si les métadonnées de l’objet a été modifié localement et dans la base de données DB2, la ligne est bleue.  
  
-   Si les métadonnées de l’objet a été modifié dans la base de données DB2, mais pas dans SSMA, la ligne est jaune.  
  
-   Si les métadonnées de l’objet a été modifié localement, mais pas dans la base de données DB2, la ligne est verte.  
  
-   Si l’objet est nouveau dans la base de données DB2, la ligne est rose.  
  
Vous pouvez spécifier des paramètres d’actualisation objet par défaut dans le **les paramètres de projet** boîte de dialogue. Pour plus d’informations, consultez [paramètres du projet &#40; Synchronisation &#41; &#40; DB2ToSQL &#41; ](../../ssma/db2/project-settings-synchronization-db2tosql.md).  
  
Pour accéder à la **Actualiser à partir de la base de données** boîte de dialogue, avec le bouton droit, un objet dans l’Explorateur de métadonnées DB2 et cliquez sur **Actualiser à partir de la base de données**.  
  
## <a name="options"></a>Options  
**Réduction (-)**  
Réduire tous les groupes d’objets pour masquer les objets individuels.  
  
**Développement (+)**  
Développez tous les groupes d’objets pour afficher les objets individuels.  
  
**Afficher/masquer les objets égales**  
Masquer les objets dans la liste si les métadonnées de l’objet sont le même dans la base de données DB2 et SSMA.  
  
**Actualiser à partir de la base de données (flèche)**  
Utilisez le bouton fléché pour spécifier que les métadonnées pour les objets sélectionnés doivent être mis à jour dans SSMA.  
  
**Effectuez pas actualiser à partir de la base de données (bouton) X**  
Utilisez le bouton X pour spécifier que les métadonnées pour les objets sélectionnés ne doivent pas mis à jour dans SSMA.  
  
**Légende**  
Affiche un **légende** boîte de dialogue. La légende contient le mappage entre les États de métadonnées et les couleurs de ligne.  
  
Pour conserver le **légende** boîte de dialogue sur le **Actualiser à partir de la base de données** boîte de dialogue, sélectionnez le **afficher en haut** case à cocher.  
  

