---
title: Accéder aux données pour les opérations DQS | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: data-quality-services
ms.service: ''
ms.component: install-windows
ms.reviewer: ''
ms.suite: sql
ms.technology:
- data-quality-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88dfb9ea-6321-4eaf-b9e4-45d36ef048f6
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 8da32d9464294466e93a9d7a42094709da7dbade
ms.sourcegitcommit: 34766933e3832ca36181641db4493a0d2f4d05c6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="access-data-for-the-dqs-operations"></a>Accéder aux données pour les opérations DQS
  Pour utiliser vos données sources pour les opérations [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS), et exporter vos données traitées, vous pouvez effectuer l'une des opérations suivantes :  
  
-   Copiez vos données sources dans une table/vue dans la base de données DQS_STAGING_DATA, puis utilisez-les pour les opérations DQS. Vous pouvez également exporter les données traitées dans une nouvelle table de la base de données DQS_STAGING_DATA. Pour cela, votre compte d'utilisateur Windows doit être accordé l'accès en lecture/écriture à la base de données de DQS_STAGING_DATA.  
  
-   Utilisez votre propre base de données comme données sources pour les opérations DQS, et destination pour exporter les données traitées. Pour cela, vérifiez que votre base de données est dans la même instance SQL Server que les bases de données Data Quality Server. Sinon, la base de données ne sera pas disponible dans Data Quality Client pour les opérations DQS. De plus, votre compte d'utilisateur Windows doit avoir accès à la base de données DQS_STAGING_DATA pour exporter les résultats correspondants, car ceux-ci sont exportés en deux phases : en premier lieu, les résultats de correspondance sont exportés vers des tables temporaires dans la base de données DQS_STAGING_DATA, puis déplacés vers la table de votre base de données de destination.  
  
## <a name="prerequisites"></a>Prerequisites  
  
-   Vous devez avoir terminé l'installation du [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] en exécutant le fichier DQSInstaller.exe. Pour plus d’informations, consultez [Exécuter DQSInstaller.exe pour terminer l’installation du serveur DQS](../../data-quality-services/install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).  
  
-   Votre compte d'utilisateur Windows doit être membre du rôle serveur fixe approprié (tel que le securityadmin, le serveradmin, ou le sysadmin) dans l'instance du moteur de base de données à accorder/modifier l'accès à la connexion SQL sur les bases de données.  
  
### <a name="to-grant-readwrite-access-to-a-user-on-the-dqsstagingdata-database"></a>Pour accorder l'accès en lecture/écriture à un utilisateur sur la base de données DQS_STAGING_DATA  
  
1.  Démarrez Microsoft SQL Server Management Studio.  
  
2.  Dans Microsoft SQL Server Management Studio, développez votre instance SQL Server, puis développez **Sécurité**et ensuite **Connexions**.  
  
3.  Cliquez avec le bouton droit sur une connexion SQL, puis cliquez sur **Propriétés**.  
  
4.  Dans la boîte de dialogue **Propriétés de la connexion** , cliquez sur la page de **Mappage de l'utilisateur** dans le volet gauche.  
  
5.  Dans le volet droit, cochez la case sous la colonne **Mappage** de la base de données **DQS_STAGING_DATA** , puis sélectionnez les rôles suivants dans le volet **Appartenance au rôle de base de données : DQS_STAGING_DATA** :  
  
    -   **db_datareader**: lire des données depuis des tables/vues.  
  
    -   **db_datawriter**: ajouter, supprimer ou modifier des données dans des tables.  
  
    -   **db_ddladmin**: créer, modifier ou supprimer des tables/vues.  
  
6.  Dans la boîte de dialogue **Propriétés de la connexion** , cliquez sur **OK** pour appliquer les modifications.  
  
## <a name="next-steps"></a>Next Steps  
 Essayez effectuer des opérations DQS qui accèdent à la base de données en tant que source de données pour l'opération DQS, puis exportez les données traitées vers la base de données.  
  
## <a name="see-also"></a> Voir aussi  
 [Installer Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md)  
  
  
