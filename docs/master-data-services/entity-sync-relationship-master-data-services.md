---
title: "Relation de synchronisation d’entités (Master Data Services) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd627a2d-dc64-47e9-9a71-2d0ad04b4962
caps.latest.revision: 6
author: smartysanthosh
ms.author: nagavo
manager: craigg
ms.translationtype: HT
ms.sourcegitcommit: 0b832a9306244210e693bde7c476269455e9b6d8
ms.openlocfilehash: 9abf874d3e813639f16e36b1ccc92cf178996f3a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/07/2017

---
# <a name="entity-sync-relationship-master-data-services"></a>Relation de synchronisation d’entités (Master Data Services)
  La synchronisation d’entités est une synchronisation unidirectionnelle et reproductible entre des versions d’entités. Elle vous permet de partager des données d’entités entre différents modèles. Vous pouvez conserver une seule source fiable dans un modèle et réutiliser ces données de référence dans d’autres modèles. Par exemple, vous pouvez stocker des données américaines dans une entité de modèle et réutiliser ces données dans d’autres modèles.  
  
 Avec la synchronisation d’entités, vous pouvez aussi copier les données en une seule fois.  
  
 Tous les membres feuille avec attributs de forme libre et attributs de fichier dans l’entité source sont synchronisés avec l’entité cible lors de l’exécution de la synchronisation. Cette opération crée, supprime et modifie le schéma de l’entité ainsi que les membres.  
  
 Dès qu’une relation de synchronisation a été établie, l’entité cible ne peut être modifiée que par synchronisation. Une relation de synchronisation peut être supprimée à tout moment pour permettre la modification de l’entité cible.  
  
## <a name="see-also"></a>Voir aussi  
 [Créer et exécuter une relation de synchronisation d’entités &#40;Master Data Services&#41;](../master-data-services/create-and-execute-an-entity-sync-relationship-master-data-services.md)   
 [Modifier et supprimer une relation de synchronisation d’entités &#40;Master Data Services&#41;](../master-data-services/edit-and-delete-an-entity-sync-relationship-master-data-services.md)  
  
  
