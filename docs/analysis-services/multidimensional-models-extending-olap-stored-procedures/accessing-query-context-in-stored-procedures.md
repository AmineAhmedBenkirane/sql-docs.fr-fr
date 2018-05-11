---
title: Accès au contexte de requête dans des procédures stockées | Documents Microsoft
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.component: olap
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 13facbc44747bedc6f28e1ff4d3bda81b60004ad
ms.sourcegitcommit: 38f8824abb6760a9dc6953f10a6c91f97fa48432
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2018
---
# <a name="accessing-query-context-in-stored-procedures"></a>Accès au contexte de requête dans les procédures stockées
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  Le contexte d’exécution d’une procédure stockée est disponible dans le code de la procédure stockée en tant que le **contexte** objet du modèle d’objet serveur ADOMD.NET. Il s'agit d'un contexte en lecture seule qui ne peut pas être modifié par la procédure stockée. Les propriétés suivantes sont disponibles pour cet objet.  
  
|Propriété|Type| Description|  
|--------------|----------|-----------------|  
|**CurrentCube**|Cube|Cube du contexte de requête actuel.|  
|**CurrentDatabaseName**|Chaîne|Identificateur de la base de données active.|  
|**CurrentConnection**|Connexion|Référence à l'objet de connexion dans le contexte actuel.|  
|**Passer**|Entier|Numéro de test du contexte actuel.|  
  
 Le **contexte** objet existe lorsque le modèle objet MDX (Multidimensional Expressions) est utilisé dans une procédure stockée. Il n'est pas disponible lorsque le modèle objet MDX est utilisé sur un client. Le **contexte** objet n’est pas explicitement passée à ou retournée par la procédure stockée. Il est disponible pendant l'exécution de la procédure stockée.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion des assemblys de modèle multidimensionnel](../../analysis-services/multidimensional-models/multidimensional-model-assemblies-management.md)   
 [Définition de procédures stockées](../../analysis-services/multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
