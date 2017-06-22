---
title: "Utilisation de datasets partagés (portail web) | Documents Microsoft"
ms.custom: 
ms.date: 05/15/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2641ea84-9343-4e6f-aec1-25339031b163
caps.latest.revision: 7
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 6dfbc134c0f0e351648d19cf8c485fe25a58eb99
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="work-with-shared-datasets---web-portal"></a>Utiliser des datasets partagés - portail web

[!INCLUDE[ssrs-appliesto-sql2016-preview](../includes/ssrs-appliesto-sql2016-preview.md)]

Avec un dataset partagé, vous pouvez gérer les paramètres d'un jeu de données (dataset) séparément des rapports et des autres éléments de catalogue qui l'utilisent. Les datasets partagés sont utilisables avec des rapports paginés et mobiles, ainsi qu’avec des indicateurs de performance clés.

Vous pouvez afficher et gérer les propriétés d’un dataset partagé dans le portail web. À partir du portail web, vous pouvez lancer le Générateur de rapports pour créer ou modifier des datasets partagés.

## <a name="create-a-shared-dataset"></a>Création d’un dataset partagé
  
Procédez comme suit pour créer un dataset partagé.  
  
1.  Sélectionnez Nouveau dans la barre de menus.  
  
2.  Sélectionnez **Dataset**.  
  
    ![ssRSDataset-NewDataset](../reporting-services/media/ssrsdataset-newdataset.png)  
  
3.  L’opération lance alors le Générateur de rapports, ou vous êtes invité à le télécharger.  
  
4.  Dans la boîte de dialogue **Nouveau rapport ou Dataset** , sélectionnez une source de données connexion à utiliser pour ce jeu de données. Vous devrez peut-être naviguer jusqu’à l’emplacement de la source des données partagée.  
  
5.  Sélectionnez **Créer**.  
  
6.  Créez votre dataset, puis sélectionnez l’icône **Enregistrer** dans l’angle supérieur gauche pour enregistrer le dataset dans le serveur de rapports.  
  
## <a name="manage-an-existing-shared-dataset"></a>Gestion d’un dataset partagé existant
  
Procédez comme suit pour gérer un dataset existant.  
  
> [!NOTE]
> Si vous ne voyez pas le dataset partagé dans le dossier, assurez-vous que vous affichez des jeux de données. Vous pouvez sélectionner **Afficher** dans la barre de menus dans le coin supérieur droit du portail web. Assurez-vous que **Datasets** est activé.  
  
1.  Sélectionnez le **points de suspension (...)**  pour le jeu de données que vous souhaitez gérer.  
  
    ![ssRSDataset-Ellipse](../reporting-services/media/ssrsdataset-ellipse.png)  
  
2.  Sélectionnez **Gérer** . L’écran de modification s’affiche alors.  
  
    ![ssRSDataset-Manage](../reporting-services/media/ssrsdataset-manage.png)  
  
## <a name="properties"></a>Propriétés
  
Dans la fenêtre des propriétés, vous pouvez modifier le **nom** et la **description** du dataset. Vous pouvez également utiliser les fonctions **Supprimer**, **Déplacer**, **Modifier dans le Générateur de rapports**, **Télécharger** ou **Remplacer**.  
  
![ssRSdataset-Properties](../reporting-services/media/ssrsdataset-properties.png)  
  
## <a name="caching"></a>Mise en cache
  
Vous disposez de différentes options de mise en cache des données d’un dataset. Vous pouvez commencer avec une simple sélection.  
  
1.  **Toujours exécuter ce rapport avec les données les plus récentes** interroge la source de données en cas de requête.  
  
2.  **Mettre en cache des copies de ce rapport et les utiliser en cas de disponibilité** place une copie temporaire des données dans un cache pour une utilisation avec les éléments qui utilisent ce dataset. La mise en cache améliore habituellement les performances, car les données sont retournées à partir du cache ; la requête de dataset n'est pas réexécutée.  
  
![ssRSDataset-Caching1](../reporting-services/media/ssrsdataset-caching1.png)  
  
Vous disposerez d’options supplémentaires en sélectionnant **Mettre en cache des copies de ce rapport et les utiliser en cas de disponibilité** .  
  
![ssRSDataset-Caching2](../reporting-services/media/ssrsdataset-caching2.png)  
  
### <a name="cache-expiration"></a>Expiration du cache  
  
Vous pouvez déterminer si vous voulez faire expirer le cache pour le dataset partagé après un certain intervalle, ou si vous préférez définir une planification. Vous pouvez utiliser une planification partagée.  
  
![ssRSDataset-Caching3](../reporting-services/media/ssrsdataset-caching3.png)  
  
> [!NOTE]
> La définition d’un délai d’expiration n’actualise pas le cache. Sans un plan d’actualisation du cache, les données sont actualisées à l’exécution suivante du dataset.  
  
### <a name="cache-refresh-plans"></a>Plans d'actualisation du cache  
  
Vous pouvez utiliser des plans d’actualisation du cache pour créer des planifications de préchargement de copies temporaires des données pour un dataset partagé dans le cache. Un plan d'actualisation inclut une planification et la possibilité de spécifier ou de remplacer des valeurs pour les paramètres. Vous ne pouvez pas remplacer les valeurs des paramètres marqués en lecture seule. Vous pouvez créer et utiliser plusieurs plans d'actualisation.   
  
Les rôles à attribuer par défaut qui vous permettent d'ajouter, de supprimer et de modifier des datasets partagés pour des plans d'actualisation du cache sont les suivants : Gestionnaire de contenu, Mes Rapports et Serveur de publication.  
  
Une fois l’option de cache activée ci-dessus, vous pouvez ensuite définir un plan d’actualisation du cache. Pour cela, sélectionnez le lien **Gérer les plans d’actualisation** qui apparaît une fois que vous appliquez les paramètres de cache. Vous serez alors dirigé vers la page de planification d’actualisation du cache.   
  
Pour créer un plan d’actualisation du cache, cliquez sur **Nouveau plan d'actualisation du cache**. Vous pouvez ensuite entrer un nom pour le plan et spécifier une planification. Si le dataset comporte des paramètres définis, ils seront répertoriés et vous serez en mesure de leur attribuer des valeurs, sauf s’ils sont marqués en lecture seule.  
  
Une fois que vous avez terminé, vous pouvez sélectionner **Créer un plan d’actualisation du Cache**.  
  
![ssRSDataset-Caching4](../reporting-services/media/ssrsdataset-caching4.png)  
  
> [!NOTE]
> L’agent SQL Server doit être en cours d’exécution pour créer un plan d’actualisation du cache.  
  
Vous pouvez ensuite **Modifier** ou **Supprimer** des plans répertoriés. L’option **Créer à partir d'un élément existant** est activée lorsqu'un seul et unique plan d'actualisation du cache est sélectionné. Cette option crée un nouveau plan d'actualisation copié à partir du plan d'origine. La page du plan d'actualisation du cache qui s'ouvre contient les détails du plan sélectionné. Vous pouvez alors modifier les options du plan d'actualisation et enregistrer ce dernier en utilisant une nouvelle description.  

D’autres questions ? [Essayez de poser le forum Reporting Services](http://go.microsoft.com/fwlink/?LinkId=620231)
