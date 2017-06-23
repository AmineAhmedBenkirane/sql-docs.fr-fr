---
title: SQL Server Management Studio - Journal des modifications (SSMS) | Microsoft Docs
ms.custom: 
ms.date: 01/30/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3dc76cc1-3b4c-4719-8296-f69ec1b476f9
caps.latest.revision: 72
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 470e6c83318eaf8eb579d053f65b5353862eb4c7
ms.openlocfilehash: 23e304e52967d5d16672872d8d5712f26ef8c610
ms.contentlocale: fr-fr
ms.lasthandoff: 06/23/2017

---
# <a name="sql-server-management-studio---changelog-ssms"></a>SQL Server Management Studio - Journal des modifications (SSMS)

## <a name="ssms-171-release"></a>Version de SSMS 17.1
Disposition générale | Numéro de build : 14.0.17119.0

### <a name="enhancements"></a>Améliorations

- Profileur : Aide > à propos affiche maintenant les (par ex. 17.1) du numéro de version release
- Analyse les utilisateurs des services peuvent actualiser les informations d’identification pour les sources de données pour 1200 les modèles TM et ci-dessus dans le menu contextuel sur la source de données
- SSIS intégrés signale maintenant afficher des journaux à partir de l’exécution de montée en puissance parallèle SSIS dans CTP 2.1
- Application de gestion de la montée en puissance parallèle SSIS
  - Afficher les informations de base principale de la montée en puissance parallèle.
  - Ajouter facilement un processus de travail pour le déploiement avec montée en charge.
  - Afficher tous les traitements de montée en puissance parallèle et les informations de base et peuvent également activer ou désactiver les facilement.

### <a name="bug-fixes"></a>Correctifs de bogues
- Always On :
  - Correction d’un problème où les propriétés d’un réplica de disponibilité a été toujours affiché comme mode de « Basculement automatique » pour les groupes de disponibilité WSFC.
  - Correction d’un problème dans lequel la liste de routage en lecture seule a été remplacée lors de la mise à jour le groupe de disponibilité
- Always Encrypted : résolution d’un problème où journal généré est absent du fichier les informations générées par DacFx.
- ShowPlan : fixe dans un problème où l’interface utilisateur était affiché toujours l’attribut de type de jointure réel pour les opérateurs de jointure non adaptatif.
- Programme d’installation :
  - Correction d’un problème où SSMS 17,0 a été avec rupture SSDT Visual Studio 2013 [se connecter élément 3133479]
  - Correction d’un problème où cliquant sur « Redémarrer » à la fin du programme d’installation a été pas le redémarrage de l’ordinateur
- Script : empêcher temporairement SSMS à partir de la suppression accidentelle des objets de base de données Azure lors de la suppression de script en désactivant cette option.  Correctif approprié sera dans une prochaine version de SSMS.
- L’Explorateur d’objets : résolution d’un problème où nœud « Bases de données » a été développé pas lorsqu’il est connecté à une base de données Azure créé à l’aide de « Copier en tant que »

## <a name="ssms-170-release"></a>Version de SSMS 17,0
Disposition générale | Numéro de build : 14.0.17099.0

### <a name="enhancements"></a>Améliorations 

- Package de mise à niveau et de Windows Software Update Services (WSUS) 
    - Les versions futures 17.X incluent un plus petit package de mise à jour cumulative 
  - Le package de mise à jour sera également publié sur le catalogue WSUS  
- Mises à jour des icônes
    - Icônes ont été mis à jour pour être cohérent avec des icônes de Shell Visual Studio fourni et prend en charge des résolutions élevées
    - Nouvelles icônes de programme SSMS et Profiler permettant de différencier les versions 16.X et 17.X
- Module SQL PowerShell
  - Module SQL Server PowerShell supprimés à partir de SSMS et est désormais fourni via PowerShell gallery (PowerShell 5.0 maintenant obligatoire pour prendre en charge le contrôle de version de module)
  - Diverses améliorations apportées à la « présentation » (mise en forme) de certains objets SMO (par exemple, les bases de données affichent maintenant la taille et la quantité d’espace disponible et tables afficher ligne nombre et l’espace de l’utilisation)
  - Colorisation ajoutée lors de l’invite de commandes PowerShell est appelé à partir du menu « Démarrer PowerShell » dans l’Explorateur d’objets
  - Les paramètres ClusterType et -RequiredCopiesToCommit ont été ajoutés aux applets de commande AG (New-SqlAvailabilityGroup, Join-SqlAvailabilityGroup, et les applets de commande Set-SqlAvailabilityGroup)
  - Les paramètres - ActiveDirectoryAuthority et - AzureKeyVaultResourceId ont été ajoutés à l’applet de commande Add-SqlAzureAuthenticationContext
  - Revoke-SqlAvailabilityGroupCreateAnyDatabase ajouté, Grant-SqlAvailabilityGroupCreateAnyDatabase et applets de commande Set-SqlAvailabilityReplicaRoleToSecondary
  - Paramètre - SeedingMode ajouté aux applets de commande Set-SqlAvailabilityReplica et New-SqlAvailabilityReplica
  - Paramètre - ConnectionString ajouté à Get-SqlDatabase
- SQL Server sur Linux
    - Améliorations d’ordre général et correctifs pour la copie des journaux de transaction
  - Prise en charge des chemins d’accès Linux natifs attacher, sauvegarde et restauration de base de données
  - Prise en charge des chemins d’accès de Linux natifs pour le dossier de destination du journal d’audit
- Analysis Services
  - Fenêtre de requête DAX :
    - Dans l’éditeur de mise en correspondance des parenthèses
    - DÉFINIR les mesures et définir les VAR prise en charge de syntaxe
    - Améliorations apportées à Intellisense assorties
  - Authentification universelle
    - Permet aux utilisateurs de spécifier qu'un nom d’utilisateur et aucun mot de passe et la boîte de dialogue de connexion Azure gère la connexion
  - Intégration de PQ SSMS : 
    - Écriture de scripts de travaux de sources de données structurées 
    - Affichage et modification de sources de données structurées dans l’interface utilisateur PQ
- Nouveau modèle « Ajouter une contrainte Unique »
- Showplan
    - Affichage du maximum au lieu de la somme pour les threads dans la fenêtre Propriétés
    - Affichage des propriétés du nouvel opérateur d’allocation de mémoire
    - Activation du bouton Modifier la requête dans les statistiques des requêtes dynamiques
    - Prise en charge de l’exécution entrelacée
  - Nouvelle option pour « Analyser Plan d’exécution réel »
  - Améliorations générales pour la comparaison du plan d’exécution
  - A introduit une fonctionnalité dans la fonction de comparaison de plan de requête pour rechercher des différences significatives dans l’Estimation de la cardinalité entre les nœuds correspondants de deux plans de requête et effectuer une analyse de base des causes possibles
