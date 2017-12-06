---
title: "Installer l’Agent SQL Server sur Linux | Documents Microsoft"
description: "Cette rubrique décrit comment installer l’Agent SQL Server sur Linux."
author: rothja
ms.author: jroth
manager: jhubbard
ms.date: 10/02/2017
ms.topic: article
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: sql-linux
ms.suite: sql
ms.custom: 
ms.technology: database-engine
ms.assetid: 77f16adc-e6cb-4a57-82f3-7b9780369868
ms.workload: On Demand
ms.openlocfilehash: 7ba7f55064542f2650584a87888214052b8d74f4
ms.sourcegitcommit: 531d0245f4b2730fad623a7aa61df1422c255edc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/01/2017
---
# <a name="install-sql-server-agent-on-linux"></a>Installer l’Agent SQL Server sur Linux

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

Les étapes suivantes installer l’Agent SQL Server (**mssql-server-agent**) sur Linux. Le [l’Agent SQL Server](https://docs.microsoft.com/sql/ssms/agent/sql-server-agent) exécute les travaux planifiés de SQL Server. Pour plus d’informations sur les fonctionnalités prises en charge pour cette version de l’Agent SQL Server, consultez le [Release Notes](sql-server-linux-release-notes.md).

> [!NOTE]
> Avant d’installer l’Agent SQL Server, tout d’abord [installer SQL Server 2017](sql-server-linux-setup.md#platforms). Cela permet de configurer les clés et les référentiels que vous utilisez lorsque vous installez le **mssql-server-agent** package.

Installez l’Agent SQL Server pour votre plateforme :

- [Red Hat Enterprise Linux](#RHEL)
- [Ubuntu](#ubuntu)
- [SUSE Linux Enterprise Server](#SLES)

## <a name="RHEL">Installer sur RHEL</a>

Utilisez les étapes suivantes pour installer le **mssql-server-agent** sur Red Hat Enterprise Linux. 

```bash
sudo yum install mssql-server-agent
sudo systemctl restart mssql-server
```

Si vous avez déjà **mssql-server-agent** installé, vous pouvez mettre à jour vers la dernière version avec les commandes suivantes :

```bash
sudo yum check-update
sudo yum update mssql-server-agent
sudo systemctl restart mssql-server
```

Si vous avez besoin d’une installation hors connexion, recherchez le téléchargement du package de l’Agent SQL Server dans le [notes de publication](sql-server-linux-release-notes.md). Puis utilisez les mêmes étapes d’installation hors connexion décrites dans la rubrique [installer SQL Server](sql-server-linux-setup.md#offline).

## <a name="ubuntu">Installer sur Ubuntu</a>

Utilisez les étapes suivantes pour installer le **mssql-server-agent** sur Ubuntu. 

```bash
sudo apt-get update 
sudo apt-get install mssql-server-agent
sudo systemctl restart mssql-server
```

Si vous avez déjà **mssql-server-agent** installé, vous pouvez mettre à jour vers la dernière version avec les commandes suivantes :

```bash
sudo apt-get update 
sudo apt-get install mssql-server-agent
sudo systemctl restart mssql-server
```

Si vous avez besoin d’une installation hors connexion, recherchez le téléchargement du package de l’Agent SQL Server dans le [notes de publication](sql-server-linux-release-notes.md). Puis utilisez les mêmes étapes d’installation hors connexion décrites dans la rubrique [installer SQL Server](sql-server-linux-setup.md#offline).

## <a name="SLES">Installez SLES</a>

Utilisez les étapes suivantes pour installer le **mssql-server-agent** sur SUSE Linux Enterprise Server. 

Installer **mssql-server-agent** 

```bash
sudo zypper install mssql-server-agent
sudo systemctl restart mssql-server
```

Si vous avez déjà **mssql-server-agent** installé, vous pouvez mettre à jour vers la dernière version avec les commandes suivantes :

```bash
sudo zypper refresh
sudo zypper update mssql-server-agent
sudo systemctl restart mssql-server
```

Si vous avez besoin d’une installation hors connexion, recherchez le téléchargement du package de l’Agent SQL Server dans le [notes de publication](sql-server-linux-release-notes.md). Puis utilisez les mêmes étapes d’installation hors connexion décrites dans la rubrique [installer SQL Server](sql-server-linux-setup.md#offline).

## <a name="next-steps"></a>Étapes suivantes
Pour plus d’informations sur l’utilisation de l’Agent SQL Server pour créer, planifier et exécuter des travaux, consultez [exécuter un travail de l’Agent SQL Server sur Linux](sql-server-linux-run-sql-server-agent-job.md).
