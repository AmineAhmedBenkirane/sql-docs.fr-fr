---
title: Architecture du pilote ODBC | Documents Microsoft
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: reference
ms.reviewer: 
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ODBC drivers [ODBC], architecture
ms.assetid: 21a62c7c-192e-4718-a16e-aa12b0de4419
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 39477161fd3eac02912fd371a873b94ea9f51828
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="odbc-driver-architecture"></a>Architecture du pilote ODBC
Les rédacteurs de pilotes doivent être conscients que l’architecture du pilote peut affecter si une application peut utiliser propres au SGBD SQL.  
  
 ![Illustre l’architecture du pilote ODBC](../../../odbc/reference/develop-driver/media/odbcdriverovruarch.gif "ODBCDriverOvruArch")  
  
 [Pilotes basés sur des fichiers](../../../odbc/reference/file-based-drivers.md)  
  
 Lorsque le pilote accède directement aux données physiques, le pilote fonctionne en tant que source de pilote et de données. Le pilote doit traiter les appels ODBC et les instructions SQL. Les développeurs de pilotes basés sur le fichier doivent écrire leurs propres moteurs de base de données.  
  
 [Pilotes basés sur SGBD](../../../odbc/reference/dbms-based-drivers.md)  
  
 Lorsqu’un moteur de base de données distincte est utilisé pour accéder aux données physiques, le pilote traite uniquement les appels ODBC. Il passe les instructions SQL au moteur de base de données pour le traitement.  
  
 [Architecture de réseau](../../../odbc/reference/network-example.md)  
  
 Les configurations et DBMS ODBC peuvent exister sur un réseau unique.  
  
 [Autres Architectures de pilote](../../../odbc/reference/other-driver-architectures.md)  
  
 Lorsqu’un pilote est requis pour fonctionner avec un large éventail de sources de données, il peut être utilisé en tant que l’intergiciel (middleware). Architecture du moteur de jointure hétérogène peut rendre le pilote apparaissent sous la forme d’un gestionnaire de pilotes. Pilotes peuvent également être installés sur les serveurs, où elles peuvent être partagées par une série de clients.  
  
 Pour plus d’informations sur l’architecture du pilote, consultez [du Gestionnaire de pilotes](../../../odbc/reference/the-driver-manager.md) et [Architecture du pilote](../../../odbc/reference/driver-architecture.md) dans la section sur [Architecture ODBC](../../../odbc/reference/odbc-architecture.md).  
  
 Vous trouverez plus d’informations sur les problèmes liés aux pilotes dans les emplacements décrits dans le tableau suivant.  
  
|Problème|Rubrique|Emplacement|  
|-----------|-----------|--------------|  
|Problèmes de compatibilité avec les applications et des pilotes|[Compatibilité de l’application/pilote](../../../odbc/reference/develop-app/application-and-driver-compatibility.md)|[Considérations sur la programmation](../../../odbc/reference/develop-app/programming-considerations.md), dans la référence du programmeur ODBC|  
|Pilotes ODBC de l’écriture|[L’écriture ODBC 3.x pilotes](../../../odbc/reference/develop-app/writing-odbc-3-x-drivers.md)|[Considérations sur la programmation](../../../odbc/reference/develop-app/programming-considerations.md), dans la référence du programmeur ODBC|  
|Instructions de pilote pour la compatibilité descendante|[Instructions de pilote pour la compatibilité descendante](../../../odbc/reference/appendixes/appendix-g-driver-guidelines-for-backward-compatibility.md)|[Annexe g : les instructions de pilote pour la compatibilité descendante](../../../odbc/reference/appendixes/appendix-g-driver-guidelines-for-backward-compatibility.md), dans la référence du programmeur ODBC|  
|Connexion à un pilote|[En choisissant des données Source ou pilote](../../../odbc/reference/develop-app/choosing-a-data-source-or-driver.md)|[Connexion aux données Source ou le pilote](../../../odbc/reference/develop-app/connecting-to-a-data-source-or-driver.md), dans la référence du programmeur ODBC|  
|Identification des pilotes|[Affichage des pilotes](../../../odbc/admin/viewing-drivers.md)|[Affichage des pilotes](../../../odbc/admin/viewing-drivers.md), l’administrateur de Source de données ODBC Microsoft aide en ligne|  
|Activer le regroupement de connexions|[Le regroupement de connexions ODBC](../../../odbc/reference/develop-app/driver-manager-connection-pooling.md)|[Connexion aux données Source ou le pilote](../../../odbc/reference/develop-app/connecting-to-a-data-source-or-driver.md), dans la référence du programmeur ODBC|  
|Problèmes de pilote et de connexion Unicode/ANSI.|[Pilotes d’Unicode](../../../odbc/reference/develop-app/unicode-drivers.md)|[Considérations sur la programmation](../../../odbc/reference/develop-app/programming-considerations.md), dans la référence du programmeur ODBC|  
  
## <a name="see-also"></a>Voir aussi  
 [Développement d’un pilote ODBC](../../../odbc/reference/develop-driver/developing-an-odbc-driver.md)

