---
title: "Propriétés de Configuration SQL Server Native Client (onglet indicateurs) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59af121d-c8b9-4faa-91a1-b664f2c9b441
caps.latest.revision: "17"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: f239242a1b5aaace84fbde3eaa87797df7193590
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="sql-server-native-client-configuration-properties-flags-tab"></a>Propriétés de la configuration de SQL Server Native Client (onglet Indicateurs)
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installés sur cet ordinateur communiquent avec les serveurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant les protocoles fournis dans le fichier de bibliothèque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client. Cette page permet de configurer l'ordinateur client de manière à ce qu'il demande une connexion chiffrée utilisant le protocole SSL (Secure Sockets Layer). En cas d'impossibilité d'établir une connexion chiffrée, la connexion échoue.  
  
 Le processus de connexion est toujours chiffré. Les options ci-dessous s'appliquent uniquement aux données de chiffrement. Pour plus d’informations sur la manière dont [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] chiffre les communications et pour obtenir des instructions sur la manière de configurer le client pour qu’il approuve l’autorité racine du certificat du serveur, consultez « Chiffrement des connexions à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]» et « Activer les connexions chiffrées dans le [!INCLUDE[ssDE](../../includes/ssde-md.md)] (Gestionnaire de configuration[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ) » dans la documentation en ligne [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="options"></a>Options  
 **Forcer le chiffrement du protocole**  
 Demande une connexion utilisant le protocole SSL.  
  
 **Faire confiance au certificat de serveur**  
 Quand cette option a la valeur **Non**, le processus client tente de valider le certificat du serveur. Le client et le serveur doivent tous les deux posséder un certificat émanant d'une autorité de certification publique. Si le certificat n'est pas présent sur l'ordinateur client ou que la validation du certificat échoue, la connexion prend fin.  
  
 Quand l’option a la valeur **Oui**, le client ne valide pas le certificat du serveur, ce qui permet d’utiliser un certificat autosigné.  
  
 **Faire confiance au certificat de serveur** n’est disponible que si l’option **Forcer le chiffrement du protocole** a la valeur **Oui**.  
  
  
