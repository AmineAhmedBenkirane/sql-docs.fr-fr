---
title: "Destination Azure Data Lake Store | Microsoft Docs"
ms.custom: ""
ms.date: "03/02/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SQL13.DTS.DESIGNER.AFPADLSDEST.F1"
  - "sql14.dts.designer.afpadlsdest.f1"
ms.assetid: 4c4f504f-dd2b-42c5-8a20-1a8ad9a5d632
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Destination Azure Data Lake Store
  Le composant **Destination Azure Data Lake Store** permet à un package SSIS d’écrire des données dans Azure Data Lake Store. Les formats de fichier pris en charge sont les formats texte, Avro et ORC. 
  
 **Destination Azure Data Lake Store** est un composant de SQL Server Integration Services (SSIS) Feature Pack pour Azure pour SQL Server 2016. Le Feature Pack est disponible en téléchargement [ici](http://go.microsoft.com/fwlink/?LinkID=626967).  
 >   [!NOTE] Pour que le gestionnaire de connexions Azure Data Lake Store et les composants qui l’utilisent, notamment la source Azure Data Lake Store et la destination Azure Data Lake Store, puissent se connecter aux services, veillez à télécharger la dernière version du Feature Pack Azure [ici](https://www.microsoft.com/download/details.aspx?id=49492). 

## <a name="configure-the-azure-data-lake-store-destination"></a>Configurer la destination Azure Data Lake Store  
1. Faites glisser le composant **Destination Azure Data Lake Store** vers le concepteur de flux de données et double-cliquez dessus pour visualiser l’éditeur.  

2.  Dans le champ **Gestionnaire de connexions Azure Data Lake Store**, spécifiez un gestionnaire de connexions Azure Data Lake Store existant ou créez-en un qui fait référence à un service Azure Data Lake Store.  
  
    1.  Dans le champ **Chemin du fichier**, spécifiez le nom du fichier où vous souhaitez écrire des données. Si ce fichier existe déjà, son contenu est remplacé.  
  
    2.  Dans le champ **Format de fichier**, spécifiez le format de fichier à utiliser.  
  
        Si le format de fichier est le format texte, vous devez renseigner le champ **Délimiteur de colonne**. Sélectionnez également l’option **Noms de colonne dans la première ligne de données** si la première ligne du fichier contient des noms de colonne.  

        Si le format de fichier est ORC, vous devez installer l’environnement JRE de la plateforme correspondante. 
  
3.  Après avoir spécifié les informations de connexion, basculez vers la page **Colonnes** pour mapper les colonnes sources sur les colonnes de destination du flux de données SSIS.  
  
  