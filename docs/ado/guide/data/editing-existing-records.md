---
title: Modification des enregistrements existants | Documents Microsoft
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology: drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editing data [ADO], existing records
ms.assetid: 17ce1263-5897-452a-9ea5-c7f96b33df65
caps.latest.revision: "10"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: fe45ca5b7d50752544c44eac530a58ce5f97220c
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="editing-existing-records"></a>Modification des enregistrements existants
Pour modifier les enregistrements existants, passer à la ligne que vous souhaitez modifier et de modifier le **valeur** propriété des champs que vous souhaitez modifier. Pour plus d’informations sur la **champ** l’objet **valeur** propriété, consultez [examen des données](../../../ado/guide/data/examining-data.md). Selon le type de curseur, vous allez utiliser **mise à jour** ou **UpdateBatch** pour renvoyer les modifications à la source de données. Pour plus d’informations, consultez [mise à jour et persistance des données](../../../ado/guide/data/updating-and-persisting-data.md).  
  
 Il est généralement plus efficace d’utiliser une procédure stockée avec un objet de commande pour effectuer des mises à jour, ainsi que pour d’autres opérations, car une procédure stockée ne nécessite pas la création d’un curseur. Pour plus d’informations sur les curseurs, consultez [présentation des curseurs et des verrous](../../../ado/guide/data/understanding-cursors-and-locks.md).
