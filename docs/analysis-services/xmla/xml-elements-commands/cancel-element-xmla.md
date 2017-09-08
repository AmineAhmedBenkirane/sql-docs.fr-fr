---
title: "Élément Cancel (XMLA) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Cancel Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- microsoft.xml.analysis.cancel
- http://schemas.microsoft.com/analysisservices/2003/engine#Cancel
- urn:schemas-microsoft-com:xml-analysis#Cancel
helpviewer_keywords:
- Cancel command
ms.assetid: de4062c1-7434-44dc-9f01-29fcf78963bd
caps.latest.revision: 15
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a12372d43b20395e878e305b036fe5a63f399d2b
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="cancel-element-xmla"></a>Élément Cancel (XMLA)
  Annule une commande en cours d’exécution un [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Command>  
   <Cancel>  
      <ConnectionID>...</ConnectionID>  
      <SessionID>...</SessionID>  
      <SPID>...</SPID>  
      <CancelAssociated>...</CancelAssociated>  
   </Cancel>  
</Command>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Aucune|  
|Valeur par défaut|Aucune|  
|Cardinalité|0-n : élément facultatif pouvant apparaître plusieurs fois.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Command](../../../analysis-services/xmla/xml-elements-properties/command-element-xmla.md)|  
|Éléments enfants|[CancelAssociated](../../../analysis-services/xmla/xml-elements-properties/cancelassociated-element-xmla.md), [ConnectionID](../../../analysis-services/xmla/xml-elements-properties/connectionid-element-xmla.md), [SessionID](../../../analysis-services/xmla/xml-elements-properties/sessionid-element-xmla.md), [SPID](../../../analysis-services/xmla/xml-elements-properties/spid-element-xmla.md)|  
  
## <a name="remarks"></a>Notes  
 La commande **Cancel** annule les commandes en cours d'exécution dans le contexte d'une session. Si l'application cliente n'a demandé aucune session, une commande ne peut être annulée.  
  
 Si l'exécution de la commande **Cancel** a lieu pendant celle d'une commande **Batch** , la commande **Batch** tout entière est annulée. Si la commande **Batch** était transactionnelle, toutes les commandes que contient la commande **Batch** sont restaurées. Si la commande **Batch** n'était pas transactionnelle, seules les commandes figurant dans la commande **Batch** et exécutées au moment de l'exécution de la commande **Cancel** sont restaurées. Les commandes incluses dans une commande **Batch** non transactionnelle et qui ont déjà été exécutées ne sont pas restaurées.  
  
 En règle générale, la commande **Cancel** est utilisée pour annuler l'exécution des commandes dans la session active. Dans ce cas, aucun des éléments enfants de la commande **Cancel** ne doit être spécifié. Les administrateurs peuvent également faire appel à la commande **Cancel** pour annuler des commandes exécutées sur des connexions ou des sessions autres que la session active. Les membres d'un rôle qui bénéficie d'autorisations d'administration pour une base de données spécifique peuvent annuler des commandes pour des connexions et des sessions applicables à cette base de données, tandis que les administrateurs de serveur peuvent annuler des commandes pour les connexions et les sessions d'une instance Analysis Services donnée.  
  
 Pour récupérer des informations sur les connexions en cours et les sessions d’un [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance, le **Discover** méthode peut être exécutée pour demander, respectivement, les ensembles de lignes de schéma DISCOVER_CONNECTIONS et DISCOVER_SESSIONS. Les membres d'un rôle qui bénéficie d'autorisations d'administration pour une base de données spécifique peuvent retourner des sessions uniquement pour une base de données donnée en précisant cette base de données dans la colonne de restriction SESSION_CURRENT_DATABASE pour l'ensemble de lignes de schéma DISCOVER_SESSIONS. Pour plus d’informations sur la **Discover** méthode, consultez [découvrir la méthode &#40; XMLA &#41; ](../../../analysis-services/xmla/xml-elements-methods-discover.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Élément de lot &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/batch-element-xmla.md)   
 [Commandes &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/xml-elements-commands.md)  
  
  
