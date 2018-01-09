---
title: "Créer un projet SMO Visual c# dans Visual Studio .NET | Documents Microsoft"
ms.custom: 
ms.date: 08/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: smo
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: Visual C# [SMO]
ms.assetid: 1e7abb16-23a0-4a18-91ad-253261e6bf84
caps.latest.revision: "43"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 231e49bce1350370917871c131d3558b02b82d8d
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="how-to-create-a-visual-c-smo-project-in-visual-studio-net"></a>Comment créer un projet SMO Visual c# dans Visual Studio .NET
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]Cette section décrit comment créer une application de console SMO simple.  
  
 Cet exemple importe des espaces de noms, qui permettent au programme de référencer des types SMO. L’importation de la **Agent** espace de noms est facultative. Utilisez-la lorsque vous écrivez un programme qui utilise [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent. Le **commune** espace de noms est requis pour établir une connexion sécurisée à l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Le **SqlClient** espace de noms est utilisé pour traiter les erreurs d’exception SQL.  
  
### <a name="creating-a-visual-c-smo-project-in-visual-studionet"></a>Création d'un projet SMO Visual C# dans Visual Studio.NET  
  
1. Démarrez Visual Studio
  
2. Sur le **fichier** menu, cliquez sur **nouveau** , puis **projet**.  La boîte de dialogue **Nouveau projet** s'affiche.   
  
3. Dans le [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **installé** volet, accédez à **modèles**\\**Visual C#**\\**Windows** et sélectionnez **Application Console**.  
  
4. (Facultatif) Dans le **nom** texte, tapez le nom de la nouvelle application.  

5. Cliquez sur **OK** pour charger le modèle d’application console.  

6. Suivez les instructions de [l’installation de SMO](installing-smo.md) pour installer le package pour votre projet à référencer.
  
7. Dans le menu **Affichage** , cliquez sur **Code**.
    
8. Dans le code, avant l’instruction d’espace de noms, tapez la commande suivante **à l’aide de** instructions pour qualifier les types dans l’espace de noms SMO :
  
    ```  
    using Microsoft.SqlServer.Management.Smo;  
    using Microsoft.SqlServer.Management.Common;  
    ```  
  
15. SMO comporte différents espaces de noms sous Microsoft.SqlServer.Management.Smo, par exemple Microsoft.SqlServer.Management.Smo.Agent. Ajoutez ces espaces de noms lorsqu'ils sont requis.  
  
16. Vous pouvez à présent ajouter votre code SMO.  
  
  
