---
title: "L’inscription d’un objet métier personnalisé | Documents Microsoft"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom business object in RDS [ADO]
- registering custom business objects in RDS [ADO]
- business objects in RDS [ADO]
ms.assetid: e9032ad8-d14c-42e3-ba13-cb5f00084a79
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1b95345c2c3818330bf442b56671192d9a47cad6
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2018
---
# <a name="registering-a-custom-business-object"></a>L’inscription d’un objet métier personnalisé
Pour permettre l’exécution d’un objet métier personnalisé (.dll ou .exe) via le serveur Web, le ProgID de l’objet métier doit être entrée dans le Registre comme indiqué dans cette procédure. Cette fonctionnalité RDS protège la sécurité de votre serveur Web en cours d’exécution que les exécutables approuvés.  
  
> [!IMPORTANT]
>  À compter de Windows 8 et Windows Server 2012, les composants de serveur Services Bureau à distance ne sont plus inclus dans le système d’exploitation Windows (consultez Windows 8 et [Cookbook de compatibilité de Windows Server 2012](https://www.microsoft.com/en-us/download/details.aspx?id=27416) pour plus de détails). Composants du client Bureau à distance seront supprimées dans une future version de Windows. Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité. La migration vers les applications qui utilisent des services Bureau à distance [Service de données WCF](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
> [!NOTE]
>  Pour MDAC 2.0 et versions ultérieures et Windows DAC, l’objet métier par défaut, [RDSServer.DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md), n’est pas enregistré par défaut lors de l’installation de MDAC/Windows DAC. Toutefois, si **RDSServer.DataFactory** a été enregistré comme sécurisés pour l’exécution sur l’ordinateur avant l’installation, l’entrée de Registre est conservée pour la nouvelle installation.  
  
### <a name="to-register-a-custom-business-object"></a>Pour enregistrer un objet métier personnalisé :  
  
1.  Cliquez sur **Démarrer** puis cliquez sur **exécuter**.  
  
2.  Type **RegEdit** et cliquez sur **OK**.  
  
3.  Dans l’Éditeur du Registre, accédez à la **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\W3SVC\Parameters\ADCLaunch** clé de Registre.  
  
4.  Sélectionnez le **ADCLaunch** clé, puis dans le **modifier**menu, pointez sur **nouveau** et cliquez sur **clé**.  
  
5.  Tapez l’identificateur ProgID de votre objet métier personnalisé, cliquez sur **entrée**. Laissez le **valeur** entrée vide.


