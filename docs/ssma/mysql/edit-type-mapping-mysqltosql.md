---
title: Modifier le mappage de Type (MySQLToSQL) | Documents Microsoft
ms.prod: sql-non-specified
ms.prod_service: sql-non-specified
ms.service: 
ms.component: ssma-mysql
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.technology: sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 184f7ab2-725f-491e-a15b-b889f2fb6a68
caps.latest.revision: "4"
author: Shamikg
ms.author: Shamikg
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 744612abf33414538b74824b56b280ba635bed6c
ms.sourcegitcommit: b2d8a2d95ffbb6f2f98692d7760cc5523151f99d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2017
---
# <a name="edit-type-mapping-mysqltosql"></a>Modifier le mappage de Type (MySQLToSQL)
Le **modifier le mappage de Type** boîte de dialogue vous permet de spécifier comment les types sont mappés entre les objets de base de données source et de destination.  
  
Vous pouvez accéder à cette boîte de dialogue à plusieurs endroits :  
  
-   Lorsque vous sélectionnez une base de données source ou un objet de base de données, le **le mappage de Type** onglet s’affiche à droite de l’Explorateur de métadonnées. Cliquez sur **ajouter** pour ajouter un nouveau mappage de type, ou cliquez sur **modifier** pour modifier un mappage de type existant.  
  
-   Sur le **outils** menu, sélectionnez **les paramètres de projet** ou **les paramètres de projet par défaut**. Dans la boîte de dialogue, sélectionnez **le mappage de Type**. Cliquez sur **ajouter** pour ajouter un nouveau mappage de type, ou cliquez sur **modifier** pour modifier un mappage de type existant.  
  
-   Mappages de type spécifique à la table de remplacent la base de données et les mappages de type de projet. Mappage spécifique à la base de données remplace les mappages du projet.  
  
## <a name="options"></a>Options  
  
##### <a name="source-type"></a>Type de source  
Sélectionnez le type de données source à mapper à un type de données SQL Server.  
  
Si le type de données est de longueur variable, les champs suivants apparaissent sous **Sourcetype**:  
  
##### <a name="from"></a>De  
Spécifiez la longueur minimale pour ce mappage. Par exemple, pour le **nchar** type de données, vous pouvez entrer 10 pour indiquer que ce mappage est pour une plage commençant à **nchar(10).**  
  
##### <a name="to"></a>Pour  
Spécifiez la longueur maximale pour ce mappage. Par exemple, pour le **nchar** type de données, vous pouvez entrer 20 pour indiquer que ce mappage est pour une plage de fin **nchar (20).**  
  
##### <a name="target-type"></a>Type de cible  
Sélectionnez le type de données SQL Server à laquelle le type de source de données est mappé. Lorsque SSMA crée la table ou de SQL Server, le type de source de données passe ce type de données.  
  
Si le type de données est de longueur variable, le champ suivant s’affiche sous **type cible**:  
  
##### <a name="replace-with"></a>Remplacer par  
Spécifiez la longueur de la cible pour ce mappage. Par exemple, pour le **nvarchar** type de données, vous pouvez entrer 20 pour spécifier que le type de données source spécifiée doit être mappé à **nvarchar (20).**  
  
