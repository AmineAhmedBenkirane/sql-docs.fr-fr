---
title: "Réinitialisation de mot de passe (système de plateforme Analytique)"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: analytics-platform-system
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: 
ms.technology: mpp-data-warehouse
ms.custom: 
ms.date: 01/05/2017
ms.reviewer: na
ms.suite: sql
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a0f808fc-e120-430b-b6c9-11f2b1c90bf3
caps.latest.revision: "26"
ms.openlocfilehash: 5b342aca4498816e59e0fafcb882c5c039fed501
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="password-reset"></a>Redéfinition du mot de passe
Le **mot de passe réinitialisé** page permet de modifier le mot de passe pour les comptes d’administrateur utilisé par le système de plateforme d’Analytique.  
  
> [!WARNING]  
> Utilisez toujours la **Configuration Manager** pour mettre à jour le mot de passe administrateur de domaine appliance. Autres méthodes ne peuvent pas mettre à jour tous les composants du système de plateforme Analytique et peut entraîner des problèmes d’accès au matériel.  
  
Lorsque l’application est remise, vous obtenez les mots de passe du système de plateforme Analytique. Toujours modifier les mots de passe pour les nouvelles valeurs lorsque vous prenez la responsabilité de votre solution. Il existe trois mots de passe pour mettre à jour. Les mots de passe n’ont pas le même que l’autre.  
  
**F <*xxxx*> \Administrator**  
Le **administrateur** du domaine d’application.  
  
**. \Administrator**  
Local **administrateur** compte sur les ordinateurs qui hébergent les machines virtuelles.  
  
> [!IMPORTANT]  
> Pour le dispositif de la mise à jour 1, **Configuration Manager** ne modifie pas correctement le mot de passe des comptes d’administrateur local dans l’ensemble de la PDW VM. Si cela est nécessaire, contactez Microsoft pour obtenir des instructions supplémentaires.  
  
**association de sécurité**  
Le **sa** dans SQL Server. **sa** est un membre de la **sysadmin** rôle serveur fixe et est un administrateur de SQL Server. Le mot de passe de la **sa** connexion peut également être modifiée à l’aide de la **ALTER LOGIN** instruction.  
  
## <a name="password-requirements"></a>Exigences de mot de passe  
Les informations d’identification d’administrateur de domaine et les informations d’identification administrateur de système respectent les stratégies de force de mot de passe pour chaque type d’informations d’identification. Lorsque vous modifiez les informations d’identification d’administrateur de domaine, le nouveau mot de passe est mis à jour au domaine quand cela est nécessaire dans l’ensemble de SQL Server PDW.  
  
> [!IMPORTANT]  
> SQL Server PDW ne prend pas en charge le signe dollar (**$**) dans l’administrateur de domaine ou les mots de passe d’administrateur local. Les caractères **^ % &** sont autorisés dans les mots de passe, mais PowerShell considère comme des caractères spéciaux. Si aucun de ces caractères sont utilisés dans les mots de passe pour l’administrateur système ou SQL Server**sa** comptes (le **AdminPassword** et **PdwSAPassword** paramètres lors de la le programme d’installation) puis le programme d’installation, y compris d’installation, mise à niveau, REPLACENODE et mise à jour corrective, échoue. Pour garantir une mise à niveau lorsque les mots de passe actuelles contient des caractères non pris en charge, modifier ces mots de passe afin qu’ils ne contiennent pas ces caractères avant d’exécuter la mise à niveau. Une fois la mise à niveau terminée, vous pouvez définir ces mots de passe vers leurs valeurs d’origine. Pour plus d’informations sur les exigences de mot de passe, consultez [ALTER LOGIN](../t-sql/statements/alter-login-transact-sql.md).  
  
## <a name="to-reset-a-password"></a>Pour réinitialiser un mot de passe  
  
1.  Se connecter sur le nœud de contrôle et lancez la **Configuration Manager** (**dwconfig.exe**). Pour plus d’informations, consultez [lance le Gestionnaire de Configuration &#40; Système de plateforme Analytique &#41; ](launch-the-configuration-manager.md).  
  
2.  Dans le volet gauche de la **Configuration Manager**, cliquez sur **réinitialisation de mot de passe**.  
  
3.  Sélectionnez le type d’administrateur à partir de la **compte** menu déroulant, puis entrez le nouveau mot de passe dans le **mot de passe** et **confirmer le mot de passe** boîtes. Cliquez sur **appliquer** pour enregistrer vos modifications.  
  
    Modifications apportées à ces comptes n’affectent pas les sessions actives, mais seront appliquées à la prochaine tentative d’ouverture de session pour chaque utilisateur.  
  
    ![Mot de passe SQL Server DWConfig](./media/password-reset/SQL_Server_PDW_DWConfig_TopPW.png "SQL_Server_PDW_DWConfig_TopPW")  
  
## <a name="see-also"></a>Voir aussi  
[Mot de passe administrateur pour ouvrir une session sur les nœuds AD dans les Services d’annuaire restaurer le Mode &#40; mode DSRM &#41; &#40; Système de plateforme Analytique &#41;](set-admin-password-for-logging-on-to-ad-nodes-in-directory-services-restore-mode.md)  
[Lancez le Gestionnaire de Configuration &#40; Système de plateforme Analytique &#41;](launch-the-configuration-manager.md)  
  
