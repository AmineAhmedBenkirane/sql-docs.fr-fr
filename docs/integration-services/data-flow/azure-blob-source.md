---
title: Source des objets blob Azure | Microsoft Docs
ms.custom: 
ms.date: 07/25/2016
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: data-flow
ms.reviewer: 
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.dts.designer.afpblobsrc.f1
- sql14.dts.designer.afpblobsrc.f1
ms.assetid: 80645c5c-88c8-4fb0-8607-de1bb7bffcbb
caps.latest.revision: "12"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: a274b61e96ab0af99cf91d8d99ba0197a705f252
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="azure-blob-source"></a>Azure Blob Source
  Le composant **Azure Blob Source** permet à un package SSIS de lire les données provenant d’un blob Azure. Les formats de fichier pris en charge sont CSV et AVRO.
  
  Pour afficher l’éditeur d’Azure Bloc Source, faites glisser **Azure Blob Source** sur le concepteur de flux de données et double-cliquez dessus pour ouvrir l’éditeur.  
  
 **Source des objets blob Azure** est un composant de [SQL Server Integration Services (SSIS) Feature Pack pour Azure](../../integration-services/azure-feature-pack-for-integration-services-ssis.md).  
  
1.  Dans le champ **Gestionnaire de connexions Azure Storage** , spécifiez un gestionnaire de connexions Azure Storage existant ou créez-en un qui fera référence à un compte Azure Storage.  
  
2.  Dans le champ **Nom du conteneur d’objets blob** , spécifiez le nom du conteneur d’objets blob qui contient les fichiers sources.  
  
3.  Dans le champ **Nom de l’objet blob** , indiquez le chemin d’accès à l’objet blob.  
  
4.  Dans le champ **Format de fichier d’objet blob** , spécifiez le format d’objet blob à utiliser.  
  
5.  Si le format de fichier est CSV, vous devez renseigner le champ **Caractère séparateur de colonnes** . Sélectionnez également l’option **Noms de colonne dans la première ligne de données** si la première ligne du fichier contient des noms de colonne.  
  
6.  Après avoir spécifié les informations de connexion, basculez vers la page **Colonnes** pour mapper les colonnes sources sur les colonnes de destination du flux de données SSIS.  
  
  
