---
title: MSSQLSERVER_33129 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: errors-events
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 33129 (Database Engine error)
ms.assetid: 83b5f368-f1a1-4a40-9bb6-c77e2dec690f
caps.latest.revision: 7
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 95d1624e61280fe8d7072a9410379f915121ab97
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="mssqlserver33129"></a>MSSQLSERVER_33129
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|33129|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|SEC_CANNOT_DISABLE_WIN_GROUP|  
|Texte du message|Impossible d'utiliser ALTER_LOGIN avec l'argument DISABLE pour refuser l'accès à un groupe Windows.|  
  
## <a name="explanation"></a>Explication  
Ce message est généré lors d'une tentative de désactivation de la connexion d'un groupe Windows.  
  
## <a name="user-action"></a>Action de l'utilisateur  
La connexion d'un groupe Windows ne peut pas être désactivée. Pour supprimer temporairement l'autorisation d'accès accordée à un groupe Windows, révoquez avec REVOKE l'autorisation CONNECT de la connexion du groupe Windows. Les utilisateurs Windows peuvent encore bénéficier d'un accès par leur connexion individuelle ou via un autre groupe Windows. L'exemple suivant révoque l'autorisation de connexion au groupe de comptabilité Accounting du domaine WESTCOAST.  
  
```Transact-SQL  
REVOKE CONNECT TO [WESTCOAST\Accounting];  
```  
  
