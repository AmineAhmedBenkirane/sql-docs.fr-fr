---
title: "Supprimer une version (Master Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "master-data-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "versions [Master Data Services], suppression"
  - "suppression de versions [Master Data Services]"
ms.assetid: 2a4eeffe-8379-4744-ad44-c27d8c8ac9a8
caps.latest.revision: 6
author: "sabotta"
ms.author: "carlasab"
manager: "jhubbard"
caps.handback.revision: 6
---
# Supprimer une version (Master Data Services)
  Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], supprimez une version lorsque vous êtes sûr de ne plus avoir besoin des données de référence qui lui sont associées. Après avoir supprimé une version, vous ne pouvez pas récupérer les données de référence associées.  
  
> [!WARNING]  
>  Si un modèle a une seule version et que vous la supprimez, le modèle devient inutilisable.  
  
## Conditions préalables  
 Pour effectuer cette procédure :  
  
-   Vous devez avoir l'autorisation d'afficher la vue mdm.viw_SYSTEM_SCHEMA_VERSION et d'exécuter la procédure stockée mds.udpVersionDelete dans la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]. Pour plus d’informations, consultez [Sécurité de l’objet de base de données &#40;Master Data Services&#41;](../master-data-services/database-object-security-master-data-services.md).  
  
### Pour supprimer une version  
  
1.  Ouvrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] et connectez-vous à l’instance [!INCLUDE[ssDE](../includes/ssde-md.md)] pour votre base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].  
  
2.  Ouvrez la vue mdm.viw_SYSTEM_SCHEMA_VERSION.  
  
3.  Recherchez la version du modèle que vous souhaitez supprimer et copiez la valeur dans le champ **ID**.  
  
4.  Créez une requête.  
  
5.  Tapez le texte suivant, en remplaçant *ID_version* par la valeur copiée à l’étape 2.  
  
    ```  
    EXEC [mdm].[udpVersionDelete] @Version_ID='version_ID'  
    ```  
  
6.  Exécute la requête.  
  
    > [!NOTE]  
    >  Vous devrez peut-être attendre quelques minutes avant que l'application Web ne reflète la modification.  
  
## Voir aussi  
 [Versions &#40;Master Data Services&#41;](../master-data-services/versions-master-data-services.md)   
 [Copier une version &#40;Master Data Services&#41;](../master-data-services/copy-a-version-master-data-services.md)  
  
  