- Suppression du gestionnaire de configuration à partir de l’Explorateur de serveurs inscrits
- Activation de la lecture des journaux d’audit à partir du stockage d’objets blob Azure
- Un paramétrage a été ajouté pour Always Encrypted. Reportez-vous à [cette page](https://blogs.msdn.microsoft.com/sqlsecurity/2016/12/13/parameterization-for-always-encrypted-using-ssms-to-insert-into-update-and-filter-by-encrypted-columns/) pour plus de détails 
- La connexion d’authentification universelle AAD à Azure SQL Database prend en charge les ID de locataire personnalisés 
- La génération de scripts pour Azure SQL Database inclut désormais le texte intégral, les règles et la base de données
- Correctifs de la personnalisation dans les écrans de démarrage pour SSMS et le profileur
- Suppression dans SSMS de l’interface utilisateur du point de contrôle de l’utilitaire
- SSMS peut maintenant créer les bases de données SQL Azure « PremiumRS » edition
- Groupes de disponibilité AlwaysOn
  - Ajouter la prise en charge pour les nouveaux types de cluster : externe et NONE
    - Ajouter la prise en charge de SQL Server sur Linux
    - Ajouter l’amorçage automatique comme une option de synchronisation initiale des données
    - Fixe des erreurs, par exemple, les URL de point de terminaison manipulation, actualisation de la base de données et la disposition de l’interface utilisateur
    - Supprimé un réplica Windows Azure les fonctionnalités associées
  - Amélioration d’IntelliSense pour plusieurs mots clés de groupe de disponibilité
- Moniteur d'activité
  - Nouveau volet de « Moniteur d’activité » ajouté à la fenêtre Sortie de SSMS
  - Modifié le message d’erreur de délai de connexion à consigner des informations de sortie de fenêtre au lieu d’un message contextuel
  - Suppression vide de graphique (graphique 5) dans la section vue d’ensemble
  - Ajouté « (en pause) » au titre de la vue d’ensemble si la collecte de données du moniteur d’activité est suspendue.
  - Graphique aux tables de nœud et le bord du graphique de SQL Server - nouvelles icônes pour les tables de nœud et le bord du graphique - seront affichées sous le dossier Tables de graphique - modèles pour créer graphiquement nœud et bord tables disponibles
- Mode de présentation
    - 3 nouvelles tâches disponibles via le menu de lancement rapide (CTRL-Q)
    - PresentOn - Activation du mode de présentation
    - PresentEdit - Modification de la taille des polices pour le mode de présentation.  « Police Éditeur de texte » pour l’éditeur de requête.  « Police Environnement » pour les autres composants.
    - RestoreDefaultFonts - Rétablissement des paramètres par défaut.
    - *Remarque : il n’existe actuellement aucune commande PresentOff pour l’instant.  Utiliser RestoreDefaultFonts pour désactiver le mode de présentation*

### <a name="bug-fixes"></a>Correctifs de bogues

- Correction d’un problème où le SSMS est tombé en panne lorsque le défile du plan d’exécution via surfacebook tactile
- Correction d’un problème où SSMS se bloque pendant un long fois lors de la mise en route les propriétés d’une base de données est restaurée ou hors connexion 
- Correction d’un problème où « Visionneuse d’aide » impossible dans les versions RC
- Correction d’un problème où les éléments de la « Gestion des Plans de boîte à outils tâches » peuvent être manquantes dans SSMS.
- Correction d’un problème dans SSMS, où l’utilisateur n’a pas pu réduire une base de données lorsque le nom de la base de données contenait des accolades. [Article de Microsoft Connect](https://connect.microsoft.com/SQLServer/feedback/details/3122618)
- Correction d’un problème où SSMS a essayé de script de la suppression d’un Azure base de données a été réellement à l’origine la suppression de la base de données. [Article de Microsoft Connect](http://connect.microsoft.com/SQLServer/feedback/details/3131458/)
- Correction d’un problème où les valeurs par défaut n’ont pas fait l’objet d’un script pour les types de tables définis par l’utilisateur. [Article de Microsoft Connect](https://connect.microsoft.com/SQLServer/feedback/details/3119027)
- Autre série d’améliorations des performances liées au menu contextuel des index. [Article de Microsoft Connect](https://connect.microsoft.com/SQLServer/feedback/details/3120783)
- Correction du problème qui provoquait un scintillement excessif lorsque des index manquants du plan d’exécution faisaient l’objet d’un pointage de la souris. [Article de Microsoft Connect](https://connect.microsoft.com/SQLServer/feedback/details/3118510)
- Correction d’un problème où SSMS prenait la base de données hors connexion lors de l’écriture de scripts [Article de Microsoft Connect](https://connect.microsoft.com/SQLServer/feedback/details/3118550)
- Divers correctifs liés à l’interface utilisateur sur les versions localisées (dans une langue que l’anglais) de SSMS.
- Correction du problème où le nœud de « Always Encrypted Keys » était manquant lors du ciblage de SQL 2016 SP1 Édition Standard.
- Always Encrypted
    - Activation incorrecte du menu Always Encrypted lors du ciblage de SQL 2016 RTM Édition Standard ou de n’importe quel serveur SQL 2014 (et versions antérieures)
    - Correction d’un problème où IntelliSense signale une erreur lors de l’utilisation de la syntaxe CREATE ou ALTER
    - Correction du problème où le chiffrement échoue si CMK/CEK contient des caractères qui devraient être ignorés, par exemple mis entre crochets
    - En cas d’exception liée à une mémoire insuffisante dans SSMS, l’utilisateur reçoit une erreur proposant d’utiliser le module PowerShell (64 bits) natif.
    - Correction du problème lié à l’échec de l’Assistant AE si l’utilisateur a utilisé des abonnements de responsable de groupe de ressources au lieu d’abonnements Azure classiques
    - Correction du problème où l’Assistant AE affiche une erreur incorrecte lorsque l’utilisateur ne détient aucune autorisation dans le cadre de ces abonnements ni aucun coffre de clé Azure.
    - Correction d’un problème de l’Assistant AE où la page de connexion du coffre de clé Azure n’affiche pas les abonnements Azure en présence de plusieurs AAD
    - Correction d’un problème de l’Assistant AE où la page de connexion du coffre de clé Azure n’affiche pas les abonnements Azure pour lesquels l’utilisateur détient une autorisation de lecture
  - Correction d’un problème où les fichiers de ressources ne soit pas chargés correctement, ce qui en résulte dans les messages d’erreur inexact
- Amélioration du contraste des liens hypertexte sur la page Installation de SSMS
- Correction d’un problème lié au non-affichage des nœuds Polybase lors de la connexion à SQL Server Express (2016 SP1)
- Correction d’un problème où SSMS est impossible de modifier le niveau de compatibilité d’une base de données Azure v140
- Amélioration des performances de l’Explorateur d’objets lors du développement de la liste des bases de données Azure [Article de Microsoft Connect](https://connect.microsoft.com/SQLServer/feedback/details/3100675)
- Correction d’un problème où l’élément de menu contextuel Afficher le journal SQL Server apparaît de manière incorrecte pour les types de serveurs non relationnels (AS\RS\IS) 
- Correction d’un problème dans lequel la vérification de la syntaxe d’une requête de partition Analysis Services à l’aide de l’authentification SQL pouvait entraîner un message d’échec de connexion
- Correction d’un problème dans lequel le fait de renommer un modèle tabulaire AS de niveau de compatibilité 1400 d’aperçu pouvait échouer dans SSMS
- Correction d’un problème lié au message « échec de l’opération sur le modèle » qui pouvait se produire après avoir tenté une opération non valide sur le serveur AS dans de rares circonstances et rétablir les modifications locales suite à un échec d’enregistrement sur le modèle
- Correction d’une faute d’orthographe dans la boîte de dialogue contextuelle de synchronisation des bases de données Analysis Services
- Les boîtes de dialogue de sauvegarde/restauration de conteneur se trouvent en dehors de l’écran dans les configurations avec plusieurs moniteurs. 
- La création d’une stratégie de sécurité échoue si le nom de l’objet cible contient le caractère « ] ».
- Le menu « Ouvrir un fichier récent » de SSMS 2016 n’affiche pas les fichiers récemment enregistrés. [Article de Microsoft Connect](https://connect.microsoft.com/SQLServer/feedback/details/3113288/ssms-2016-open-recent-menu-doesnt-show-recently-saved-files)
- Suppression de la réinitialisation des paramètres utilisateur lors de la mise à jour du shell VS.
- Correction d’un problème qui empêchait l’utilisateur d’être en mesure de modifier le niveau de compatibilité de base de données sur SQL Server 2017.
- Les fenêtres de requête utilisant l’authentification universelle AAD ne peuvent pas actualiser la requête au bout d’une heure.
- Suppression dans SSMS de l’interface utilisateur du point de contrôle de l’utilitaire.
- Les connexions d’authentification universelle AAD échouent à interroger des données après l’expiration du jeton initial.
- Impossible de générer des scripts de règles depuis Azure SQL Database vers Azure SQL Database.
- Résolution d’un problème où PowerShell SQL ne pouvait pas se connecter à des instances SQL héritées (2014 et antérieur). [Article de Microsoft Connect](https://connect.microsoft.com/SQLServer/feedback/details/1138754/sql-server-sqlps-powershell-module-fails-connection-to-sql-2012-instance)
- Résolution d’un problème qui provoquait le blocage de SSMS lors d’un échec d’importation des serveurs inscrits.
- Résolution d’un problème qui provoquait le blocage de SSMS si un utilisateur avait certaines autorisations sur une base de données. 
- SSMS - des tables disparaissent de l’aire de conception pendant l’examen des vues. [Article de Microsoft Connect](https://connect.microsoft.com/SQLServer/feedback/details/2946125/ssms-tables-disappears-from-design-surface-while-reviewing-views) 
- La barre de défilement des tables ne permet pas à l’utilisateur de faire défiler le contenu d’une table : seule la flèche haut/bas le permet. Il est également possible de faire défiler le contenu de la table après avoir essayé de faire défiler à l’aide de la barre de défilement, ce qui est un bogue. [Article de Microsoft Connect](
http://connect.microsoft.com/SQLServer/feedback/details/3106561/sql-server-manager-2016-bug-in-design-view) 
- Les icônes ne s’affichent pas pour les serveurs inscrits une fois le nœud racine actualisé.
- Le bouton du script pour créer une base de données sur les serveurs v12 Azure exécute un script, puis affiche le message « Aucune action pour le script ».
- La boîte de dialogue SSMS Se connecter au serveur n’efface pas l’onglet « Propriétés supplémentaires » pour chaque nouvelle connexion.
- Le script de génération de tâches ne génère pas de scripts de création de base de données pour une base de données Azure SQL Database.
- La barre de défilement du Concepteur de vues apparaît désactivée.
- Les chemins de clés AVK d’Always Encrypted n’incluent pas les ID de version.
- Réduction du nombre de requêtes de l’édition du moteur dans la fenêtre de requête. [Article de Microsoft Connect](http://connect.microsoft.com/SQLServer/feedback/details/3113387)
- Les erreurs Always Encrypted provenant de l’actualisation des modules après chiffrement ne sont pas gérées correctement.
- Changement du délai d’expiration de la connexion par défaut pour OLTP et OLAP de 15 à 30 secondes, pour résoudre une classe d’échecs de connexion ignorés. 
- Correction d’un blocage dans SSMS lors du lancement d’un rapport personnalisé. [Article de Microsoft Connect](http://connect.microsoft.com/SQLServer/feedback/details/3118856)
- Résolution d’un problème où « Générer un Script... » échoue pour les bases de données SQL Azure.
- Correction de « Générer un script en tant que » et « Assistant Génération de scripts », qui n’ajoutaient pas de sauts de ligne supplémentaires lors de la génération de scripts pour des objets comme les procédures stockées. [Article de Microsoft Connect](http://connect.microsoft.com/SQLServer/feedback/details/3115850)
- Le fournisseur SQLAS PowerShell : Ajout de la propriété LastProcessed aux dossiers Dimension et MeasureGroup. [Article de Microsoft Connect](http://connect.microsoft.com/SQLServer/feedback/details/3111879)
- Statistiques sur les requêtes en direct : Résolution d’un problème où elles montraient seulement la première requête dans un lot. [Élément de connexion] (http://connect.microsoft.com/SQLServer/feedback/details/3114221)  
- Plan d’exécution de requêtes : Affichage du maximum au lieu de la somme pour les threads dans la fenêtre Propriétés.
- Magasin de requêtes : Ajout d’un nouveau rapport sur les requêtes avec les variation fortes des exécutions.
- Problèmes de performances de l’Explorateur d’objets : [Article de Microsoft Connect](http://connect.microsoft.com/SQLServer/feedback/details/3114074)
    - Le menu contextuel pour les tables se bloque momentanément
    - SSMS est lent quand l’utilisateur clique avec le bouton droit sur un index pour une table (via une connexion (Internet) à distance). 
    - Éviter d’émettre des requêtes sur des tables qui sont triées sur le serveur
- Suppression dans SSMS de l’Assistant Déploiement Azure (pour déployer une base de données sur une machine virtuelle Azure)
- Résolution d’un problème où les index manquants n’étaient pas affichés dans les plans d’exécution dans SSMS [Article de Microsoft Connect](http://connect.microsoft.com/SQLServer/feedback/details/3114194)
- Résolution du problème courant de blocage lors de l’arrêt dans SSMS
- Résolution du problème dans l’Explorateur d’objets, où une erreur se produisait lors de l’affichage du menu contextuel sur les nœuds Polybase | Groupe de scale-out[Article de Microsoft Connect](http://connect.microsoft.com/SQLServer/feedback/details/3115128)
- Résolution d’un problème où SSMS pouvait se bloquer lors d’une tentative d’affichage des autorisations sur une base de données
- Magasin de requêtes : améliorations générales apportées aux éléments du menu contextuel pour les grilles de résultats des rapports du magasin de requêtes
- La configuration d’Always Encrypted pour une table existante échoue avec des erreurs sur des objets non associés. [Article de Microsoft Connect](http://connect.microsoft.com/SQLServer/feedback/details/3103181)
- La configuration d’Always Encrypted pour une base de données existante avec plusieurs schémas ne fonctionne pas. [Élément de connexion] (http://connect.microsoft.com/SQLServer/feedback/details/3109591)
- L’Assistant Colonne chiffrée d’Always Encrypted échoue parce que la base de données contient des vues qui référencent des vues système. [Élément de connexion] (http://connect.microsoft.com/SQLServer/feedback/details/3111925)
- Lors du chiffrement à l’aide d’Always Encrypted, les erreurs provenant de l’actualisation des modules après le chiffrement ne sont pas gérées correctement.
- Résolution du problème de troncation de l’interface utilisateur dans la boîte de dialogue « Nouvelle inscription de serveur »
- Correction de la mise à jour incorrecte par l’interface utilisateur des conditions DMF pour les expressions contenant des valeurs de constante de chaîne incluant des guillemets
- Résolution d’un problème pouvant provoquer le blocage de SSMS lors de l’exécution de rapports personnalisés
- Ajout de l’élément de menu « Exécution dans Scale Out... » au nœud du dossier
- Correction d’un problème avec la fonctionnalité d’adresse de base de données SQL Azure pare-feu liste blanche d’adresses IP
- Fixe à un problème dans SSMS, ce qui a provoqué une référence d’objet ne définie pas exception lors de la modification de la source de partition multidimensionnelle
- Fixe à un problème dans SSMS, ce qui a provoqué une référence d’objet ne définie pas exception lors de la suppression d’un assembly client à partir de multidimensionnel AS server
- Correction d’un problème où la modification du nom d’un tableau 1400 base de données a échoué
- Correction d’un problème avec un niveau de compatibilité 1400 des scripts en tant que source de données tabulaire à partir de la boîte de dialogue de propriétés connexion
- Supprimer l’hypothèse que les tables de modèle de niveau de compatibilité 1400 ont au moins une partition
- CTRL + R bascule maintenant le volet de résultats dans l’éditeur de requête SSMS DAX


## <a name="ssms-1653-release"></a>Version 16.5.3 de SSMS
Disponibilité générale | Numéro de build : 13.0.16106.4

Les problèmes suivants ont été résolus dans cette version :

* Résolution du problème introduit dans SSMS 16.5.2 qui provoquait l’expansion du nœud « Table » quand la table comportait plusieurs colonnes éparses.

* Les utilisateurs peuvent déployer des packages SSIS contenant le Gestionnaire de connexions OData qui connectent une ressource Microsoft Dynamics AX/CRM Online au catalogue SSIS. Pour plus d’informations, consultez [Gestionnaire de connexions OData](https://msdn.microsoft.com/library/dn584133.aspx).

* La configuration d’Always Encrypted sur une table existante échoue avec des erreurs sur des objets non associés. [Microsoft Connect - ID 3103181](https://connect.microsoft.com/SQLServer/feedback/details/3103181/setting-up-always-encrypted-on-an-existing-table-fails-with-errors-on-unrelated-objects)

* La configuration d’Always Encrypted pour une base de données existante avec plusieurs schémas ne fonctionne pas. [Microsoft Connect - ID 3109591](https://connect.microsoft.com/SQLServer/feedback/details/3109591/sql-server-2016-always-encrypted-against-existing-database-with-multiple-schemas-doesnt-work)

* L’Assistant Colonne chiffrée d’Always Encrypted échoue parce que la base de données contient des vues qui référencent des vues système. [Microsoft Connect - ID 3111925](https://connect.microsoft.com/SQLServer/feedback/details/3111925/sql-server-2016-always-encrypted-encrypted-column-wizard-failed-task-failed-due-to-following-error-cannot-save-package-to-file-the-model-has-build-blocking-errors)

* Lors du chiffrement à l’aide d’Always Encrypted, les erreurs provenant de l’actualisation des modules après le chiffrement ne sont pas gérées correctement.

* Le menu *Ouvrir un fichier récent* n’affiche pas les fichiers récemment enregistrés. [Microsoft Connect - ID 3113288](https://connect.microsoft.com/SQLServer/feedback/details/3113288/ssms-2016-open-recent-menu-doesnt-show-recently-saved-files)

* SSMS est lent quand l’utilisateur clique avec le bouton droit sur un index pour une table (via une connexion (Internet) à distance). [Microsoft Connect - ID 3114074](https://connect.microsoft.com/SQLServer/feedback/details/3114074/ssms-slow-when-right-clicking-an-index-for-a-table-over-a-remote-internet-connection)
 
* Correction d’un problème avec la barre de défilement de SQL Designer. [Microsoft Connect - ID 3114856](http://connect.microsoft.com/SQLServer/feedback/details/3114856/bug-in-scrollbar-on-sql-desginer-in-ssms-2016)

* Le menu contextuel pour les tables se bloque momentanément 
 
* Il peut arriver que SSMS lève des exceptions dans le moniteur d’activité et se bloque. [Microsoft Connect - ID 697527](https://connect.microsoft.com/SQLServer/feedback/details/697527/)

* SSMS 2016 se bloque avec l’erreur « Le processus a été arrêté en raison d’une erreur interne dans le runtime .NET à l’adresse IP 71AF8579 (71AE0000) avec le code de sortie 80131506 »


## <a name="ssms-1651-release"></a>Version 16.5.1 de SSMS
Disponibilité générale | Numéro de build : 13.0.16100.1

* Correction d’un problème où Invoke-Sqlcmd insère par erreur plusieurs lignes lors d’une contrainte de validation. [Article Microsoft Connect n°811560](https://connect.microsoft.com/SQLServer/feedback/details/811560)

* Correction d’un problème où les versions en langue autre que le français ne fonctionnent pas complètement lors de la création de groupes de disponibilité.

* Correction d’un problème où un clic sur le fichier XML du plan de requête n’ouvre pas l’interface utilisateur SSMS appropriée.


## <a name="ssms-165-release"></a>Version 16.5 de SSMS
Disponibilité générale | Numéro de build : 13.0.16000.28

* Résolution d’un problème : un blocage peut se produire quand une base de données avec un nom de la table contenant « ;: » a été activée.
* Résolution d’un problème : les modifications apportées à la page Modèle dans la fenêtre des propriétés de base de données tabulaire AS génèrent un script de la définition d’origine. 
[Élément Microsoft Connect : 3080744](https://connect.microsoft.com/SQLServer/feedback/details/3080744) 
* Correction du problème lié à l’ajout de fichiers temporaires à la liste « Fichiers récents ».  
[Élément Microsoft Connect : 2558789](https://connect.microsoft.com/SQLServer/feedback/details/2558789)
* Résolution du problème : l’élément de menu « Gérer la Compression » est désactivé pour les nœuds de la table utilisateur dans l’arborescence de l’Explorateur d’objets.  
[Élément Microsoft Connect : 3104616](https://connect.microsoft.com/SQLServer/feedback/details/3104616)

* Résolution du problème : l’utilisateur ne peut pas définir la taille de police pour l’Explorateur d’objets, l’Explorateur de serveurs inscrits, l’Explorateur de modèle ainsi que pour les détails de l’Explorateur d’objets. La police pour les explorateurs utilise la police de l’environnement.  
[Élément Microsoft Connect : 691432](https://connect.microsoft.com/SQLServer/feedback/details/691432)

* Résolution du problème : SSMS se reconnecte toujours à la base de données par défaut quand la connexion est perdue.  
[Élément Microsoft Connect Item : 3102337](https://connect.microsoft.com/SQLServer/feedback/details/3102337)

* Résolution d’un grand nombre de problèmes liés à la haute résolution dans la fenêtre de gestion des stratégies et de l’Éditeur de requête, notamment les icônes de plan d’exécution.

* Résolution du problème : l’option de configuration des polices et des couleurs pour les événements étendus est manquante.

* Résolution du problème : blocage de SSMS se produisant lors de la fermeture de l’application ou lors de la tentative d’affichage de la boîte de dialogue d’erreur.


## <a name="ssms-1641-september-2016-release"></a>Version de SSMS 16.4.1 (septembre 2016)
Disponibilité générale | Numéro de build : 13.0.15900.1

*  Correction d’un problème selon lequel la tentative de modification (ALTER) d’une procédure stockée échoue :  
[Article Microsoft Connect n°3103831](https://connect.microsoft.com/SQLServer/feedback/details/3103831)

* Nouvelles applets de commande « Read-SqlTableData », « Read-SqlViewData » et « Write-SqlTableData » pour afficher et écrire des données à l’aide de PowerShell.  
[Trello Read-SqlTableData Card](https://trello.com/c/FXVUNJ8x/131-read-sqltabledata)  
[Article Microsoft Connect n° 2685363](https://connect.microsoft.com/SQLServer/feedback/details/2685363)
    
* Nouvelle applet de commande « Add-SqlLogin » pour permettre de nouveaux scénarios de gestion de connexion à l’aide de PowerShell.  
[Article Microsoft Connect n° 2588952](https://connect.microsoft.com/SQLServer/feedback/details/2588952)
    
*  Prise en charge et utilisation améliorées pour les utilisateurs qui se connectent à plusieurs clouds nationaux.
    
    
*  Correction d’un problème où des exceptions Mémoire insuffisante étaient levées.  
[Article Microsoft Connect n° 3062914](https://connect.microsoft.com/SQLServer/feedback/details/3062914)  
[Article Microsoft Connect n° 3074856](https://connect.microsoft.com/SQLServer/feedback/details/3074856)
    
*  Correction d’un problème où le filtrage par schéma n’était pas une option de filtre valide.  
[Article Microsoft Connect n° 3058105](https://connect.microsoft.com/SQLServer/feedback/details/3058105)  
[Article Microsoft Connect n° 3101136](https://connect.microsoft.com/SQLServer/feedback/details/3101136)
    
*  Correction d’un problème où la fenêtre de surveillance d’une base de données étendue n’était pas accessible.
    
*  Correction d’un problème où la touche F1 (Aide) ouvrait toujours le contenu en ligne. Les utilisateurs peuvent désormais choisir s’ils préfèrent une aide en ligne ou hors connexion dans « Définir les préférences pour l’aide » du menu Aide.   
[Article Microsoft Connect n° 2826366](https://connect.microsoft.com/SQLServer/feedback/details/2826366)
    
*  Correction d’un problème où l’écriture du script d’un modèle tabulaire Analysis Services de niveau 1200 ne supprimait pas le mot de passe pour l’écriture du script, même si la version du serveur indiquait [l’objet de modèle de client est maintenant synchronisé avant l’écriture du script].
    
*  Correction d’un problème où l’option « Sélectionner les n premières lignes » générait une syntaxe déconseillée pour l’opérateur TOP.  
[Article Microsoft Connect n° 3065435](https://connect.microsoft.com/SQLServer/feedback/details/3065435)
    
*  Correction de divers problèmes de mise en page dans SSMS, notamment la page Propriétés de la connexion et les options d’exécution de requête avancée.   
[Article Microsoft Connect n° 3058199](https://connect.microsoft.com/SQLServer/feedback/details/3058199)  
[Article Microsoft Connect n° 3079122](https://connect.microsoft.com/SQLServer/feedback/details/3058199)  
[Article Microsoft Connect n° 3071384](https://connect.microsoft.com/SQLServer/feedback/details/3071384)
    
*  Correction d’un problème où une solution était créée automatiquement chaque fois qu’un utilisateur ouvrait une nouvelle fenêtre de requête.   
[Article Microsoft Connect n° 2924667](https://connect.microsoft.com/SQLServer/feedback/details/2924667)    
[Article Microsoft Connect n° 2917742](https://connect.microsoft.com/SQLServer/feedback/details/2917742)   
[Article Microsoft Connect n° 2612635](https://connect.microsoft.com/SQLServer/feedback/details/2612635)
    
*  Correction d’un problème où les tables temporelles ne pouvaient pas être développées dans l’Explorateur d’objets quand elles se trouvaient dans des bases de données système.  
[Article Microsoft Connect n° 2551649](https://connect.microsoft.com/SQLServer/feedback/details/2551649)
    
*  Correction d’un problème où SSMS exécute une requête SELECT @@trancount après l’exécution d’un lot.    
[Article Microsoft Connect n° 3042364](https://connect.microsoft.com/SQLServer/feedback/details/3042364)
    
*  Correction d’un problème dans Analysis Services où la création d’un script à partir de la page de propriétés d’un serveur masquait une boîte de dialogue de connexion.
    
*  Correction d’un problème où Ctrl + Q ne sélectionnait pas la barre d’outils Lancement rapide.
    
*  Correction d’un problème où la modification du paramètre MaxSize d’une base de données à l’aide de la boîte de dialogue Propriétés du serveur ne fonctionnait pas pour les bases de données > 2 To.  
[Article Microsoft Connect n°1231091](https://connect.microsoft.com/SQLServer/feedback/details/1231091)
    
*  Correction d’un problème où l’Assistant Restauration de la base de données n’acceptait pas les noms de fichiers avec des espaces de début :   
[Article Microsoft Connect n°2395147](https://connect.microsoft.com/SQLServer/feedback/details/2395147)



## <a name="ssms-163-august-2016-release"></a>Version de SSMS 16.3 (août 2016)
Généralement disponible | Numéro de version : 13.0.15700.28

* Les versions mensuelles de SSMS sont désormais étiquetées numériquement.

* [Nouvelle option d’authentification **« Authentification universelle Active Directory »**](https://azure.microsoft.com/documentation/articles/sql-database-ssms-mfa-authentication/). Il s’agit d’un système d’authentification par jeton piloté par Azure Active Directory, qui prend en charge des mécanismes d’authentification multifacteur, par mot de passe et intégrée.

* Nouveaux modèles d’événements étendus correspondant à la fonctionnalité des modèles SQL Server Profiler [(article Microsoft Connect n°2543925)](https://connect.microsoft.com/SQLServer/feedback/details/2543925/sql-server-extended-events-profiler-tool). En savoir plus les [modèles SQL Server Profiler](https://msdn.microsoft.com/library/ms190176.aspx)inclus.

* Nouvelles boîtes de dialogue Créer une base de données et Propriétés de la base de données pour les bases de données SQL Azure.

* Nouvelles applets de commande « Get-SqlLogin » et « Remove-SqlLogin » pour effectuer la gestion des comptes de connexion SQL Server à l’aide de PowerShell.  
*Demandes de correctif connexes des clients :*   
[Article Microsoft Connect n°2588952.](https://connect.microsoft.com/SQLServer/feedback/details/2588952/)

* Nouvelle applet de commande PowerShell « New-SqlColumnMasterKeySettings » qui ajoute la prise en charge de la création de clés principales de colonne pour les fournisseurs arbitraires et les chemins d’accès de clé.

* Nouvelle boîte de dialogue « Créer une base de données » pour simplifier la création de bases de données SQL Azure dans SSMS>

* Prise en charge du filtrage dans le nœud « Bases de données » de l’Explorateur d’objets de SSMS. Accédez au nœud « Bases de données » dans l’Explorateur d’objets, puis cliquez sur l’icône de filtre dans la barre d’outils de l’Explorateur d’objet pour filtrer la liste des bases de données.

* Prise en charge des comptes de stockage de type Azure Resource Manager (ARM) dans les Assistants Sauvegarde et Restauration.

* [Prise en charge bêta initiale des écrans haute résolution](https://blogs.msdn.microsoft.com/sqlreleaseservices/ssms-highdpi-support/).  
*Demandes de correctif connexes des clients :*   
[Article Microsoft Connect n°1129301](https://connect.microsoft.com/SQLServer/feedback/details/1129301/management-studio-is-unusable-on-a-4k-display), [Article Microsoft Connect n°1858763](https://connect.microsoft.com/SQLServer/feedback/details/1858763/), [Article Microsoft Connect n°1852671](https://connect.microsoft.com/SQLServer/feedback/details/1852671/), [Article Microsoft Connect n°1487643](https://connect.microsoft.com/SQLServer/feedback/details/1487643/),  [Article Microsoft Connect n°1355641](https://connect.microsoft.com/SQLServer/feedback/details/1355641/), [Article Microsoft Connect n°2161595](https://connect.microsoft.com/SQLServer/feedback/details/2161595/), [Article Microsoft Connect n°1854041](https://connect.microsoft.com/SQLServer/feedback/details/1854041/), [Article Microsoft Connect n°1055617](https://connect.microsoft.com/SQLServer/feedback/details/1055617/), [Article Microsoft Connect n°2448774](https://connect.microsoft.com/SQLServer/feedback/details/2448774/), [Article Microsoft Connect n°1521405](https://connect.microsoft.com/SQLServer/feedback/details/1521405/), [Article Microsoft Connect n°2117853](https://connect.microsoft.com/SQLServer/feedback/details/2117853/), [Article Microsoft Connect n°2014256](https://connect.microsoft.com/SQLServer/feedback/details/2014256/), [Article Microsoft Connect n°2162218](https://connect.microsoft.com/SQLServer/feedback/details/2162218/), [Article Microsoft Connect n°2344551](https://connect.microsoft.com/SQLServer/feedback/details/2344551/), [Article Microsoft Connect n°1664436](https://connect.microsoft.com/SQLServer/feedback/details/1664436/), [Article Microsoft Connect n°2554043](https://connect.microsoft.com/SQLServer/feedback/details/2554043/), [Article Microsoft Connect n°2983216](https://connect.microsoft.com/SQLServer/feedback/details/2983216/), [Article Microsoft Connect n°2021706](https://connect.microsoft.com/SQLServer/feedback/details/2021706/)

* Améliorations de l’Assistant Paramétrage du moteur de base de données (DTA) pour prendre automatiquement en charge la lecture d’une charge de travail à partir du Magasin de requêtes de SQL Server.

* Améliorations de l’Assistant Paramétrage du moteur de base de données (DTA) pour afficher les recommandations d’index des index columnstore, columnstore non cluster et rowstore.

* Prise en charge de l’envoi de commandes DBCC (Database Console Commands) à l’aide d’applets de commande PowerShell de SQL Server Analysis Services.

* Résolution de bogue pour afficher le texte en clair de colonnes d’objet volumineux (LOB) AlwaysEncrypted déchiffrées dans SSMS.  
*Demandes de correctif connexes des clients :*   
[Article Microsoft Connect n°2413024](https://connect.microsoft.com/SQLServer/feedback/details/2413024/cannot-view-cleartext-of-alwaysencrypted-lob-columns-in-ssms)

* Résolution de bogue dans la boîte de dialogue Chiffrement intégral pour corriger l’incident qui se produit quand les styles visuels Windows ne sont pas activés (par exemple, l’activation de l’affichage à contraste élevé).

* Résolution de bogue pour l’erreur « Méthode introuvable » qui empêche la connexion à des instances SQL Server.

* Résolution de bogue pour l’incident SSMS qui se produit lors de la création d’une fonction de partition avec décalage de date/heure.

* Résolution de bogue pour ajouter l’exigence de disposer de Microsoft .NET 3.5 pour démarrer l’outil d’administration Distributed Replay (DReplay.exe).

* Résolution de bogue dans l’Assistant Déploiement d’Analysis Services pour prendre en charge les noms de serveur complets.

* Résolution de bogue dans SSMS pour afficher les partitions dans les modèles tabulaires Analysis Services avec un modèle de compatibilité 2016.  
*Demandes de correctif connexes des clients :*   
[Article Microsoft Connect n°2845053](https://connect.microsoft.com/SQLServer/feedback/details/2845053/ssms-cannot-display-partitions-in-tabular-models-in-2016-compatibility-level) 

* Améliorations des performances et résolutions de bogues dans les modèles tabulaires Analysis Services et les Objets de gestion partagée SQL Server. 


---
## <a name="ssms-july-2016-hotfix-update-release"></a>Version mise à jour du correctif logiciel SSMS - juillet 2016 
Généralement disponible | Numéro de version : 13.0.15600.2

* **Résolution de bogue dans SSMS pour activer des options de menu contextuel manquantes**.  
*Demandes de correctif connexes des clients :*  
[Article Microsoft Connect n°2883440](https://connect.microsoft.com/SQLServer/feedback/details/2883440/lost-table-design-and-edit-top-n-rows-in-tables-context-menu)  
[Article Microsoft Connect n°2909644](https://connect.microsoft.com/SQLServer/feedback/details/2909644/ssms-2016-is-missing-edit-options-against-sql-express-2014)  
[Article Microsoft Connect n°2924345](https://connect.microsoft.com/SQLServer/feedback/details/2924345/some-ssms-object-explorer-right-click-menu-options-missing-in-july-update)

---
## <a name="ssms-july-2016-release"></a>Version de SSMS - juillet 2016 
Généralement disponible | Numéro de version : 13.0.15500.91

* *Modification, 5 juillet :* **Prise en charge améliorée des bases de données tabulaires SQL Server 2016 (niveau de compatibilité 1200) dans la boîte de dialogue de processus Analysis Services et l’Assistant Déploiement d’Analysis Services.**

* *Modification, 5 juillet :* **Nouvelle option dans la boîte de dialogue des options d’exécution de requête de SSMS pour définir « XACT_ABORT ». Cette option est activée par défaut dans cette version de SSMS. Elle demande à SQL Server de restaurer l’intégralité de la transaction et d’abandonner le traitement du lot en cas d’erreur d’exécution.**

* **Prise en charge d’Azure SQL Data Warehouse dans SSMS.**

* **Mises à jour importantes du module SQL Server PowerShell. Celles-ci incluent [un nouveau module SQL PowerShell et de nouvelles applets de commande pour le Chiffrement intégral, l’Agent SQL et les journaux d’erreurs SQL](https://blogs.technet.microsoft.com/dataplatforminsider/2016/06/30/sql-powershell-july-2016-update)**.

* **Prise en charge de la génération de scripts PowerShell dans l’Assistant Chiffrement intégral**.

* **Délais de connexion aux bases de données SQL Azure considérablement améliorés.**

* **Nouvelle boîte de dialogue Backup to URL (Sauvegarde vers l’URL) pour prendre en charge la création d’informations d’identification de stockage Azure pour les sauvegardes de bases de données SQL Server 2016. Il est ainsi plus simple de stocker les sauvegardes de bases de données dans un compte de stockage Azure.**
 
* **Nouvelle boîte de dialogue Restore (Restauration) pour simplifier la restauration d’une sauvegarde de base de données SQL Server 2016 à partir du service de stockage Microsoft Azure.**
 
* **Résolution de bogue dans le concepteur de requêtes SSMS pour permettre l’ajout de tables au concepteur si un utilisateur ne dispose pas d’autorisations SELECT sur celles-ci.**

* **Résolution de bogue pour ajouter la prise en charge IntelliSense pour les fonctions TRY_CAST() et TRY_CONVERT().**  
*Demandes de correctif connexes des clients :*  
[Article Microsoft Connect n°2453461](https://connect.microsoft.com/SQLServer/feedback/details/2453461/sql-server-2012-issue-with-try-cast).

* **Résolution de bogue dans le module PowerShell pour activer le chargement de l’extension Analysis Services SQLAS.**  
*Demandes de correctif connexes des clients :*  
[Article Microsoft Connect n°2544902](https://connect.microsoft.com/SQLServer/feedback/details/2544902/ssms-march-2016-refresh-sqlps-failed-to-load-the-sqlas-extension).

* **Résolution de bogue dans la fenêtre de l’éditeur SSMS pour autoriser l’ouverture par glisser-déplacer de fichiers Sql.**  
*Demandes de correctif connexes des clients :*  
[Article Microsoft Connect n°2690658](https://connect.microsoft.com/SQLServer/feedback/details/2690658/cannot-drag-sql-files-into-management-studios).

* **Résolution de bogue dans Profiler pour résoudre les blocages de Profiler lors de la sortie.**  
*Demandes de correctif connexes des clients :*  
[Article Microsoft Connect n°2616550](https://connect.microsoft.com/SQLServer/feedback/details/2616550/sql-server-2016-rc2-profiler-version-13-0-1300-275-wont-close-after-trace-is-started-even-after-trace-is-stopped).  
[Article Microsoft Connect n°2319968](https://connect.microsoft.com/SQLServer/Feedback/Details/2319968).

* **Résolution de bogue dans SSMS pour éviter l’incident qui se produit lors d’une tentative de modification d’un lien de jointure dans le Concepteur de tables SSMS.**  
*Demandes de correctif connexes des clients :*  
[Article Microsoft Connect n°2721052](https://connect.microsoft.com/SQLServer/feedback/details/2721052/ssms-view-design-mode-right-click-on-join-crashes-ssms).

* **Résolution de bogue dans SSMS pour activer la génération de script de base de données pour les membres du rôle db_owner.**  
*Demandes de correctif connexes des clients :*  
[Article Microsoft Connect n°2869241](https://connect.microsoft.com/SQLServer/feedback/details/2869241/error-with-script-database-as-create-to-in-ssms-2008r2-and-ssms-2016-june).

* **Résolution de bogue dans l’éditeur SSMS pour supprimer le délai de fermeture d’un onglet de requête si le serveur a été mis hors connexion.**  
*Demandes de correctif connexes des clients :*  
[Article Microsoft Connect n°2656058](https://connect.microsoft.com/SQLServer/feedback/details/2656058/ssms-2014-2016-query-tab-takes-significantly-longer-to-close-if-the-instance-it-was-connected-to-is-now-offline).

* **Résolution de bogue pour activer l’option de sauvegarde dans les bases de données SQL Server Express.**  
*Demandes de correctif connexes des clients :*  
[Article Microsoft Connect n°2801910](https://connect.microsoft.com/SQLServer/feedback/details/2801910/ssms-2016-backup-option-not-appearing-in-tasks).  
[Article Microsoft Connect n°2874434](https://connect.microsoft.com/SQLServer/feedback/details/2874434/backup-missing-from-tasks-context-menu-in-ssms-2016-when-you-are-connected-to-an-express-instance).

* **Résolution de bogue dans Analysis Services pour afficher correctement le fournisseur de flux de données pour les modèles Analysis Services multidimensionnels.**

----
## <a name="ssms-june-2016-generally-available-release"></a>Version généralement disponible de SSMS - Juin 2016
Généralement disponible | Numéro de version : 13.0.15000.23

* **SSMS est généralement disponible depuis la version de juin 2016.**

* **Nouvelle boîte de dialogue Recherche rapide dans SSMS mieux intégrée dans le document actif et qui permet des recherches via des expressions régulières.**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2735513/quick-find-replace-in-ssms-2016-rc3/>

* **Améliorations du programme d’installation de SSMS permettant de suivre la progression de l’installation et les codes de sortie du processus pour les installations sans assistance à l’aide de scripts.**

* **Résolution de bogue dans l’aide contextuelle (accessible via la touche F1) de SSMS afin d’afficher correctement les documents et articles d’aide.**

* **Résolution de bogue dans la vue « Requêtes régressées » du magasin de données de requête, qui entraînait le blocage de SSMS lors du défilement.** 

* **Résolution de bogue dans le connecteur Analysis Services OLEDB d’Excel pour autoriser les connexions d’Excel 2016 à SQL Server Analysis Services.**

* **Résolution de bogue dans la boîte de dialogue de connexion de SSMS pour afficher la boîte de dialogue de connexion sur le même moniteur que la fenêtre principale de SSMS dans les systèmes multimoniteurs.**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/724909/connection-dialog-appears-off-screen/>
<https://connect.microsoft.com/SQLServer/feedback/details/755689/sql-server-management-studio-connect-to-server-popup-dialog/>  
<https://connect.microsoft.com/SQLServer/feedback/details/389165/sql-server-management-studio-gets-confused-dealing-with-multiple-displays/>

* **Résolutions de bogues avec l’utilisation d’Always Encrypted. Résolution du bogue où l’option de menu Chiffrement intégral n’était pas activée correctement pour les bases de données Stretch. Résolution également du bogue de l’Assistant Always Encrypted qui n’utilisait pas correctement le fournisseur HSM SafeNet (Luna SA).**

---
## <a name="ssms-april-2016-preview"></a>Version préliminaire de SSMS - Avril 2016 
Numéro de version : 13.0.14000.36
  
* **Amélioration du programme d’installation de SSMS par l’ajout de messages d’erreur explicites.**  
  
* **Amélioration de l’Assistant Stretch Database par l’ajout de la prise en charge des prédicats**.  
  
* **Amélioration de l’applet de commande Powershell AlwaysEncrypted par l’ajout d’API de chiffrement à clé**.  
  
* **Résolution de bogue pour désactiver IntelliSense dans la barre d’outils de SSMS si l’application a été désactivée dans la boîte de dialogue Outils, Options.**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2555163/sql-2016-rc2-turning-off-intellisense-from-options-does-not-turn-it-off-on-toolbar/>  
    
* **Améliorations et résolutions de bogues dans l’interface utilisateur de comparaison de Showplan pour réduire l’espace utilisé par les plans de requête longue**.  
  
* **Résolutions de bogues dans SSMS afin de résoudre les problèmes qui provoquaient le blocage de SSMS lors de la sortie**.   
  
* **Résolutions de bogues dans l’Assistant Chiffrement intégral pour conserver les autorisations de l’utilisateur durant le chiffrement, et permettre les opérations de détachement de base de données une fois l’exécution de l’Assistant terminée**.  
  
* **Résolution de bogue dans la boîte de dialogue Nouvelle clé principale de colonne Always Encrypted pour fournir des commentaires sur une tentative de génération d’une clé à l’aide d’un fournisseur d’algorithme de chiffrement non pris en charge.**  
  
---  
## <a name="ssms-march-2016-preview-refresh"></a>Actualisation de la version préliminaire de SSMS - Mars 2016
Numéro de version : 13.0.13000.55
  
* **SSMS utilise désormais le shell isolé Visual Studio 2015.**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2390544/update-ssms-to-use-visual-studio-2015-dependencies/>  
  
* **Nouvelle barre d’outils Lancement rapide qui vous aide à trouver rapidement des éléments et options de menu. (Shell isolé VS 2015)**  
  
* **Améliorations des options de thèmes de SSMS pour ajouter la prise en charge d’un thème clair. (Shell isolé VS 2015)**  
  
* **Résolution de bogue de l’option de menu des outils de SSMS afin de réinitialiser correctement les raccourcis de requête si l’utilisateur appuie sur le bouton Rétablir les valeurs par défaut.**  
  
* **Résolution de bogue dans les modèles de nouveau projet de SSMS pour afficher des noms de modèle facilement lisibles.**  
  
* **Erreur résolue lors de l’affichage de l’historique des travaux de l’Agent SQL dans SSMS.**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2458860/error-viewing-job-history-microsoft-datawarehouse-sqm/>  
    
* **Résolution de bogue pour permettre l’installation hors connexion de SSMS. Celle-ci vous permet d’installer sans avoir besoin d’une connexion Internet. (Shell isolé VS 2015)**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2497178/cannot-install-ssms-when-server-has-no-internet-access/>  
    
* **Résolution de bogue pour conserver le répertoire actuel de l’utilisateur lors de l’importation du module SQL Server PowerShell (SQLPS).**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2434605/loading-sqlps-module-changes-current-directory-to-ps-sqlserver/>  
    
* **Résolution de bogue dans le module SQL Server PowerShell (SQLPS) afin d’utiliser les verbes PowerShell approuvés.**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2432891/sqlps-module-uses-unapproved-powershell-verbs/>  
    
* **Résolution de bogue dans le module SQL Server Powershell (SQLPS) afin de charger le module plus rapidement.**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2429153/sqlps-module-is-slow-to-load/>  
    
* **Résolution de bogue dans les étapes de travail de l’Agent SQL afin de permettre la modification d’une étape de travail.**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2453996/issues-with-agent-in-ssms-2016-rc0-13-0-12000-65/>  
    
* **Résolution de bogue dans l’Explorateur d’objets SSMS afin de répertorier les tables dans l’ordre alphabétique.**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2424718/sql-server-2016-ssms-table-list-confusing/>  
    
* **Résolution de bogue dans la liste déroulante Bases de données disponibles afin d’afficher la liste exacte des noms de base de données en cas de modification d’une connexion SQL Server.**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2513420/available-databases-drop-down-box-does-not-update-when-connection-changes-in-ssms/>  
    
* **Résolution de bogue dans les raccourcis clavier de SSMS, afin de positionner le focus sur la liste déroulante Bases de données disponibles en cas d’appui sur la combinaison de touches CTRL+U.**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2534820/ssms-ctrl-u-doesnt-work/>  
  
---  
## <a name="ssms-march-2016-preview"></a>Version préliminaire de SSMS - Mars 2016 
Numéro de version : 13.0.12500.29 
  
* **Amélioration du programme d’installation web de SSMS pour permettre la navigation à l’aide des touches du clavier.**  
  
* **Amélioration de l’Assistant Always Encrypted pour prendre en charge les types de données d’alias pour le chiffrement.**  
  
* **Résolution de bogue dans l’Assistant Nouveau groupe de disponibilité AlwaysOn pour afficher le nombre maximal correct de cibles de basculement automatique.**  
*Demandes de correctif connexes des clients :* <https://connect.microsoft.com/SQLServer/feedback/details/2333670/ssms-is-showing-the-wrong-number-of-maximum-automatic-failover-targets/>  
    
* **Résolution de bogue dans le programme d’installation web de SSMS pour corriger des erreurs affectant l’installation.**  
*Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2181548/sql-server-2016-ctp-3-2-management-studio-setup/>  
    
* **Résolution de bogue dans la version préliminaire de SSMS pour activer l’enregistrement des plans de maintenance de SQL Server 2012 et versions inférieures.**  
      
* **Résolutions de bogues dans l’Assistant Sauvegarde afin d’autoriser plusieurs noms de sauvegarde personnalisés pour les sauvegardes sur bandes et d’afficher le nom de fichier de sauvegarde approprié si un nouveau nom est entré après la sélection des informations d’identification d’un stockage.**  
  
---  
## <a name="ssms-february-2016-preview"></a>Version préliminaire de SSMS - Février 2016 
Numéro de version : 13.0.12000.65
  
* **Amélioration du Moniteur d’activité pour afficher les options de texte quand des paramètres de contraste élevé sont activés dans SSMS.**  
  
* **Amélioration de la boîte de dialogue de l’Assistant Always Encrypted afin d’afficher un avertissement si le classement d’une colonne va être modifié durant le processus de chiffrement.**  
  
* **Amélioration de la gestion des stratégies afin d’ajouter la prise en charge de la création de conditions sur les clés de chiffrement de colonne, les valeurs des clés de chiffrement de colonne et les clés principales de colonne.**  
  
* **Résolution de bogue pour améliorer la convivialité de la boîte de dialogue de nettoyage de la clé principale et des messages d’erreur Always Encrypted.**  
  
* **Résolution de bogue pour désactiver la permutation des clés principales de colonne Always Encrypted s’il n’existe qu’une seule clé.**  
  
* **Résolution de bogue pour l’erreur d’initialiseur de type qui se produit quand la boîte de dialogue Always Encrypted est ouverte à l’aide de la version de janvier de SSMS ou de la version de SSMS fournie avec le support SQL Server RC0.**  
  
---  
## <a name="ssms-january-2016-preview"></a>Version préliminaire de SSMS - Janvier 2016 
Numéro de version : 13.0.11000.78 
  
* **Résolution de bogue dans SSMS pour permettre la suppression des sessions d’événements étendus (XEvent).**  
  
* **Résolution de bogue pour ouvrir une boîte de dialogue de propriétés pour un groupe de disponibilité SQL Server 2014.**  
 *Demandes de correctif connexes des clients :*  
 <https://connect.microsoft.com/SQLServer/feedback/details/1609719/>  
     
* **Résolution de bogue pour activer la possibilité d’ajouter un réplica Azure à un groupe de disponibilité.**  
 *Demandes de correctif connexes des clients :*  
 <https://connect.microsoft.com/SQLServer/feedback/details/2029135/>  
     
* **Résolution de bogue pour ouvrir une boîte de dialogue de propriétés pour des bases de données SQL Server 2014.**  
 *Demandes de correctif connexes des clients :*  
 <https://connect.microsoft.com/SQLServer/feedback/details/2080209/>  
     
* **Résolution de bogue pour supprimer les doublons de colonnes qui s’affichent pour chaque table lors de la connexion à une base de données SQL Azure.**  
 *Demandes de correctif connexes des clients :*  
 <https://connect.microsoft.com/SQLServer/feedback/details/2103116/>  
---  
## <a name="ssms-december-2015-preview"></a>Version préliminaire de SSMS - Décembre 2015 
Numéro de version : 13.0.900.73
  
* **Améliorations de la comparaison des plans d’exécution de requêtes pour pouvoir comparer le plan d’exécution de requête actuel à un plan enregistré dans un fichier.**  
  
* **Prise en charge améliorée par IntelliSense des index columnstore inline dans SSMS.**  
  
* **Résolution de bogue dans l’Assistant de session d’événements étendus pour pouvoir sélectionner les modèles avec une connexion à un serveur Azure V12.**  
  
* **Nouveaux taquets de tabulation dans les boîtes de dialogue Créer un audit et Nouvelle connexion sous le dossier Sécurité pour faciliter la navigation au clavier.**  
  
* **Résolution de bogue pour activer la fonctionnalité « Basculer vers l’onglet des résultats après l’exécution de la requête » si SSMS est configuré pour afficher les résultats sous forme de grille.**   
 *Demandes de correctif connexes des clients :*  
  <https://connect.microsoft.com/SQLServer/feedback/details/1390296/switch-to-results-tab-after-query-execution-grid-mode-in-ssms-2016>  
  
* **Résolution de bogue pour afficher des en-têtes de colonnes non tronqués si SSMS est configuré pour afficher les résultats sous forme de grille.**  
 *Demandes de correctif connexes des clients :*  
  <https://connect.microsoft.com/SQLServer/feedback/details/2004111/bugbash-column-headers-in-grid-mode-truncated-with-courier-new-8>  
      
* **Résolutions de bogues pour permettre l’installation correcte du programme d’installation web de SSMS.**  
 *Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/2003865/ssms-october-preview-incoherent-error-message>  
<https://connect.microsoft.com/SQLServer/feedback/details/2079557/unable-to-instal-sql-server-update-13-0-800-111-over-13-0-700-242-error-code-2711>  
  
---  
## <a name="ssms-november-2015-preview"></a>Version préliminaire de SSMS - Novembre 2015
Numéro de version : 13.0.800.111
  
* **Prise en charge de la mise à l’échelle bitmap pour les affichages en haute résolution dans SSMS.**  
  
* **Améliorations apportées à l’interface utilisateur des boîtes de dialogue et Assistants Always Encrypted pour simplifier le processus de création des clés de chiffrement de base de données.**  
  
* **Nouvelle option de menu contextuel dans la liste Processus du Moniteur d’activité pour afficher les statistiques des requêtes en direct.**  
  
* **Résolution de bogue pour permettre la désinstallation correcte des versions préliminaires de SSMS sur les ordinateurs clients.**  
  *Demandes de correctif connexes des clients :*  
  <https://connect.microsoft.com/SQLServer/feedback/details/1868474/ssms-2016-preview-can-be-installed-but-not-uninstalled>  
  
* **Résolution de bogue pour permettre la modification des étapes de travail dans l’Agent SQL, même quand un fichier est manquant**.  
  *Demandes de correctif connexes des clients :*  
  <https://connect.microsoft.com/SQLServer/feedback/details/1769778/management-studio-2016-sql-job-agent>  
    <https://connect.microsoft.com/SQLServer/feedback/details/1502100/ssms-preview-error>  
      
* **Résolution de bogue dans l’option de menu Afficher les données cibles pour une session d’événements étendus sur une base de données exécutée dans une machine virtuelle Azure.**  
  *Demandes de correctif connexes des clients*:  
  <https://connect.microsoft.com/SQLServer/feedback/details/1769778/management-studio-2016-sql-job-agent>  
***  

## <a name="ssms-october-2015-preview"></a>Version préliminaire de SSMS - Octobre 2015 
Numéro de version : 13.0.700.242  
* **Nouveau programme d’installation web, léger et modernisé, qui simplifie le processus de téléchargement et d’installation de SSMS.**  
  
* **Nouvel Assistant de chiffrement de colonne Always Encrypted qui autorise le chiffrement et le déchiffrement côté client des colonnes sélectionnées.**  
  
* **Nouvelle boîte de dialogue de permutation de clé principale de colonne pour les bases de données Always Encrypted qui simplifie le processus de permutation des clés de chiffrement pour sécuriser les données.**  
  
* **Nouvelle surveillance de Stretch Database qui permet de dépanner et d’analyser l’état de migration des données vers le cloud Azure.**  
  
* **Améliorations apportées à l’Assistant Stretch Database pour prendre en charge la sélection d’un serveur Microsoft Azure qui n’est pas inclus dans l’abonnement Microsoft Azure par défaut.**  
  *Demandes de correctif connexes des clients :*  
  <https://connect.microsoft.com/SQLServer/feedback/details/1687063/cannot-choose-from-multiple-microsoft-azure-subscriptions>  
* **Résolution de bogue pour afficher correctement le plan d’exécution actif dans SSMS.**  
  *Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/1774446/viewing-live-execution-plan-from-activity-monitor-crashes-ssms>    
* **Résolution de bogue pour supprimer les options non valides dans les scripts SSMS d’instantanés de base de données**  
  *Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/1515168/ssms-scripting-of-database-snapshots-includes-invalid-options>  
* **Résolution de bogue dans l’interface utilisateur du magasin de données de requête pour afficher des détails dans le volet des principales requêtes consommatrices de ressources.**  
  *Demandes de correctif connexes des clients :*  
<https://connect.microsoft.com/SQLServer/feedback/details/1737185/sql-server-2016-overall-resource-consumption-query-store-pane-issue>  
***  

## <a name="ssms-september-2015-preview"></a>Version préliminaire de SSMS - Septembre 2015 
Numéro de version : 13.0.600.65  
* **Nouvelle boîte de dialogue Règle de pare-feu qui simplifie le processus de connexion à une base de données SQL Azure.**      
    
* **Mise à jour de la boîte de dialogue Nouvel index qui permet de créer des index non cluster rowstore, même si un index cluster columnstore est présent. Cette fonctionnalité est disponible pour SQL 2016 et versions ultérieures.**      
  *Demandes de correctif connexes des clients :*    
  <https://connect.microsoft.com/SQLServer/feedback/details/1552617/creation-of-nc-index-when-clustered-columnstore-index>  
      
* **Résolution de bogue pour permettre l’affichage et la modification des étapes de travail de l’Agent SQL dans les versions préliminaires de SSMS exécutées sur Windows 7.**      
  *Demandes de correctif connexes des clients :*    
  <https://connect.microsoft.com/SQLServer/feedback/details/1548140/cannot-view-or-edit-any-sql-agent-job-step>,    
  <https://connect.microsoft.com/SQLServer/feedback/details/1626895/unable-to-load-dll-dts>,    
  <https://connect.microsoft.com/SQLServer/feedback/details/1576662/error-creating-new-job-step>     
      
* **Résolution de bogue pour afficher les nœuds déclencheurs dans SSMS pour SQL Server 2014 et versions ultérieures.**      
  *Demandes de correctif connexes des clients :*    
  <https://connect.microsoft.com/SQLServer/feedback/details/1617533/trigger-node-missing>   
      
* **Résolutions de bogues dans l’interface utilisateur des rapports standard de base de données et de serveur pour exclure les informations de version de l’en-tête.**      
  *Demandes de correctif connexes des clients :*    
  <https://connect.microsoft.com/SQLServer/feedback/details/1387471/report-headings-wrongly-named>  
      
* **Résolution de bogue pour empêcher qu’un nœud de statistiques des requêtes en direct apparaisse comme étant terminé alors qu’il ne l’est pas.**      
  *Demandes de correctif connexes des clients :*    
  <https://connect.microsoft.com/SQLServer/feedback/details/1589096/live-query-statistics-node-shows-as-completed>  
  
***      
## <a name="ssms-august-2015-preview"></a>Version préliminaire de SSM - Août 2015 
Numéro de version : 13.0.500.53
  
* **Application de mises à jour à l’Explorateur d’objets pour réduire le délai de chargement en présence d’un grand nombre de bases de données.**  
  
* **Améliorations relatives à l’installation de SSMS sur les ordinateurs Windows 10.**  
  
* **Application de résolutions de bogues et de mises à jour au Gestionnaire de configuration SQL Server et à l’interface utilisateur des rapports utilisateur SSMS**    
***  
  
## <a name="ssms-july-2015-preview"></a>Version préliminaire de SSMS - Juillet 2015
Numéro de version : 13.0.400.91
  
* **Schémas de base de données pour Azure SQL Database (V12).**  
  
* **Prise en charge améliorée par IntelliSense de la nouvelle syntaxe de tables temporelles.**  
  
* **Mise à jour de la bibliothèque DACFx pour prendre en charge les dernières fonctionnalités des bases de données SQL Azure, notamment la sécurité de niveau ligne et l’authentification Azure Active Directory.**  
  
* **Résolutions de bogues (option d’interface utilisateur Rechercher les mises à jour mise à jour, correction de l’interface utilisateur dans la liste niveau de compatibilité, etc.).**  
***  
  
## <a name="ssms-june-2015-preview"></a>Version préliminaire de SSMS - Juin 2015 
Numéro de version : 13.0.300.44
  
* **Nouveau programme d’installation de SSMS (version web légère).**  
  
* **Recherche automatique des mises à jour.**  
  
* **SSMS prend désormais en charge la recherche en texte intégral pour Azure SQL Database (V12).**  
  
* **Les principales demandes des clients ont été traitées :**  
  * Option « Modifier les 200 lignes du haut » activée pour les tables et les vues dans l’Explorateur d’objets.  
  * Concepteur de tables activé pour Azure SQL Database (V12).  
  * Boîtes de dialogue des propriétés de base de données et de de table activées pour Azure SQL Database (V12).  
    
 * **Nouvelle option permettant d’ignorer la demande d’enregistrement des fichiers T-SQL.**  
   
 * **Prise en charge dans l’Assistant Importation/Exportation de nouveaux niveaux de service Azure SQL Database (De base, Standard, Premium).**  
   
 * **Application de nombreuses résolutions de bogues (scénarios de script, activation du suivi des modifications pour les bases de données SQL, etc.).**   

