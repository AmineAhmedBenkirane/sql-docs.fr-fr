---
title: "Mise à jour de données | Documents Microsoft"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data updates [ADO], about data updates
- updating data [ADO], about updating data
ms.assetid: 6508e4e9-e33a-4dad-b340-5d632fd78a91
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: c8138aeea7e5ea40e659a6fed5f5d5f551b1c69d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="updating-data"></a>Mise à jour des données
Comportement de mise à jour et fonctionnalités dépend en grande partie mettre à jour le mode (type de verrou), type de curseur et l’emplacement du curseur.  
  
 Utilisez le **mise à jour** méthode pour enregistrer les modifications apportées à l’enregistrement en cours d’un **Recordset** objet depuis l’appel le **AddNew** (méthode) ou parce que la modification des valeurs de champs dans un enregistrement existant. Le **Recordset** objet doit prendre en charge les mises à jour.  
  
 Si le **Recordset** objet prend en charge la mise à jour par lot, vous pouvez mettre en cache plusieurs modifications apportées à un ou plusieurs enregistrements localement jusqu'à ce que vous appeliez la **UpdateBatch** (méthode). Si vous modifiez l’enregistrement actif ou ajoutez un nouvel enregistrement lorsque vous appelez le **UpdateBatch** (méthode), ADO appelle automatiquement la **mise à jour** méthode pour enregistrer les modifications en attente à l’enregistrement actif avant transmettre les modifications par lot au fournisseur.  
  
 L’enregistrement actif reste actif après avoir appelé la **mise à jour** ou **UpdateBatch** méthodes.  
  
 Cette section contient les rubriques suivantes.  
  
-   [Mode immédiat](../../../ado/guide/data/immediate-mode.md)  
  
-   [En Mode Batch](../../../ado/guide/data/batch-mode.md)  
  
-   [Traitement des transactions](../../../ado/guide/data/transaction-processing.md)
