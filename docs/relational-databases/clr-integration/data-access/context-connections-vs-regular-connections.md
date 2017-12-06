---
title: "Vs régulières. Connexions contextuelles | Documents Microsoft"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: clr
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: a1dead02-be88-4b16-8cb2-db1284856764
caps.latest.revision: "13"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 6b15a8e2c830c0f8e367aa9b2efc60a6911ee25e
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="context-connections-vs-regular-connections"></a>Connexions de contexte Visual Studio. Connexions normales
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]Si vous vous connectez à un serveur distant, utilisez toujours des connexions normales plutôt que des connexions de contexte. Si vous devez vous connecter au même serveur sur lequel la procédure stockée ou la fonction est en cours d'exécution, utilisez la connexion contextuelle dans la majorité des cas. Ceci présente des avantages, notamment l'exécution dans le même espace de transaction et la non-obligation de s'authentifier à nouveau.  
  
 Qui plus est, le recours aux connexions contextuelles produit généralement de meilleures performances et garantit une utilisation plus réduite des ressources. La connexion contextuelle est une connexion in-process uniquement. Elle peut donc contacter « directement » le serveur en ignorant les couches transport et protocole réseau pour envoyer des instructions Transact-SQL et recevoir des résultats. Le processus d'authentification est également ignoré. La figure suivante illustre les composants principaux de la **SqlClient** gérés fournisseur, ainsi que comment les différents composants interagissent entre eux lorsque vous utilisez une connexion normale et lors de l’utilisation de la connexion de contexte.  
  
 ![Chemins de code d’un contexte et connexion normale. ] (../../../relational-databases/clr-integration/data-access/media/clrintdataaccess.gif "Chemins de code d’un contexte et connexion normale.")  
  
 La connexion contextuelle suit un chemin de code plus court et implique moins de composants. Vous pouvez donc vous attendre à des demandes et des résultats circulant vers et depuis le serveur plus rapidement qu'avec une connexion normale. Le temps d'exécution des requêtes sur le serveur est le même pour les connexions normales et contextuelles.  
  
 Dans certains cas, vous devrez peut-être ouvrir une connexion normale distincte sur le même serveur. Par exemple, il existe des restrictions d’utilisation de la connexion de contexte décrite dans [Restrictions sur les connexions normales et contextuelles](../../../relational-databases/clr-integration/data-access/context-connections-and-regular-connections-restrictions.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Connexion contextuelle](../../../relational-databases/clr-integration/data-access/context-connection.md)  
  
  