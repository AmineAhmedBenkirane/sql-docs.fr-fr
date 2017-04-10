---
title: "Convertir les types sans v&#233;rification de la conversion (Assistant Importation et Exportation SQL&#160;Server) | Microsoft Docs"
ms.custom: ""
ms.date: "01/11/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.impexpwizard.nomappingfile.f1"
ms.assetid: 87d9d3e5-477f-4117-a37f-bff53ea3e14d
caps.latest.revision: 25
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 24
---
# Convertir les types sans v&#233;rification de la conversion (Assistant Importation et Exportation SQL&#160;Server)
  Une fois que vous avez sélectionné les tables et vues existantes pour copier ou vérifier la requête que vous avez fournie, l’Assistant Importation et Exportation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut afficher **Convertir les types sans vérification de la conversion**. L’Assistant affiche cette page quand il ne peut pas trouver un ou plusieurs fichiers de conversion et de mappage de types de données dont il a besoin pour mapper les types de données entre la source et la destination. La page inclut des informations qui vous aident à comprendre ce qui est manquant.
  
 Pour continuer sans connaître l’issue des conversions des types de données, cliquez sur **Suivant**. Sinon, cliquez sur **Précédent** pour modifier vos sélections, ou cliquez sur **Annuler** pour quitter l’Assistant.
  
 Pour plus d’informations sur la façon dont l’Assistant mappe les types de données des colonnes sources vers les colonnes de destination, et sur la façon dont il utilise les fichiers de mappage de types de données, consultez [Comment l’Assistant mappe les types de données entre la source et la destination ?](Import%20and%20Export%20Data%20with%20the%20SQL%20Server%20Import%20and%20Export%20Wizard.md\#wizardMapping).  

## <a name="screen-shot-of-the-convert-types-page"></a>Capture d’écran de la page Convertir des types  
  
La capture d’écran suivante montre un exemple de la page **Convertir les types sans vérification de la conversion** de l’Assistant.

![Convertir les types](../../integration-services/import-export-data/media/convert-types.png)

Le problème ici est que l’Assistant ne peut pas trouver de fichier de mappage qui mappe les types de données pour la destination sélectionnée.

Les informations de cette page n’incluent pas le nom du fichier de mappage manquant. Étant donné que l’Assistant ne sait pas si le fichier existe pour le fournisseur de données spécifié, il ne peut pas fournir de nom pour le fichier manquant.

## <a name="whats-next"></a>Étape suivante  
 Après avoir cliqué sur **Suivant** pour poursuivre sans savoir si les conversions des types de données vont réussir, vous tombez sur la page **Enregistrer et exécuter le package**. Dans cette page, vous spécifiez si vous souhaitez exécuter l’opération de copie immédiatement. Selon votre configuration, vous pouvez également être en mesure d’enregistrer le package [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] créé par l’Assistant pour le personnaliser et le réutiliser ultérieurement. Pour plus d’informations, consultez [Enregistrer et exécuter le package](../../integration-services/import-export-data/save-and-run-package-sql-server-import-and-export-wizard.md).  
