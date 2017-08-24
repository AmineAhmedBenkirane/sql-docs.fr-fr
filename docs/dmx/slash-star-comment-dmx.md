---
title: "Barre oblique étoile (commentaire) (DMX) | Documents Microsoft"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- DMX
helpviewer_keywords:
- commenting characters
- forward slash-asterisk character pairs
- /*...*/ (comment)
ms.assetid: 163976cc-aa47-4eda-bd98-03c1a397f80e
caps.latest.revision: 15
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 5bfaadd08f5a9aba145c754f281cf1d2c8e38496
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="slash-star-comment-dmx"></a>Barre oblique étoile (commentaire) (DMX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Indique une chaîne de texte que [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ne doit pas exécuter. Le serveur n’évalue pas le texte entre les caractères de commentaire / * et \*/. Vous pouvez imbriquer les commentaires dans une instruction DMX (Data Mining Extensions), les ajouter à la fin d'une ligne de code ou les insérer sur une ligne séparée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
/* Comment_Text */  
```  
  
#### <a name="parameters"></a>Paramètres  
 *Comment_Text*  
 Chaîne contenant le texte du commentaire.  
  
## <a name="remarks"></a>Notes  
 Commentaires de plusieurs lignes doivent être signalés par / * et \*/.  
  
 Il n'y a pas de longueur maximale pour les commentaires.  
  
 Pour plus d’informations sur l’utilisation de différents types de commentaires dans DMX, consultez [commentaires &#40; DMX &#41;](../dmx/comments-dmx.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Double barre oblique &#40; Commentaire &#41; &#40; DMX &#41;](../dmx/double-slash-comment-dmx.md)   
 [--&#40; Commentaire &#41; &#40; DMX &#41; Résumé](../dmx/comment-dmx-summary.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence des opérateurs](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Opérateurs &#40; DMX &#41;](../dmx/operators-dmx.md)  
  
  

