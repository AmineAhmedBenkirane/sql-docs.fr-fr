---
title: "Les propriétés de connexion avancées | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: change-data-capture
ms.reviewer: 
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4edfab68-7e68-45e8-a3f3-a0049ff7eb9e
caps.latest.revision: 8
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 856dce7d9b5c984407e7c03cee56013d22103fec
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---
# <a name="advanced-connection-properties"></a>Propriétés avancées de connexion
  Pour ajouter des paramètres de connexion à la chaîne de connexion, utilisez la boîte de dialogue **Propriétés avancées de connexion** .  
  
 Les paramètres de connexion supplémentaires peuvent être des paramètres de connexion ODBC pris en charge par l'instance de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous utilisez.  
  
 Les paramètres ajoutés à partir de la boîte de dialogue **Propriétés avancées de connexion** sont ajoutés aux paramètres sélectionnés dans la boîte de dialogue **Connexion à SQL Server** .  
  
 La dernière instance de chaque paramètre fourni remplace toutes les instances précédentes du paramètre. Les paramètres ajoutés à partir de la boîte de dialogue **Paramètres de connexion avancés** suivent et remplacent les paramètres fournis dans la boîte de dialogue **Connexion SQL Server** . Par exemple, si la boîte de dialogue **Connexion SQL Server** spécifie SERVEUR1 en tant que Nom du serveur et si la page **Paramètres de connexion supplémentaires** indique ;SERVEUR=SERVEUR2, la connexion sera établie à SERVEUR2.  
  
 Les paramètres ajoutés à partir de la boîte de dialogue **Propriétés avancées de connexion** sont transmis sous forme de texte brut.  
  
> [!IMPORTANT]  
>  N'incluez pas les informations d'identification de connexion dans la boîte de dialogue **Propriétés avancées de connexion** . Ceux-ci ne seront pas chiffrés lorsqu'ils seront transmis sur le réseau.  
  
## <a name="see-also"></a>Voir aussi  
 [Accéder à la Console du Concepteur de capture de données modifiées](../../integration-services/change-data-capture/access-the-cdc-designer-console.md)   
 [Connexion SQL Server pour l’Instance de la création](../../integration-services/change-data-capture/sql-server-connection-for-instance-creation.md)  
  
  

