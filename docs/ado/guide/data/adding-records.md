---
title: Ajouter des enregistrements | Documents Microsoft
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: guide
ms.technology: drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AddNew method [ADO]
- ADO, editing data
- editing data [ADO], AddNew method
- editing data [ADO], adding data
ms.assetid: dd34669e-6f06-403b-9241-1c85c82aecc2
caps.latest.revision: "10"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 1d46cb8e801f39cf8b87c0c3187667247e3da9d0
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="adding-records-to-a-recordset"></a>Ajout d’enregistrements à un jeu d’enregistrements
Utilisez le **AddNew** méthode pour créer et initialiser un nouvel enregistrement dans un fichier **Recordset**. Vous pouvez utiliser la **prend en charge** méthode avec un **CursorOptionEnum** valeur **adAddNew** pour vérifier si vous pouvez ajouter des enregistrements à actuel **Recordset** objet.

 Après avoir appelé la **AddNew** (méthode), le nouvel enregistrement devient l’enregistrement actif et reste actif après avoir appelé la **mise à jour** (méthode). Si le **Recordset** objet ne prend pas en charge les signets, vous n’êtes peut-être pas en mesure d’accéder au nouvel enregistrement une fois que vous déplacez vers un autre enregistrement. Par conséquent, selon le type de curseur, vous devrez peut-être appeler le **Requery** méthode pour rendre le nouvel enregistrement accessible.

 Si vous appelez **AddNew** lors de la modification de l’enregistrement en cours ou lors de l’ajout d’un nouvel enregistrement, ADO appelle la **mise à jour** méthode pour enregistrer les modifications et crée ensuite le nouvel enregistrement.

 Cette section contient les rubriques suivantes.

-   [Ajout d’enregistrements avec AddNew](../../../ado/guide/data/adding-records-using-addnew.md)

-   [Ajout de plusieurs champs](../../../ado/guide/data/adding-multiple-fields.md)

-   [Détermination du mode d’édition](../../../ado/guide/data/determining-edit-mode.md)

-   [Utilisation d’AddNew dans les modes immédiat et batch](../../../ado/guide/data/using-addnew-in-immediate-and-batch-modes.md)
