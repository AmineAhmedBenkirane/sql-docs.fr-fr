---
title: remote admin connections (option de configuration de serveur) | Microsoft Docs
ms.custom: 
ms.date: 03/02/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- administrator connections [SQL Server]
- DAC
- connections [SQL Server], dedicated administrator
- remote admin connections option
- dedicated administrator connections [SQL Server]
ms.assetid: bf32b60a-7a48-401f-b6be-b5e2e46c413f
caps.latest.revision: 15
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: On Demand
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 9cfa41a838ebb89777b44464ec2b2a48b256c3f9
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="remote-admin-connections-server-configuration-option"></a>remote admin connections (option de configuration de serveur)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournit une connexion administrateur dédiée. Celle-ci permet à un administrateur d’accéder à un serveur actif pour exécuter des fonctions de diagnostic ou des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] ou pour résoudre des problèmes sur ce serveur, même s’il est verrouillé, que son état est anormal ou qu’il ne répond pas à une connexion du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] . Par défaut, cette connexion n'est disponible qu'à partir d'un client sur le serveur. Pour autoriser des applications clientes sur des ordinateurs distants à utiliser la connexion administrateur dédiée, utilisez l'option remote admin connections de sp_configure.  
  
 Par défaut, la connexion administrateur dédiée n'écoute que sur l'adresse IP (127.0.0.1), port 1434. Si le port TCP 1434 n’est pas disponible, un port TCP est affecté dynamiquement lors du démarrage du [!INCLUDE[ssDE](../../includes/ssde-md.md)] . Lorsque plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont installées sur un ordinateur, consultez le journal des erreurs afin de connaître le numéro de port TCP.  
  
 Le tableau suivant répertorie les valeurs possibles de l'option remote admin connections.  
  
|Valeur|Description|  
|-----------|-----------------|  
|0|Indique que seules les connexions locales sont autorisées à utiliser la connexion administrateur dédiée.|  
|1|Indique que les connexions à distance sont autorisées à utiliser la connexion administrateur dédiée.|  
  
## <a name="example"></a>Exemple  
 L'exemple suivant active la connexion administrateur dédiée à partir d'un ordinateur distant.  
  
```  
sp_configure 'remote admin connections', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Connexion de diagnostic pour les administrateurs de base de données](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md)  
  
  

