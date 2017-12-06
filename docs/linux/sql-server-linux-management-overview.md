---
title: "Gérer SQL Server sur Linux | Documents Microsoft"
description: "Cette rubrique fournit des liens vers les tâches de gestion courantes et des outils pour SQL Server en cours d’exécution sur Linux."
author: rothja
ms.author: jroth
manager: jhubbard
ms.date: 03/17/2017
ms.topic: article
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: sql-linux
ms.suite: sql
ms.technology: database-engine
ms.assetid: 6bd8eb0b-593d-467e-87ea-ab1c4dbcd1ea
ms.custom: 
ms.workload: On Demand
ms.openlocfilehash: b9a28793d63f20a983f5eec92641f33978f6888b
ms.sourcegitcommit: 531d0245f4b2730fad623a7aa61df1422c255edc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/01/2017
---
# <a name="choose-the-right-tool-to-manage-sql-server-on-linux"></a>Choisissez l’outil approprié pour gérer SQL Server sur Linux

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

Il existe plusieurs façons de gérer 2017 du serveur SQL sur Linux. La section suivante fournit une vue d’ensemble rapide des outils d’administration différents et des techniques avec des pointeurs vers les ressources supplémentaires.

## <a name="mssql-conf"></a>MSSQL-conf 
Le **mssql-conf** outil configure SQL Server sur Linux. Pour plus d’informations, consultez [configurer SQL Server sur Linux avec mssql-conf](sql-server-linux-configure-mssql-conf.md).

## <a name="transact-sql"></a>Transact-SQL

Presque tout ce dont vous pouvez faire dans un outil client peut également être accompli avec des instructions Transact-SQL. SQL Server fournit [des vues de gestion dynamique (DMV)](../relational-databases/system-dynamic-management-views/system-dynamic-management-views.md) qui interroger l’état et la configuration de SQL Server. Il existe également [commandes Transact-SQL](https://msdn.microsoft.com/library/bb510741.aspx) pour les tâches de gestion de base de données. Vous pouvez exécuter ces commandes dans n’importe quel outil client qui prend en charge la connexion à SQL Server et l’exécution des requêtes Transact-SQL. Exemples [sqlcmd](sql-server-linux-setup-tools.md), [Visual Studio Code](sql-server-linux-develop-use-vscode.md), et [SQL Server Management Studio](sql-server-linux-manage-ssms.md).

## <a name="sql-server-management-studio-on-windows"></a>SQL Server Management Studio sur Windows

SQL Server Management Studio (SSMS) est une application Windows qui fournit une interface utilisateur graphique pour la gestion de SQL Server. Bien qu’il s’exécute actuellement uniquement sur Windows, vous pouvez l’utiliser pour se connecter à distance à vos instances de SQL Server de Linux. Pour plus d’informations sur l’utilisation de SSMS pour gérer SQL Server, consultez [SSMS d’utilisation pour gérer SQL Server sur Linux](sql-server-linux-manage-ssms.md).

## <a name="powershell"></a>PowerShell

PowerShell fournit un environnement riche de ligne de commande pour gérer SQL Server sur Linux. Pour plus d’informations, consultez [utiliser PowerShell pour gérer SQL Server sur Linux](sql-server-linux-manage-powershell.md).

## <a name="next-steps"></a>Étapes suivantes

Pour plus d’informations sur SQL Server sur Linux, consultez [SQL Server sur Linux](sql-server-linux-overview.md).
