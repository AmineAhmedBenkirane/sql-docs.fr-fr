---
title: "Enregistrer (non autorisé), boîte de dialogue | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssms-visual-db
ms.reviewer: 
ms.suite: sql
ms.technology: tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: sql13.swb.table.tablerecreatenosave.f1
ms.assetid: 7efda8e3-739f-4c97-a497-b8808a0acbea
caps.latest.revision: "4"
author: stevestein
ms.author: sstein
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 188f544161ee56e63d92e381fa4cd5485eeba05e
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="save-not-permitted-dialog-box"></a>Enregistrer (non autorisé), boîte de dialogue
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)] La boîte de dialogue **Enregistrer** (non autorisé) vous prévient que l’enregistrement des changements n’est pas autorisé car les changements que vous avez apportés nécessitent la suppression et la recréation des tables répertoriées.  
  
Les actions suivantes peuvent nécessiter la recréation d'une table :  
  
-   Ajout d'une nouvelle colonne au milieu de la table  
  
-   Suppression d'une colonne  
  
-   Modification de la possibilité de valeur nulle d'une colonne  
  
-   Modification de l'ordre des colonnes  
  
-   Modification du type de données d'une colonne  
  
Pour modifier cette option, dans le menu **Outils** , cliquez sur **Options**, développez **Concepteurs**, puis cliquez sur **Concepteurs de bases de données et de tables**. Cochez ou décochez la case **Empêcher l’enregistrement de modifications qui nécessitent une recréation de la table** .  
  
