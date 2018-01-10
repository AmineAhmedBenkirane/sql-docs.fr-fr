---
title: "Suppression d’une extension de remise | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.service: 
ms.component: extensions
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
helpviewer_keywords:
- removing delivery extensions
- deleting delivery extensions
- delivery extensions [Reporting Services], removing
ms.assetid: dcb7caf2-d19a-4bc5-afb3-2b61ad11cac5
caps.latest.revision: "31"
author: markingmyname
ms.author: maghan
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 659c572c6f9a2b013e3ae3f182418bacc0f89b50
ms.sourcegitcommit: 7e117bca721d008ab106bbfede72f649d3634993
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2018
---
# <a name="removing-a-delivery-extension"></a>Suppression d'une extension de remise
  Pour supprimer une extension de remise [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], supprimez simplement l’élément **Extension** de votre extension de remise du fichier de configuration. Une fois les informations de configuration supprimées, l'extension de remise n'est plus disponible pour le serveur de rapports.  
  
 Une fois que l’élément **Extension** correspondant d’une extension de remise est supprimé du fichier de configuration, il n’est plus inscrit auprès du serveur de rapports. Le serveur de rapports supprime l'entrée dans la liste d'extensions de remise et désactive tous les abonnements qui utilisent cette extension de remise. Lorsqu'une extension de remise est supprimée, les utilisateurs ne sont plus en mesure de le sélectionner comme méthode de notification.  
  
## <a name="see-also"></a> Voir aussi  
 [Implémentation d’une extension de remise](../../../reporting-services/extensions/delivery-extension/implementing-a-delivery-extension.md)   
 [Bibliothèque d'extensions Reporting Services](../../../reporting-services/extensions/reporting-services-extension-library.md)  
  
  
