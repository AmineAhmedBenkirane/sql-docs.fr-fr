---
title: "&#201;tape&#160;3&#160;: modification de la valeur de configuration de la propri&#233;t&#233; Directory | Microsoft Docs"
ms.custom: ""
ms.date: "02/27/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
applies_to: 
  - "SQL Server 2016"
ms.assetid: ba2a091f-361c-4331-afe2-53b465164c36
caps.latest.revision: 29
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
---
# &#201;tape&#160;3&#160;: modification de la valeur de configuration de la propri&#233;t&#233; Directory
Dans cette tâche, vous modifiez le paramètre de configuration (stocké dans le fichier SSISTutorial.dtsConfig) pour la propriété Value de la variable de niveau package `User::varFolderName`. Cette variable met à jour la propriété Directory du conteneur de boucles Foreach. La valeur modifiée pointe sur le dossier **New Sample Data** que vous avez créé dans la tâche précédente. Une fois le paramètre de configuration modifié et le package exécuté, la propriété Directory est mise à jour par la variable, en utilisant la valeur récupérée dans le fichier de configuration au lieu de la valeur de la propriété Directory configurée au départ dans le package.  
  
### Pour modifier le paramétrage de configuration de la propriété Directory  
  
1.  Dans le Bloc-notes ou dans tout autre éditeur de texte, recherchez et ouvrez le fichier de configuration SSISTutorial.dtsConfig que vous avez créé à l'aide de l'Assistant Configuration de package au cours de la tâche précédente.  
  
2.  Modifiez la valeur de l’élément **ConfiguredValue** pour qu’elle corresponde au chemin du dossier **New Sample Data** que vous avez créé dans la tâche précédente. N'encadrez pas le chemin d'accès de guillemets. Si le dossier **New Sample Data** se trouve à la racine de votre lecteur (par exemple C:\\), le code XML mis à jour doit être semblable à l’exemple suivant :  
  
    `<?xml version="1.0"?><DTSConfiguration><DTSConfigurationHeading><DTSConfigurationFileInfo GeneratedBy="DOMAIN\UserName" GeneratedFromPackageName="Lesson 5" GeneratedFromPackageID="{F4475E73-59E3-478F-8EB2-B10AFA61D3FA}" GeneratedDate="6/10/2012 8:16:50 AM"/></DTSConfigurationHeading><Configuration ConfiguredType="Property" Path="\Package.Variables[User::varFolderName].Properties[Value]" ValueType="String"><ConfiguredValue></ConfiguredValue></Configuration></DTSConfiguration>`  
  
    Les informations d’en-tête, **GeneratedBy**, **GeneratedFromPackageID** et **GeneratedDate** sont différentes dans votre fichier, bien évidemment. L’élément à noter est l’élément **Configuration**. La propriété **Value** de la variable `User::varFolderName` contient maintenant C:\New Sample Data.  
  
3.  Enregistrez les modifications, puis fermez l'éditeur de texte.  
  
## Tâche suivante de la leçon  
[Étape 4 : Test de la leçon 5 du Package du didacticiel](../integration-services/step-4-testing-the-lesson-5-tutorial-package.md)  
  
  
  
