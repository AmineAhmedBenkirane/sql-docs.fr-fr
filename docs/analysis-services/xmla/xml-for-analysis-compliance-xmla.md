---
title: Conformité XML for Analysis (XMLA) | Documents Microsoft
ms.custom: ''
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- compliance [XML for Analysis]
- XML for Analysis, compliance
- XMLA, extended functionality
- XML for Analysis, extended functionality
- XMLA, compliance
- extending XML for Analysis
ms.assetid: d987d320-5581-4454-ad45-68e3a22175b6
caps.latest.revision: 15
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b801e87576ae4ecf47f6ed828d35eac06c44a94d
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="xml-for-analysis-compliance-xmla"></a>Conformité XML for Analysis (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
  La spécification XML for Analysis 1.1 décrit une norme ouverte qui prend en charge l'accès aux sources de données qui résident sur Internet. Cette rubrique détaille le niveau de compatibilité avec la spécification XML for Analysis 1.1 est pris en charge par [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
## <a name="compliant-items"></a>Éléments conformes  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] est conforme avec tous les éléments obligatoires répertoriés dans la spécification XML for Analysis 1.1. Qui plus est, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] implémente l'élément facultatif suivant décrit dans la spécification XML for Analysis 1.1.  
  
|Élément|Spécification|Implémentation|  
|----------|-------------------|--------------------|  
|Prise en charge de la session|Les éléments d'en-tête SOAP répertoriés dans la section relative à la prise en charge de l'état dans XML for Analysis pour la spécification XML for Analysis 1.1.|Tous les éléments d'en-tête SOAP répertoriés sont pris en charge par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], tel que décrit dans la spécification.|  
  
## <a name="extensions"></a>Extensions  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] permet également d'étendre la spécification XML for Analysis 1.1 afin de prendre en charge les fonctionnalités et les outils supplémentaires suivants.  
  
|Élément|Spécification|Implémentation|  
|----------|-------------------|--------------------|  
|Négociation de protocole|Aucune information contenue dans la spécification XML for Analysis 1.1|Élément d’en-tête ProtocolCapabilities ajouté par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour prendre en charge la négociation des fonctionnalités de protocole.|  
|Commandes XML for Analysis (XMLA) prises en charge par la méthode Discover|Les commandes suivantes sont prises en charge par la spécification XML for Analysis 1.1 :<br /><br /> [Élément d’instruction &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/statement-element-xmla.md)|Les commandes suivantes sont prises en charge par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] :<br /><br /> [Élément ALTER &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/alter-element-xmla.md)<br /><br /> [Élément de sauvegarde &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/backup-element-xmla.md)<br /><br /> [Élément du lot &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/batch-element-xmla.md)<br /><br /> [Élément BeginTransaction &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/begintransaction-element-xmla.md)<br /><br /> [Élément Cancel &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/cancel-element-xmla.md)<br /><br /> [Élément ClearCache &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/clearcache-element-xmla.md)<br /><br /> [Élément CommitTransaction &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/committransaction-element-xmla.md)<br /><br /> [Créer l’élément &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/create-element-xmla.md)<br /><br /> [Supprimer l’élément &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/delete-element-xmla.md)<br /><br /> [Élément DesignAggregations &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/designaggregations-element-xmla.md)<br /><br /> [Élément DROP &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/drop-element-xmla.md)<br /><br /> [Insérer l’élément &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md)<br /><br /> [Verrouiller l’élément &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/lock-element-xmla.md)<br /><br /> [Élément MergePartitions &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/mergepartitions-element-xmla.md)<br /><br /> [Élément NotifyTableChange &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/notifytablechange-element-xmla.md)<br /><br /> [Traiter l’élément &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md)<br /><br /> [Élément Restore &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/restore-element-xmla.md)<br /><br /> [Élément RollbackTransaction &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/rollbacktransaction-element-xmla.md)<br /><br /> [Élément d’instruction &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/statement-element-xmla.md)<br /><br /> [Élément Subscribe &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/subscribe-element-xmla.md)<br /><br /> [Synchroniser, élément & #40 ; XMLA & #41 ;](../../analysis-services/xmla/xml-elements-commands/synchronize-element-xmla.md)<br /><br /> [Élément Unlock &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/unlock-element-xmla.md)<br /><br /> [Mettre à jour d’élément &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/update-element-xmla.md)<br /><br /> [Élément UpdateCells &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/updatecells-element-xmla.md)|  
|Erreurs de colonne dans les ensembles de lignes tabulaires|Non répertoriées dans la spécification XML for Analysis 1.1.|Le [erreur](../../analysis-services/xmla/xml-elements-properties/error-element-xmla.md) élément est utilisé par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour signaler des erreurs pour les éléments de colonne contenus dans un [ligne](../../analysis-services/xmla/xml-elements-properties/error-element-xmla.md) élément.|  
  
## <a name="see-also"></a>Voir aussi  
 [XML for Analysis & #40 ; XMLA & #41 ; Référence](../../analysis-services/xmla/xml-for-analysis-xmla-reference.md)  
  
  
