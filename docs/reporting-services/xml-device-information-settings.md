---
title: XML Device Information Settings | Documents Microsoft
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [Reporting Services], rendering
- device information settings [Reporting Services], PDF rendering
ms.assetid: a32e83fe-c10e-4ebd-8975-5be7dcc422e7
caps.latest.revision: 43
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 9a5af7c3ba8de8f3134e40850524ecfd397faebd
ms.contentlocale: fr-fr
ms.lasthandoff: 08/09/2017

---
# <a name="xml-device-information-settings"></a>Paramètres d'informations de périphérique XML
  Le tableau suivant répertorie les paramètres d'informations de périphérique qui permettent un rendu au format XML.  
  
|Paramètre|Valeurs|Détails|  
|-------------|------------|-------------|  
|**XSLT**|Chemin dans l’espace de noms du serveur de rapports d’un paramètre XSLT à appliquer au fichier XML, par exemple **/Transforms/myxslt**.|Le fichier xsl doit être une ressource publiée sur le serveur de rapports et vous devez y accéder par le biais d'un chemin d'accès de l'élément du serveur de rapports. La valeur de ce paramètre est appliquée après tout XSLT spécifié dans le rapport. Si le paramètre **XSLT** est appliqué, le paramètre **OmitSchema** est ignoré.|  
|**MIMEType**|Type MIME (Multipurpose Internet Mail Extensions) du fichier XML.||  
|**UseFormattedValues**|**true**<br /><br /> **false**|Indique s'il faut restituer la valeur mise en forme d'une zone de texte lors de la génération des données XML.<br /><br /> Une valeur false indique que la valeur sous-jacente de la zone de texte est utilisée.|  
|**Indented**|**true**<br /><br /> **false**|Indique s'il faut générer du code XML mis en retrait. La valeur par défaut **false** génère un code XML compressé sans mise en retrait.|  
|**OmitNamespace**|**true**<br /><br /> **false**|Indique s'il faut omettre l'espace de noms XML par défaut.<br /><br /> Si la valeur est True, le XML ne spécifie aucun espace de noms par défaut.<br /><br /> Si la valeur est False, le XML spécifie un espace de noms par défaut avec la valeur de la propriété DataSchema du rapport. La propriété DataSchema utilise par défaut le nom du rapport.<br /><br /> La valeur par défaut est**false**.|  
|**OmitSchema**|**true**<br /><br /> **false**|Indique s'il faut omettre l'emplacement du schéma XML par défaut. L'emplacement est l'attribut SchemaLocation.<br /><br /> La valeur par défaut d'OmitSchema dépend de la valeur d'OmitNamespace :<br /><br /> Si OmitNamespace = False, OmitSchema = **False** par défaut. L'utilisateur peut remplacer la valeur par défaut en attribuant la valeur True à OmitSchema.<br /><br /> If OmitNamespace = True, OmitSchema fonctionne comme **True** indépendamment de la valeur explicitement configurée pour OmitShema.|  
|**Encodage**|Nom IANA (Internet Assigned Numbers Authority) d'un encodage de caractères pris en charge par le .NET Framework.|La valeur par défaut est **UTF-8**. Les exemples d'autres valeurs incluent ASCII, UTF-7 et UTF-16.|  
|**FileExtension**|Extension de fichier à utiliser pour le fichier généré.||  
|**Schéma**|La valeur **true** indique qu’un schéma XML est restitué. La valeur par défaut est **false**.|Indique si la définition de schéma XML (XSD) est restituée ou si les données XML réelles sont restituées.|  
  
## <a name="see-also"></a>Voir aussi  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 [Passage de paramètres d’informations de périphérique aux Extensions de rendu](../reporting-services/report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md)   
 [Personnaliser les paramètres d’Extension de rendu dans RSReportServer.Config](../reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [Informations techniques de référence &#40; SSRS &#41;](../reporting-services/technical-reference-ssrs.md)  
  
  
