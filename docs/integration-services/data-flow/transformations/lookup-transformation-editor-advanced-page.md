---
title: "Éditeur de Transformation de recherche (Page avancé) | Documents Microsoft"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.dts.designer.lookuptransformation.advanced.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: f3395c65-0320-47f9-8d83-daaa082d8713
caps.latest.revision: 42
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 13b342d7db5106451f7355c7dd1672181443f18d
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---
# <a name="lookup-transformation-editor-advanced-page"></a>Éditeur de transformation de recherche (page Avancé)
  La page **Avancé** de la boîte de dialogue **Éditeur de transformation de recherche** permet de configurer la mise en cache partielle et de modifier l’instruction SQL pour la transformation de recherche.  
  
 Pour en savoir plus sur la transformation de recherche, consultez [Lookup Transformation](../../../integration-services/data-flow/transformations/lookup-transformation.md).  
  
## <a name="options"></a>Options  
 **Taille du cache (32 bits)**  
 Ajustez la taille du cache (en mégaoctets) pour les ordinateurs 32 bits. La valeur par défaut est 5 mégaoctets.  
  
 **Taille du cache (64 bits)**  
 Ajustez la taille du cache (en mégaoctets) pour les ordinateurs 64 bits. La valeur par défaut est 5 mégaoctets.  
  
 **Activer le cache pour les lignes sans entrées correspondantes**  
 Mettez en cache les lignes sans entrées correspondantes dans le dataset de référence.  
  
 **Allocation à partir du cache**  
 Spécifiez le pourcentage de cache à allouer aux lignes sans entrées correspondantes dans le dataset de référence.  
  
 **Modifier l'instruction SQL**  
 Modifiez l'instruction SQL utilisée pour générer le dataset de référence.  
  
> [!NOTE]  
>  L’instruction SQL facultative que vous spécifiez dans cette page substitue et remplace le nom de table que vous avez spécifié dans la page **Connexion** de **l’Éditeur de transformation de recherche**. Pour plus d’informations, consultez [Éditeur de transformation de recherche &#40;page Connexion&#41;](../../../integration-services/data-flow/transformations/lookup-transformation-editor-connection-page.md).  
  
 **Définition des paramètres**  
 Mappez les colonnes d’entrée aux paramètres en utilisant la boîte de dialogue **Définition des paramètres de la requête** .  
  
## <a name="external-resources"></a>Ressources externes  
 Entrée de blog, [Lookup cache modes](http://go.microsoft.com/fwlink/?LinkId=219518) sur blogs.msdn.com  
  
## <a name="see-also"></a>Voir aussi  
 [Éditeur de Transformation de recherche &#40; Page Général &#41;](../../../integration-services/data-flow/transformations/lookup-transformation-editor-general-page.md)   
 [Éditeur de Transformation de recherche &#40; Page de connexion &#41;](../../../integration-services/data-flow/transformations/lookup-transformation-editor-connection-page.md)   
 [Éditeur de Transformation de recherche &#40; Page colonnes &#41;](../../../integration-services/data-flow/transformations/lookup-transformation-editor-columns-page.md)   
 [Éditeur de Transformation de recherche &#40; Page sortie d’erreur &#41;](../../../integration-services/data-flow/transformations/lookup-transformation-editor-error-output-page.md)   
 [Integration Services Error and Message Reference](../../../integration-services/integration-services-error-and-message-reference.md)   
 [Transformation de recherche floue](../../../integration-services/data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
