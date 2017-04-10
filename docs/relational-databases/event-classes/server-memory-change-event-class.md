---
title: "Classe d&#39;&#233;v&#233;nements Server Memory Change | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Server Memory Change (classe d'événements)"
ms.assetid: c9836484-39c5-4a89-b080-3567783b6fff
caps.latest.revision: 29
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 29
---
# Classe d&#39;&#233;v&#233;nements Server Memory Change
  La classe d’événements **Server Memory Change** intervient quand l’utilisation de la mémoire de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a augmenté ou diminué, soit de 1 mégaoctet (Mo), soit de 5 % de la taille maximale de la mémoire du serveur, la plus élevée de ces deux valeurs étant retenue.  
  
## Colonnes de la classe d'événements Server Memory Change  
  
|Nom de la colonne de données|Type de données|Description|ID de la colonne|Oui|  
|----------------------|---------------|-----------------|---------------|---------|  
|**EventClass**|**int**|Type d’événement = 81.|27|Non|  
|**EventSequence**|**int**|Séquence d'un événement donné au sein de la demande.|51|Non|  
|**EventSubClass**|**int**|Type de sous-classe d'événements.<br /><br /> 1=Augmentation de la mémoire<br /><br /> 2=Diminution de la mémoire|21|Oui|  
|**IntegerData**|**int**|Nouvelle taille de la mémoire, en mégaoctets (Mo).|25|Oui|  
|**IsSystem**|**int**|Indique si l'événement s'est produit sur un processus système ou sur un processus utilisateur. 1 = système, 0 = utilisateur.|60|Oui|  
|**RequestID**|**int**|ID de la demande contenant l'instruction.|49|Oui|  
|**ServerName**|**nvarchar**|Nom de l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tracée.|26|Non|  
|**SessionLoginName**|**nvarchar**|Nom de connexion de l'utilisateur à l'origine de la session. Par exemple, si vous vous connectez à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] au moyen de Login1 et que vous exécutez une commande en tant que Login2, **SessionLoginName** affiche Login1 et **LoginName** affiche Login2. Cette colonne affiche à la fois les connexions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et Windows.|64|Oui|  
|**SPID**|**int**|ID de la session au cours de laquelle l'événement s'est produit.|12|Oui|  
|**StartTime**|**datetime**|Heure à laquelle a débuté l'événement, si elle est connue.|14|Oui|  
|**TransactionID**|**bigint**|ID affecté par le système à la transaction.|4|Oui|  
|**XactSequence**|**bigint**|Jeton qui décrit la transaction en cours.|50|Oui|  
  
## Voir aussi  
 [Événements étendus](../../relational-databases/extended-events/extended-events.md)   
 [sp_trace_setevent &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)   
 [Mémoire du serveur (option de configuration de serveur)](../../database-engine/configure-windows/server-memory-server-configuration-options.md)  
  
  