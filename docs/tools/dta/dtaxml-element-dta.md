---
title: "DTAXML, élément (DTA) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-non-specified
ms.service: 
ms.component: dta
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: XML
helpviewer_keywords: DTAXML element
ms.assetid: 3d9942ed-8a27-40db-a7c9-808984d914a2
caps.latest.revision: "18"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c75accc66ce70c6d5f8c022fe87ba9aeaa11bc1a
ms.sourcegitcommit: b2d8a2d95ffbb6f2f98692d7760cc5523151f99d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2017
---
# <a name="dtaxml-element-dta"></a>DTAXML, élément (Assistant Paramétrage de base de données)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]L’élément racine d’une base de données du moteur Assistant Paramétrage du fichier d’entrée ou de sortie, **DTAXML** contient tous les éléments qui décrivent une entrée de paramétrage et les sorties de paramétrage qui génère l’Assistant Paramétrage du moteur de base de données.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
<DTAXML   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
    xmlns="http://schemas.microsoft.com/sqlserver/2004/07/dta">  
    ...code removed here...  
</DTAXML>  
```  
  
## <a name="element-attributes"></a>Attributs des éléments  
  
|Attribut|Description|  
|---------------|-----------------|  
|**xmlns:xsi**|Obligatoire. Identifie l'espace de noms de l'instance du schéma XML. Les attributs de cet espace de noms servent à référencer le schéma qui est utilisé pour valider le fichier XML de l'Assistant Paramétrage du moteur de base de données.<br /><br /> Valeur obligatoire : [http://www.w3.org/2001/XMLSchema-instance](http://www.w3.org/2001/XMLSchema-instance)|  
|**xmlns**|Obligatoire. Identifie l'espace de noms de l'Assistant Paramétrage du moteur de base de données.<br /><br /> Si vous modifiez le fichier XML de l'Assistant Paramétrage du moteur de base de données à l'aide de l'éditeur XML dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cette valeur est utilisée par l'aide obtenue par la touche F1 et l'aide dynamique pour rechercher les rubriques de référence dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .<br /><br /> Valeur obligatoire :<br /><br /> [Database Engine Tuning Advisor XML Schema](http://go.microsoft.com/fwlink/?LinkId=43100) Namespace|  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|**Type de données et longueur**|Aucun.|  
|**Valeur par défaut**|Aucun.|  
|**Occurrence**|Obligatoire une fois par fichier XML de l'Assistant Paramétrage du moteur de base de données.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Éléments|  
|------------------|--------------|  
|**Élément parent**|Aucune|  
|**Éléments enfants**|[DTAInput, élément &#40;DTA&#41;](../../tools/dta/dtainput-element-dta.md)<br /><br /> **DTAOutput** , élément (consultez l’article [Database Engine Tuning Advisor XML schema](http://schemas.microsoft.com/sqlserver/) pour plus d’informations)|  
  
## <a name="remarks"></a>Notes  
 Pour plus d'informations sur les espaces de noms XML, consultez l'article [Namespaces in an XML Document](http://go.microsoft.com/fwlink/?LinkId=7341) dans la bibliothèque [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN.  
  
## <a name="example"></a>Exemple  
 Pour obtenir des exemples d’éléments **DTAXML** caractéristiques, consultez [Exemples de fichiers d’entrée XML &#40;DTA&#41;](../../tools/dta/xml-input-file-samples-dta.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md)   
 [Démarrer et utiliser l’Assistant Paramétrage du moteur de base de données](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)  
  
  
