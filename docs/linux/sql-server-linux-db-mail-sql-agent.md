---
title: "Messagerie de base de données et les alertes par courrier électronique avec l’Agent SQL sur Linux | Documents Microsoft"
description: "Cette rubrique décrit comment utiliser la messagerie de base de données et les alertes par courrier électronique avec SQL Server sur Linux"
author: meet-bhagdev
ms.author: meetb
manager: jhubbard
ms.date: 10/02/2017
ms.topic: article
ms.prod: sql-linux
ms.technology: database-engine
ms.assetid: tbd
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 834bba08c90262fd72881ab2890abaaf7b8f7678
ms.openlocfilehash: 77eed5cce942dbb91b0b9eb5afbd9ad11403e1d2
ms.contentlocale: fr-fr
ms.lasthandoff: 10/02/2017

---
# <a name="db-mail-and-email-alerts-with-sql-agent-on-linux"></a>Messagerie de base de données et les alertes par courrier électronique avec l’Agent SQL sur Linux

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

Les étapes suivantes vous montrent comment configurer la messagerie de base de données et l’utiliser avec l’Agent SQL Server (**mssql-server-agent**) sur Linux. 

> [!NOTE]
> Pour utiliser la messagerie de base de données avec SQL Server sur Linux, vous devez utiliser SQL Server 2017 RC1 ou version ultérieure.

## <a name="prerequisites"></a>Conditions préalables

- SQL Server 2017 RC1 et versions ultérieures
- L’Agent SQL Server v14.0.800.90-2 et versions ultérieures (si vous envisagez d’utiliser la messagerie pour les alertes)

## <a name="1-enable-db-mail"></a>1. Activer la messagerie de base de données

```sql
USE master 
GO 
sp_configure 'show advanced options',1 
GO 
RECONFIGURE WITH OVERRIDE 
GO 
sp_configure 'Database Mail XPs', 1 
GO 
RECONFIGURE  
GO  
```

## <a name="2-create-a-new-account"></a>2. Créer un nouveau compte
```sql
EXECUTE msdb.dbo.sysmail_add_account_sp 
@account_name = 'SQLAlerts', 
@description = 'Account for Automated DBA Notifications', 
@email_address = 'sqlagenttest@gmail.com', 
@replyto_address = 'sqlagenttest@gmail.com', 
@display_name = 'SQL Agent', 
@mailserver_name = 'smtp.gmail.com', 
@port = 587, 
@enable_ssl = 1, 
@username = 'sqlagenttest@gmail.com', 
@password = '<password>' 
GO
```

## <a name="3-create-a-default-profile"></a>3. Créer un profil par défaut

```sql
EXECUTE msdb.dbo.sysmail_add_profile_sp 
@profile_name = 'default', 
@description = 'Profile for sending Automated DBA Notifications' 
GO
```

## <a name="4-add-the-database-mail-account-to-a-database-mail-profile"></a>4. Ajoutez le compte de messagerie de base de données à un profil de messagerie de base de données
```sql
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp 
@profile_name = 'default', 
@principal_name = 'public', 
@is_default = 1 ; 
 ```
 
## <a name="5-add-account-to-profile"></a>5. Ajouter un compte au profil 
```sql
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp   
@profile_name = 'default',   
@account_name = 'SQLAlerts',   
@sequence_number = 1;  
 ```
 
## <a name="6-send-test-email"></a>6. Envoyer un courrier électronique de test
> [!NOTE]
> Vous devrez accéder à votre client de messagerie et activer la « moins sécurisées clients autorisés à envoyer du courrier. » Pas tous les clients reconnaissent la messagerie de base de données comme un démon par courrier électronique.

```
EXECUTE msdb.dbo.sp_send_dbmail 
@profile_name = 'default', 
@recipients = 'recipient-email@gmail.com', 
@Subject = 'Testing DBMail', 
@Body = 'This message is a test for DBMail' 
GO
```

## <a name="7-set-db-mail-profile-using-mssql-conf-or-environment-variable"></a>7. Définir le profil de messagerie de base de données à l’aide de la variable d’environnement ou mssql-conf
Vous pouvez utiliser les utilitaires de mssql-conf ou des variables d’environnement pour inscrire votre profil de messagerie de base de données. Dans ce cas, nous allons appeler de notre valeur par défaut du profil.

```bash
# via mssql-conf
sudo /opt/mssq/bin/mssql-conf set sqlagent.databasemailprofile default
# via environment variable
MSSQL_AGENT_EMAIL_PROFILE=default
```

## <a name="8-set-up-an-operator-for-sqlagent-job-notifications"></a>8. Définir un opérateur pour les notifications de tâche SQLAgent 

```sql
EXEC msdb.dbo.sp_add_operator 
@name=N'JobAdmins',  
@enabled=1, 
@email_address=N'recipient-email@gmail.com',  
@category_name=N'[Uncategorized]' 
GO 
```

## <a name="9-send-email-when-agent-test-job-succeeds"></a>9. Envoyer un courrier électronique lors de réussite du travail de Test de l’Agent 

```
EXEC msdb.dbo.sp_update_job 
@job_name='Agent Test Job', 
@notify_level_email=1, 
@notify_email_operator_name=N'JobAdmins' 
GO
```

## <a name="next-steps"></a>Étapes suivantes
Pour plus d’informations sur l’utilisation de l’Agent SQL Server pour créer, planifier et exécuter des travaux, consultez [exécuter un travail de l’Agent SQL Server sur Linux](sql-server-linux-run-sql-server-agent-job.md).

