---
title: "Installer et configurer la recherche s&#233;mantique | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-search"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "recherche sémantique [SQL Server], installation"
  - "recherche sémantique [SQL Server], configuration"
ms.assetid: 2cdd0568-7799-474b-82fb-65d79df3057c
caps.latest.revision: 31
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 28
---
# Installer et configurer la recherche s&#233;mantique
  Décrit les conditions préalables à une recherche sémantique statistique, ainsi que la procédure d'installation ou de vérification de ces conditions.  
  
## Installation de la recherche sémantique  
  
###  <a name="HowToCheckInstalled"></a> Procédure : vérifier si la recherche sémantique est installée  
 Interrogez la propriété **IsFullTextInstalled** de la fonction de métadonnées [SERVERPROPERTY &#40;Transact-SQL&#41;](../../t-sql/functions/serverproperty-transact-sql.md).  
  
 Une valeur de retour de 1 indique que la recherche en texte intégral et la recherche sémantique sont installées ; une valeur de retour de 0 indique qu'elles ne le sont pas.  
  
```tsql  
SELECT SERVERPROPERTY('IsFullTextInstalled');  
GO  
```  
  
###  <a name="BasicsSemanticSearch"></a> Procédure : pour installer la recherche sémantique  
 Pour installer la recherche sémantique, sélectionnez **Extraction en texte intégral et extraction sémantique de recherche** dans la page **Fonctionnalités à installer** pendant l’installation.  
  
 La recherche sémantique statistique dépend de la recherche en texte intégral. Ces deux fonctionnalités en option de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont installées ensemble.  
  
## Installation ou suppression de la base de données des statistiques linguistiques de sémantique  
 La recherche sémantique a une dépendance externe supplémentaire qui est appelée base de données des statistiques linguistiques de sémantique. Cette base de données contient les modèles linguistiques statistiques requis par la recherche sémantique. Une base de données unique des statistiques linguistiques de sémantique contient les modèles linguistiques de toutes les langues prises en charge pour l'indexation sémantique.  
  
###  <a name="HowToCheckDatabase"></a> Procédure : vérifier si la base de données des statistiques linguistiques de sémantique est installée  
 Interrogez l’affichage catalogue [sys.fulltext_semantic_language_statistics_database &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-fulltext-semantic-language-statistics-database-transact-sql.md).  
  
 Si la base de données des statistiques linguistiques de sémantique est installée et inscrite pour l'instance, les résultats de la requête contiennent une seule ligne d'informations sur la base de données.  
  
```tsql  
SELECT * FROM sys.fulltext_semantic_language_statistics_database;  
GO  
```  
  
###  <a name="HowToInstallModel"></a> Procédure : installer, attacher et inscrire la base de données des statistiques linguistiques de sémantique  
 La base de données des statistiques linguistiques de sémantique n'est pas installée par le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Pour installer la base de données des statistiques linguistiques de sémantique comme une condition préalable à l'indexation sémantique, procédez comme suit :  
  
 **1. Installez la base de données des statistiques linguistiques de sémantique.**  
 1.  Localisez la base de données des statistiques linguistiques de sémantique sur le support d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou téléchargez-la sur le Web.  
  
    -   Localisez le package Windows Installer nommé **SemanticLanguageDatabase.msi** sur le support d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
    -   Téléchargez le package d'installation à partir de la page [Microsoft® SQL Server® 2014 Semantic Language Statistics](http://go.microsoft.com/fwlink/?LinkID=296743) du centre de téléchargement [!INCLUDE[msCoName](../../includes/msconame-md.md)] .  
  
2.  Exécutez le package Windows Installer **SemanticLanguageDatabase.msi** pour extraire la base de données et le fichier journal.  
  
     Vous pouvez éventuellement modifier le répertoire de destination. Par défaut, le programme d’installation extrait les fichiers dans un sous-dossier nommé **Microsoft Semantic Language Database** du dossier Program Files. Le fichier MSI contient un fichier de base de données et un fichier journal compressés.  
  
3.  Déplacez le fichier de base de données et le fichier journal extraits vers l'emplacement approprié dans le système de fichiers.  
  
     Si vous laissez les fichiers dans leur emplacement par défaut, il n'est pas possible d'extraire une autre copie de la base de données pour une autre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
> [!IMPORTANT]  
>  Lorsque la base de données des statistiques linguistiques de sémantique est extraite, des autorisations limitées sont assignées au fichier de base de données et au fichier journal à l'emplacement par défaut dans le système de fichiers. Par conséquent, vous pouvez ne pas avoir l'autorisation d'attacher la base de données si vous la laissez dans l'emplacement par défaut. Si une erreur se produit lorsque vous essayez d'attacher la base de données, déplacez les fichiers, ou vérifiez et corrigez les autorisations du système de fichiers s'il y a lieu.  
  
 **2. Attachez la base de données des statistiques linguistiques de sémantique.**  
 Attachez la base de données à l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ou en appelant [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](../../t-sql/statements/create-database-sql-server-transact-sql.md) avec la syntaxe **FOR ATTACH**. Pour plus d’informations, consultez [Attacher et détacher une base de données &#40;SQL Server&#41;](../../relational-databases/databases/database-detach-and-attach-sql-server.md).  
  
 Par défaut, le nom de la base de données est **semanticsdb**. Vous pouvez éventuellement donner un nom différent à la base de données lorsque vous l'attachez. Vous devez spécifier ce nom lorsque vous inscrivez la base de données à l'étape suivante.  
  
```tsql  
CREATE DATABASE semanticsdb  
            ON ( FILENAME = 'C:\Microsoft Semantic Language Database\semanticsdb.mdf' )  
            LOG ON ( FILENAME = 'C:\Microsoft Semantic Language Database\semanticsdb_log.ldf' )  
            FOR ATTACH;  
GO  
```  
  
 Cet exemple de code suppose que vous avez déplacé la base de données de son emplacement par défaut vers un nouvel emplacement.  
  
 **3. Inscrivez la base de données des statistiques linguistiques de sémantique.**  
 Appelez la procédure stockée [sp_fulltext_semantic_register_language_statistics_db &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-fulltext-semantic-register-language-statistics-db-transact-sql.md) et fournissez le nom attribué à la base de données lors de son attachement.  
  
```tsql  
EXEC sp_fulltext_semantic_register_language_statistics_db @dbname = N'semanticsdb';  
GO  
```  
  
###  <a name="HowToUnregister"></a> Procédure : pour annuler l'inscription, détacher et supprimer la base de données des statistiques linguistiques de sémantique  
 **Annulez l'inscription de la base de données des statistiques linguistiques de sémantique.**  
 Appelez la procédure stockée [sp_fulltext_semantic_unregister_language_statistics_db &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-fulltext-semantic-unregister-language-statistics-db-transact-sql.md). Vous ne devez pas fournir le nom de la base de données étant donné qu'une instance ne peut avoir qu'une seule base de données des statistiques linguistiques de sémantique.  
  
```tsql  
EXEC sp_fulltext_semantic_unregister_language_statistics_db;  
GO  
```  
  
 **Détachez la base de données des statistiques linguistiques de sémantique.**  
 Appelez la procédure stockée [sp_detach_db &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-detach-db-transact-sql.md) et fournissez le nom de la base de données.  
  
```tsql  
USE master;  
GO  
  
EXEC sp_detach_db @dbname = N'semanticsdb';  
GO  
```  
  
 **Supprimez la base de données des statistiques linguistiques de sémantique.**  
 Après avoir annulé l'inscription de la base de données et l'avoir détachée, vous pouvez simplement supprimer le fichier de base de données. Il n'existe aucun programme de désinstallation ni aucune entrée dans **Programmes et fonctionnalités** dans le Panneau de configuration.  
  
###  <a name="reqinstall"></a> Exigences et restrictions pour installer et supprimer la base de données des statistiques linguistiques de sémantique  
  
-   Vous ne pouvez attacher et inscrire une base de données des statistiques linguistiques de sémantique que sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
     Chaque instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur un seul ordinateur requiert une copie physique distincte de la base de données des statistiques linguistiques de sémantique. Attachez une copie à chaque instance.  
  
-   Vous ne pouvez pas détacher une base de données des statistiques linguistiques de sémantique valide et inscrite et la remplacer par une base de données arbitraire du même nom. Vous risqueriez sinon de provoquer l'échec du remplissage de l'index actif ou des futurs index.  
  
-   La base de données des statistiques linguistiques de sémantique est en lecture seule. Vous ne pouvez pas personnaliser cette base de données. Si vous modifiez le contenu de la base de données de quelque manière que ce soit, les résultats d'une future indexation sémantique sont non déterministes. Pour restaurer l'état d'origine de ces données, vous pouvez supprimer la base de données modifiée et télécharger et attacher une copie nouvelle et inchangée de la base de données.  
  
-   Il est possible de détacher ou de supprimer la base de données des statistiques linguistiques de sémantique. S'il existe des opérations d'indexation actives qui comportent des verrous de lecture sur la base de données, l'opération de détachement ou de suppression échoue ou expire. Ce comportement est cohérent avec celui existant. Une fois la base de données supprimée, les opérations d'indexation sémantique échouent.  
  
## Installation de la prise en charge facultative de nouveaux types de documents  
  
###  <a name="office"></a> Procédure : installer les derniers filtres pour Microsoft Office et d'autres types de documents Microsoft  
 Cette version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installe les analyseurs lexicaux et les générateurs de formes dérivées [!INCLUDE[msCoName](../../includes/msconame-md.md)] les plus récents, mais n'installe pas les filtres les plus récents pour les documents [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office et d'autres types de documents [!INCLUDE[msCoName](../../includes/msconame-md.md)] . Ces filtres sont nécessaires pour l'indexation des documents créés avec les versions récentes de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office et d'autres applications [!INCLUDE[msCoName](../../includes/msconame-md.md)] . Pour télécharger les filtres les plus récents, consultez [Microsoft Office 2010 Filter Packs](http://go.microsoft.com/fwlink/?LinkId=218293).  
  
  