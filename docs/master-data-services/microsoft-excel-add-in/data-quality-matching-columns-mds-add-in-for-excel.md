---
title: "Colonnes de mise en correspondance de la qualité des données (Complément MDS pour Excel) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology: master-data-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f683fdc6-0d4c-4793-8143-567616cb2094
caps.latest.revision: "9"
author: smartysanthosh
ms.author: nagavo
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 05ea85ea22f8d780e53f2fbf05cdecd8629b32b4
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="data-quality-matching-columns-mds-add-in-for-excel"></a>Colonnes de mise en correspondance de la qualité des données (Complément MDS pour Excel)
  Dans [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], après avoir mis les données en correspondance, dans le groupe **Qualité des données** du ruban, vous pouvez cliquer sur **Afficher les détails** pour afficher les colonnes qui fournissent des détails sur les correspondances.  
  
 Le tableau suivant présente les colonnes affichées lors de la mise en correspondance des données.  
  
|Nom|Description|  
|----------|-----------------|  
|**CLUSTER_ID**|Identificateur unique utilisé pour regrouper les enregistrements similaires. Toutes les lignes similaires ont le même **CLUSTER_ID**. Si aucun **CLUSTER_ID** n’est affiché pour une ligne, aucun enregistrement similaire n’a été trouvé.|  
|**RECORD_ID**|Identificateur unique utilisé pour identifier les enregistrements. Similaire à la valeur Code stockée dans le référentiel MDS, il s'agit d'une valeur utilisée pour identifier un enregistrement. Il est généré automatiquement chaque fois que la mise en correspondance a lieu.|  
|**PIVOT_MARK**|Enregistrement arbitraire auxquels les autres enregistrements sont comparés ; il n'a pas de valeur de score.|  
|**SCORE**|Représente le degré de similitude des enregistrements du groupe par rapport à l'enregistrement pivot. Ce score est déterminé par DQS. Si aucun score n'est affiché, l'enregistrement est le tableau croisé dynamique d'autres enregistrements, ou bien aucune correspondance n'a été trouvée.|  
  
## <a name="see-also"></a>Voir aussi  
 [Mise en correspondance de la qualité des données dans le complément MDS pour Excel](../../master-data-services/microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md)   
 [Mettre en correspondance les données similaires &#40;Complément MDS pour Excel&#41;](../../master-data-services/microsoft-excel-add-in/match-similar-data-mds-add-in-for-excel.md)   
 [Correspondance de données](../../data-quality-services/data-matching.md)  
  
  
