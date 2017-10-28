---
title: "L’installation de SSMA pour SAP ASE (SybaseToSQL) | Documents Microsoft"
ms.custom: 
ms.date: 09/30/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 8d5a4ce6-b747-46e3-9184-645d56e8b35c
caps.latest.revision: 6
author: Shamikg
ms.author: Shamikg
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 759a7084024e1c608431683de6dae5a6fb40304e
ms.openlocfilehash: 7b2c96006c5495c89486c8a86e1b60b64f2dd22c
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="installing-ssma-for-sap-ase-sybasetosql"></a>L’installation de SSMA pour SAP ASE (SybaseToSQL)
[!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]Migration Assistant (SSMA) pour SAP ASE se compose d’une application cliente qui vous permet d’effectuer une migration à partir de SAP Adaptive Server Enterprise (ASE) à [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] ou base de données SQL Azure. Il contient également un Pack d’extension qui prend en charge la migration des données et l’utilisation des fonctions de système ASE dans vos bases de données migrées.  
  
Vous installez l’application cliente sur l’ordinateur à partir duquel vous allez effectuer les étapes de migration. Vous devez installer les fichiers de pack d’extension sur l’ordinateur qui est en cours d’exécution [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] hébergeant des bases de données migrées.  
  
## <a name="upgrading-ssma-for-sybase"></a>La mise à niveau de SSMA pour Sybase  
Si vous souhaitez mettre à niveau vers une version ultérieure de SSMA pour SAP ASE, votre doit d’abord désinstaller le client et le Pack d’extension de serveur, puis installez la version la plus récente.  
  
Si vous ouvrez un projet à partir d’une version antérieure de SSMA pour SAP ASE, SSMA vous demande si vous souhaitez convertir le projet vers la version la plus récente. Vous devez cliquer sur **Oui** pour travailler avec le projet dans la version la plus récente de SSMA.  
  
## <a name="contents"></a>Sommaire  
  
|Rubrique| Description|  
|---------|---------------|  
|[L’installation de SSMA pour SAP ASE Client &#40; SybaseToSQL &#41;](../../ssma/sybase/installing-ssma-for-sybase-client-sybasetosql.md)|Fournit des informations et des instructions pour installer le client SSMA.|  
|[Installation des composants SSMA sur SQL Server &#40; SybaseToSQL &#41;](../../ssma/sybase/installing-ssma-components-on-sql-server-sybasetosql.md)|Fournit des informations et des instructions pour installer le Pack d’extension sur les instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)].|  
|[Suppression de SSMA pour les composants SAP ASE &#40; SybaseToSQL &#41;](../../ssma/sybase/removing-ssma-for-sybase-components-sybasetosql.md)|Fournit des instructions pour désinstaller le client pack programme et l’extension.|  
  
## <a name="see-also"></a>Voir aussi  
[Migration SAP ASE bases de données SQL Server - base de données SQL Azure &#40; SybaseToSQL &#41;](../../ssma/sybase/migrating-sybase-ase-databases-to-sql-server-azure-sql-db-sybasetosql.md)  

