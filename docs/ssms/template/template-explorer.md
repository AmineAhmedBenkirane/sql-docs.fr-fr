---
title: "Explorateur de modèles | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.templates.explorer.f1
- sql13.wb.templates.f1
helpviewer_keywords:
- templates [SQL Server]
- SQL Server Management Studio [SQL Server], Template Explorer
- Template Explorer
- templates [Transact-SQL]
- templates [SQL Server], Template Explorer
ms.assetid: b9ee55c5-bb44-4f76-90ac-792d8d83b4c8
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: e0d0525a7da87f0c2f2363d641fcb07bcd5262ad
ms.lasthandoff: 04/11/2017

---
# <a name="template-explorer"></a>Explorateur de modèles
[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] propose divers modèles. Les modèles sont des fichiers réutilisables contenant des scripts SQL qui peuvent vous aider à créer des objets dans une base de données. À la première ouverture de l’Explorateur de modèles, une copie des modèles est placée dans le dossier de l’utilisateur dans C:\Utilisateur, sous AppData\Roaming\Microsoft\SQL Server Management Studio\130\Templates.  
  
Vous pouvez parcourir les modèles disponibles dans l'Explorateur de modèles, puis ouvrir un modèle pour incorporer code dans une fenêtre d'éditeur de code. Vous pouvez également créer des modèles personnalisés.  
  
## <a name="benefits-of-templates"></a>Avantages des modèles  
Les modèles peuvent être utilisés pour les solutions, les projets et différents types d'éditeurs de code. Certains modèles sont destinés à la création d’objets tels que des bases de données, des tables, des vues, des index, des procédures stockées, des déclencheurs, des statistiques et des fonctions. D'autres modèles sont conçus pour simplifier la gestion de votre serveur en créant des propriétés étendues, des serveurs liés, des noms d'accès, des rôles et des utilisateurs. Il existe en outre certains modèles destinés à [!INCLUDE[ssASnoversion](../../includes/ssasnoversion_md.md)].  
  
Les modèles de scripts fournis avec [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] contiennent des paramètres qui permettent de personnaliser le code. Quand vous ouvrez un modèle, utilisez la boîte de dialogue **Remplacer les paramètres de modèle** pour insérer des valeurs dans le script.  
  
Créez des modèles personnalisés pour les tâches que vous effectuez fréquemment. Organisez les scripts personnalisés dans les dossiers existants ou créez une structure de dossiers.  
  
L'Éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde_md.md)] prend également en charge les extraits de code, que vous pouvez insérer à des emplacements spécifiques dans un script en cliquant avec le bouton droit à cet emplacement.  
  
## <a name="related-tasks"></a>Tâches associées  
Utiliser les rubriques suivantes pour commencer à utiliser les modèles  
  
|**Description**|**Rubrique**|  
|-------------------|-------------|  
|Explique comment incorporer le code d'un modèle dans une fenêtre d'éditeur de code.|[Ouvrir un modèle](../../ssms/template/open-a-template.md)|  
|Explique comment remplacer des valeurs de paramètre de modèle après avoir ouvert un modèle dans un éditeur de code.|[Remplacer les paramètres de modèle](../../ssms/template/replace-template-parameters.md)|  
  
