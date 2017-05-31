---
title: "Supprimer une procédure stockée | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-stored-Procs
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- removing stored procedures
- stored procedures [SQL Server], deleting
- deleting stored procedures
ms.assetid: 232dbf4d-392a-406f-af3a-579518cd8e46
caps.latest.revision: 26
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: d9f9d65d2521299d34188897fbbf5675b5c9eea4
ms.contentlocale: fr-fr
ms.lasthandoff: 04/11/2017

---
# <a name="delete-a-stored-procedure"></a>Supprimer une procédure stockée
    
##  <a name="Top"></a> Cette rubrique explique comment supprimer une procédure stockée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
-   **Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)  
  
-   **To delete a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Avant de commencer  
  
###  <a name="Restrictions"></a> Limitations et restrictions  
 La suppression d'une procédure peut entraîner l'échec des scripts et des objets dépendants quand ceux-ci n'ont pas été mis à jour pour refléter la suppresion de la procédure. Cependant, si vous créez une nouvelle procédure ayant le même nom et les mêmes paramètres pour remplacer celle qui a été supprimée, les autres objets qui y font référence pourront s'exécuter correctement. Pour plus d’informations, consultez [Afficher les dépendances d’une procédure stockée](../../relational-databases/stored-procedures/view-the-dependencies-of-a-stored-procedure.md).  
  
###  <a name="Security"></a> Sécurité  
  
####  <a name="Permissions"></a> Autorisations  
 Exige l'autorisation ALTER sur le schéma auquel appartient la procédure ou l'autorisation CONTROL sur la procédure.  
  
##  <a name="Procedures"></a> Pour supprimer une procédure stockée  
 Vous pouvez utiliser l'un des éléments suivants :  
  
-   [SQL Server Management Studio](#SSMSProcedure)  
  
-   [Transact-SQL](#TsqlProcedure)  
  
###  <a name="SSMSProcedure"></a> Utilisation de SQL Server Management Studio  
 **Pour supprimer une procédure dans l'Explorateur d'objets**  
  
1.  Dans l’Explorateur d’objets, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.  
  
2.  Développez **Bases de données**, développez la base de données à laquelle appartient la procédure, puis développez **Programmabilité**.  
  
3.  Développez **Procédures stockées**, cliquez avec le bouton droit sur la procédure à supprimer, puis sélectionnez **Supprimer**.  
  
4.  Pour afficher les objets qui dépendent de la procédure, cliquez sur **Afficher les dépendances**.  
  
5.  Vérifiez que la procédure correcte est sélectionnée, puis cliquez sur **OK**.  
  
6.  Supprimez les références à la procédure à partir de tous les objets et scripts dépendants.  
  
###  <a name="TsqlProcedure"></a> Utilisation de Transact-SQL  
 **Pour supprimer une procédure dans l'Éditeur de requête**  
  
1.  Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.  
  
2.  Développez **Bases de données**, développez la base de données à laquelle appartient la procédure, ou, dans la barre d'outils, sélectionnez la base de données dans la liste des bases de données disponibles.  
  
3.  Dans le menu Fichier, cliquez sur **Nouvelle requête**.  
  
4.  Obtient le nom de la procédure stockée à supprimer dans la base de données active. Dans l'Explorateur d'objets, développez **Programmabilité** , puis **Procédures stockées**. Sinon, dans l'éditeur de requête, exécutez l'instruction suivante.  
  
    ```tsql  
    SELECT name AS procedure_name   
        ,SCHEMA_NAME(schema_id) AS schema_name  
        ,type_desc  
        ,create_date  
        ,modify_date  
    FROM sys.procedures;  
    ```  
  
5.  Copiez et collez l'exemple suivant dans l'éditeur de requête et insérez un nom de procédure stockée à supprimer de la base de données active.  
  
    ```tsql  
    DROP PROCEDURE <stored procedure name>;  
    GO  
    ```  
  
6.  Supprimez les références à la procédure à partir de tous les objets et scripts dépendants.  
  
## <a name="see-also"></a>Voir aussi  
 [Créer une procédure stockée](../../relational-databases/stored-procedures/create-a-stored-procedure.md)   
 [Modifier une procédure stockée](../../relational-databases/stored-procedures/modify-a-stored-procedure.md)   
 [Renommer une procédure stockée](../../relational-databases/stored-procedures/rename-a-stored-procedure.md)   
 [Afficher la définition d'une procédure stockée](../../relational-databases/stored-procedures/view-the-definition-of-a-stored-procedure.md)   
 [Afficher les dépendances d'une procédure stockée](../../relational-databases/stored-procedures/view-the-dependencies-of-a-stored-procedure.md)   
 [DROP PROCEDURE &#40;Transact-SQL&#41;](../../t-sql/statements/drop-procedure-transact-sql.md)  
  
  
