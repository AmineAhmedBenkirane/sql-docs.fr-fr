---
title: Configuration du pilote ODBC pour Oracle | Documents Microsoft
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring ODBC driver for Oracle [ODBC]
- ODBC driver for Oracle [ODBC], configuring
ms.assetid: 0a5f827c-0b80-4627-85cb-f10292b9fb33
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 64e6dfe9f31eb983170f08e9fcd3e0705ba9ae62
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="configuring-the-odbc-driver-for-oracle"></a>Configuration du pilote ODBC pour Oracle
> [!IMPORTANT]  
>  Cette fonctionnalité sera supprimée dans une future version de Windows. Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité. Au lieu de cela, utilisez le pilote ODBC fourni par Oracle.  
  
 Vous pouvez contrôler les performances du pilote ODBC pour Oracle par le fait de connaître l’environnement de données et définir correctement les paramètres de la connexion de source de données par le biais du [administrateur de sources de données ODBC](../../odbc/admin/odbc-data-source-administrator.md) boîte de dialogue zone ou à connecter des paramètres de chaîne. La boîte de dialogue fournit les contrôles suivants pour la connexion à une source de données à l’aide de la boîte de dialogue ou à l’aide de chaînes de connexion :  
  
-   **Onglet de sources de données utilisateur** répertorie les noms de Source de données qui sont sur l’ordinateur local.  
  
-   **Onglet de sources de données système** vous permet d’ajouter ou supprimer une source de données système. Sources de données système est accessible par tous les utilisateurs sur l’ordinateur local.  
  
-   **Onglet sources de données de fichier** vous permet d’ajouter ou supprimer une source de données de fichier à partir de l’ordinateur local. Sources de données de fichier peuvent être partagés par tous les utilisateurs qui ont le même pilote installé.  
  
-   **Onglet pilotes** répertorie les pilotes ODBC installés.  
  
-   **Onglet suivi** vous permet de spécifier comment le Gestionnaire de pilotes ODBC suit les appels aux fonctions ODBC. Vous pouvez configurer le traçage séparément pour chaque application ODBC installé.  
  
-   **Le regroupement de connexion, onglet** vous permet de sélectionner les options de connexion pour chaque pilote installé.  
  
-   **Sur l’onglet** répertorie les fichiers des composants ODBC installés.  
  
 Après avoir ajouté une source de données, vous pouvez utiliser la **administrateur de sources de données ODBC** boîte de dialogue pour configurer l’accès à votre source de données. Sélectionnez une source de données, puis cliquez sur un des onglets pour modifier ou consulter les informations.
