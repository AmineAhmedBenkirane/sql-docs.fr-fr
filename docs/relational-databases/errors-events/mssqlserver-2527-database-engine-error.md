---
title: MSSQLSERVER_2527 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords: 2527 (Database Engine error)
ms.assetid: 1cef90ef-9c39-44e6-bc7f-316c8f53c10c
caps.latest.revision: "17"
author: edmacauley
ms.author: edmaca
manager: cguyer
ms.workload: Inactive
ms.openlocfilehash: 006041fe98cdc7f6add16b16ac0fb8169a2dfeeb
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="mssqlserver2527"></a>MSSQLSERVER_2527
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|2527|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|DBCC_INDEX_FILEGROUP_IS_OFFLINE|  
|Texte du message|Impossible de traiter l'index I_NAME de la table O_NAME car le groupe de fichiers F_NAME est hors connexion.|  
  
## <a name="explanation"></a>Explication  
Ce message d'information indique qu'il est impossible de vérifier l'index, car l'un des groupes de fichiers qui stocke les données de l'index n'est pas connecté. L'état des fichiers dans un groupe de fichiers détermine la disponibilité du groupe de fichiers tout entier. Pour qu'un groupe de fichiers soit disponible, tous ses fichiers doivent être en ligne. S’il n’y a pas d’autre problème, tous les autres index du même objet seront vérifiés.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Pour afficher l’état des fichiers du groupe de fichiers spécifié, interrogez l’affichage catalogue **sys.database_files** ou **sys.master_files**.  
  
Restaurez le fichier hors connexion à partir d'une sauvegarde.  
  
## <a name="see-also"></a>Voir aussi  
[sys.database_files &#40;Transact-SQL&#41;](~/relational-databases/system-catalog-views/sys-database-files-transact-sql.md)  
[sys.master_files &#40;Transact-SQL&#41;](~/relational-databases/system-catalog-views/sys-master-files-transact-sql.md)  
[RESTORE &#40;Transact-SQL&#41;](~/t-sql/statements/restore-statements-transact-sql.md)  
  
