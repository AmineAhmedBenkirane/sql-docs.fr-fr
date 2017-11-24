---
title: "Outil de gestion de ligne de commande : SqlLocalDB.exe | Documents Microsoft"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: localdb
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apilocation: sqluserinstance.dll
ms.assetid: dd0882b1-a8a9-447a-8bdf-0f9d7f36d336
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 8f2bac1f105f5d299fa97d11fa579226026134aa
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="command-line-management-tool-sqllocaldbexe"></a>Outil de gestion en ligne de commande : SqlLocalDB.exe
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]SqlLocalDB.exe est un outil simple qui permet à l’utilisateur de gérer facilement les instances de base de données locale à partir de la ligne de commande. Il est implémenté comme wrapper simple autour de l'API de l'instance de LocalDB. Comme dans de nombreux outils similaires SQL Server (par exemple, SQLCMD), les paramètres sont passés à SqlLocalDB comme arguments de ligne de commande et la sortie est envoyée à la console.  
  
 SqlLocalDB permet aux développeurs d'utiliser LocalDB sans devoir écrire du code pour appeler l'API ou dépendre d'autres d'outils pour l'exécuter pour eux.  
  
## <a name="sqllocaldb-options"></a>Options de SqlLocalDB  
 SqlLocalDB prend en charge les options suivantes.  
  
|Option|Ce qu’il fait|  
|------------|------------------|  
|`-?`|Affiche le texte d'aide.|  
|' create\|c « nom de l’instance » [numéro de version] [-s]'|Crée une nouvelle instance de LocalDB avec un nom et une version spécifiés.<br /><br /> Si le paramètre [numéro-version] est omis, il prend par défaut la valeur de la version de la build de SqlLocalDB.<br /><br /> -s démarre la nouvelle instance de LocalDB après sa création.|  
|' delete\|d « nom de l’instance » »|Supprime l'instance de LocalDB portant le nom spécifié.|  
|« Start|s « nom de l’instance » »|Démarre l'instance de LocalDB portant le nom spécifié.|  
|« Stop|p « nom de l’instance » [-i\|-k]'|Arrête l'instance de LocalDB portant le nom spécifié, une fois les requêtes actuelles terminées.<br /><br /> -i demande l'arrêt de l'instance de LocalDB avec l'option NOWAIT.<br /><br /> -k met fin au processus de l'instance de LocalDB sans le contacter.|  
|' share\|h [« SID propriétaire ou compte »] « nom privé » « nom partagé » »|Partage l'instance privée spécifiée à l'aide du nom partagé spécifié. Si le SID ou le nom de compte de l'utilisateur est omis, il prend par défaut la valeur de l'utilisateur actuel.|  
|' unshare\|u « nom partagé » »|Annule le partage de l'instance de LocalDB partagée spécifiée.|  
|' info\|i'|Répertorie toutes les instances existantes de LocalDB détenues par l'utilisateur actuel et toutes les instances partagées de LocalDB.|  
|' info\|i « nom de l’instance » »|Affiche des informations relatives à l'instance de LocalDB spécifiée.|  
|' versions\|v'|Répertorie toutes les versions de LocalDB installées sur l'ordinateur.|  
|||  
|' trace\|t on\|OFF'|Active et désactive le traçage.|  
  
 SqlLocalDB traite les espaces comme des délimiteurs ; vous devez donc placer les noms d'instances contenant des espaces et des caractères spéciaux entre guillemets. Par exemple :  
  
 `SqlLocalDB create "My instance name with spaces"`  
  
  
