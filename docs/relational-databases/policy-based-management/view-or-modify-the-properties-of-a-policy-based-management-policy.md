---
title: "Afficher ou modifier les propriétés d’une stratégie de gestion basée sur des stratégies | Microsoft Docs"
ms.custom: 
ms.date: 10/06/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Policy-Based Management, modify policies
- Policy-Based Management, view policies
ms.assetid: ba805504-5db5-4731-a8da-a0e89cb20c37
caps.latest.revision: 9
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 485dca1df0b2d62fb71b1c51b86fe30e449b7ccf
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-policy"></a>Afficher ou modifier les propriétés d'une stratégie de gestion basée sur des stratégies
  Cette rubrique décrit comment afficher ou modifier les propriétés d'une stratégie de gestion basée sur des stratégies dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
  
##  <a name="BeforeYouBegin"></a> Avant de commencer  
  
  
####  <a name="Permissions"></a> Permissions  
 Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.  
  
##  <a name="SSMSProcedure"></a> Utilisation de SQL Server Management Studio  
  
#### <a name="to-view-the-properties-of-all-policies-on-an-object"></a>Pour afficher les propriétés de toutes les stratégies sur un objet  
  
1.  Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur, un objet de serveur, une base de données ou un objet de base de données, pointez sur **Stratégies** et sélectionnez **Afficher**. Pour plus d’informations sur les options disponibles dans la boîte de dialogue **Afficher les stratégies –***nom_objet* , consultez [Boîte de dialogue Afficher les stratégies](../../relational-databases/policy-based-management/view-policies-dialog-box.md).  
  
2.  Lorsque vous avez terminé, cliquez sur **Fermer**.  
  
#### <a name="to-view-or-modify-a-specific-policys-properties"></a>Pour afficher ou modifier les propriétés d'une stratégie spécifique  
  
1.  Dans **l’Explorateur d’objets**, cliquez sur le signe plus (+) pour développer la stratégie de gestion basée sur des stratégies que vous souhaitez afficher ou modifier.  
  
2.  Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .  
  
3.  Cliquez sur le signe plus (+) pour développer **Gestion de la stratégie**.  
  
4.  Cliquez sur le signe plus (+) pour développer le dossier **Stratégies** .  
  
5.  Cliquez avec le bouton droit sur la stratégie que vous souhaitez afficher ou modifier, puis sélectionnez **Propriétés**. Pour plus d’informations sur les options disponibles de la boîte de dialogue **Créer une nouvelle stratégie–***nom_stratégie* , consultez [Boîte de dialogue Créer une nouvelle stratégie ou Ouvrir une stratégie, page Général](../../relational-databases/policy-based-management/create-new-policy-or-open-policy-dialog-box-general-page.md) ou [Boîte de dialogue Créer une nouvelle stratégie ou Ouvrir une stratégie, page Description](../../relational-databases/policy-based-management/create-new-policy-or-open-policy-dialog-box-description-page.md).  
  
6.  Lorsque vous avez terminé, cliquez sur **OK**.  
  
##  <a name="TsqlProcedure"></a> Utilisation de Transact-SQL  
  
#### <a name="to-view-a-policys-properties"></a>Pour afficher les propriétés d'une stratégie  
  
1.  Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.  
  
3.  Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       execution_mode,  
       description,  
       is_enabled,  
       job_id  
    FROM syspolicy_policies;  
    GO  
    ```  
  
 Pour plus d’informations, consultez [syspolicy_policies &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/syspolicy-policies-transact-sql.md).  
  
  

