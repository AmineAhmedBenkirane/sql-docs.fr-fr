---
title: Notes de publication pour le pilote JDBC | Documents Microsoft
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 074f211e-984a-4b76-bb15-ee36f5946f12
caps.latest.revision: 206
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: On Demand
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: bd65725237fd625c40f8755e636bb4f6fa2c55ea
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="release-notes-for-the-jdbc-driver"></a>Notes de publication pour le pilote JDBC
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

## <a name="updates-in-microsoft-jdbc-driver-62-for-sql-server"></a>Mises à jour de Microsoft JDBC Driver 6.2 pour SQL Server
Le 6.2 de pilote JDBC Microsoft pour SQL Server est entièrement conforme aux spécifications de JDBC 4.1 et 4.2. Les fichiers JAR contenues dans le package 6.0 sont nommées en fonction de la compatibilité des versions de Java. Par exemple, le fichier mssql-jdbc-6.2.1.jre8.jar à partir du package 6.2 est recommandé pour être utilisé avec Java 8. 

**Remarque :** un problème avec les métadonnées de la mise en cache d’amélioration du produit a été trouvé dans la RTW 6.2 JDBC publiées le 29 juin 2017. L’amélioration a été restaurée et de nouveaux fichiers JAR (version 6.2.1) ont été publiées sur le 17 juillet 2017 le [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=852460), [GitHub](https://github.com/Microsoft/mssql-jdbc/releases/tag/v6.2.1), et [Maven Central](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.microsoft.sqlserver%22%20AND%20a%3A%22mssql-jdbc%22). Mettez à jour vos projets pour utiliser le 6.2.1 libérer les fichiers JAR. Veuillez consulter [notes de publication](https://github.com/Microsoft/mssql-jdbc/releases/tag/v6.2.1) pour plus d’informations.

**Prise en charge de Azure Active Directory (AAD) pour Linux**

Se connecter vos applications Linux à la base de données SQL Azure en utilisant l’authentification AAD via les méthodes jeton d’accès et nom d’utilisateur/mot de passe.

**Federal Standard FIPS (Information Processing) activé JVM**

Le pilote JDBC permet désormais de JVM qui s’exécutent en mode de conformité FIPS 140 aux fédérales et conformité. 

**Amélioration de l’authentification Kerberos** 

Le pilote JDBC prend désormais en charge : 
* Méthode principal/mot de passe pour les applications où la configuration de Kerberos ne peut pas être modifié ou Impossible de récupérer un nouveau jeton ou un fichier keytab. Cette méthode peut être utilisée pour l’authentification sur un serveur SQL Server qui autorise uniquement l’authentification Kerberos. 
* Authentification inter-domaines à l’aide de l’authentification Kerberos intégrée sans définir explicitement le SPN du serveur. Maintenant le pilote calcule automatiquement le domaine même si elle n’a pas été fourni.
* La délégation contrainte Kerberos en acceptant empruntée des informations d’identification de l’utilisateur en tant qu’objet d’informations d’identification GSS via la source de données. Ces informations d’identification avec emprunt d’identité sont ensuite utilisée pour établir une connexion Kerberos. 

**Ajout de délais d’attente**

Le pilote JDBC prend désormais en charge le configurable délais d’attente suivants que vous pouvez modifier selon les besoins de votre application : 
* Contrôler le nombre de secondes à attendre avant un délai d’expiration du délai de requête se produit lors de l’exécution d’une requête. 
* Délai d’attente de socket pour spécifier le nombre de millisecondes à attendre avant un délai d’attente se produit sur un socket de lecture ou accepter. 

## <a name="updates-in-microsoft-jdbc-driver-61-for-sql-server"></a>Mises à jour de Microsoft JDBC Driver 6.1 pour SQL Server

La version 6.1 de Microsoft JDBC Driver pour SQL Server est entièrement conforme aux spécifications de JDBC 4.1 et 4.2. Ceci est la version initiale ouvrir la source du pilote JDBC et contient les fichiers de mssql-jdbc-6.1.0.jre7.jar mssql-jdbc-6.1.0.jre8.jar, qui correspondent à la compatibilité de la version Java. 

## <a name="updates-in-microsoft-jdbc-driver-60-for-sql-server"></a>Mises à jour de Microsoft JDBC Driver 6.0 pour SQL Server

Le pilote Microsoft JDBC 6.0 pour SQL Server est entièrement conforme aux spécifications de JDBC 4.1 et 4.2. Les fichiers JAR contenues dans le package 6.0 sont nommées en fonction de leur conformité avec la version de l’API JDBC. Par exemple, le fichier sqljdbc42.jar à partir du package 6.0 est conforme à JDBC API 4.2. De même, le fichier sqljdbc41.jar est compatible avec l’API JDBC 4.1.

Pour garantir que vous avez le droit sqljdbc42.jar ou sqljdbc41.jar, exécutez les lignes de code suivantes. Si la sortie est « version du pilote : 6.0.7507.100 », vous disposez du package de pilote JDBC 6.0.
```
Connection conn = DriverManager.getConnection("jdbc:sqlserver://<server>;user=<user>;password=<password>;");
System.out.println("Driver version: " + conn.getMetaData().getDriverVersion());
```  
 **Always Encrypted**  
  
 Prise en charge de la fonctionnalité toujours chiffré récemment publiée dans SQL Server 2016, une nouvelle fonctionnalité de sécurité qui garantit que les données sensibles ne soient jamais affichées en texte brut dans une instance de SQL Server. Always Encrypted chiffre les données de l’application par transparence, de sorte que SQL Server manipule uniquement les données chiffrées, et non des valeurs en texte clair. Même si l’instance SQL ou l’ordinateur hôte est compromis, un attaquant peut obtenir qu’un texte chiffré des données sensibles. Pour plus d’informations, consultez [à l’aide d’Always Encrypted avec le pilote JDBC](../../connect/jdbc/using-always-encrypted-with-the-jdbc-driver.md).  
  
 **Nom de domaine international (IDN)**  
  
 Prise en charge des noms de domaine internationaux pour les noms de serveur. Pour plus d’informations, consultez à l’aide des noms de domaines internationaux sur le [fonctionnalités internationales du pilote JDBC](../../connect/jdbc/international-features-of-the-jdbc-driver.md) page.  
  
 **Requête paramétrée**  
  
 Prise en charge de la récupération des métadonnées de paramètres avec des instructions préparées pour les requêtes complexes telles que les sous-requêtes et/ou les jointures. Notez que cette amélioration est disponible uniquement lorsque vous utilisez SQL Server 2012 et les versions plus récentes.  
  
 **Azure Active Directory (AAD)**  
  
 L’authentification AAD est un mécanisme de se connecter à la base de données SQL Azure v12 à l’aide des identités dans AAD. Utilisez l’authentification AAD pour gérer les identités des utilisateurs de base de données et comme alternative à l’authentification SQL Server de manière centralisée. Le pilote JDBC 6.0 vous permet de spécifier vos informations d’identification dans la chaîne de connexion JDBC pour se connecter à la base de données SQL Azure.  Pour plus d’informations, consultez la propriété d’authentification sur le [définissant les propriétés de connexion](../../connect/jdbc/setting-the-connection-properties.md) page.  
  
 **Paramètres table**  
  
 Paramètres table fournissent un moyen simple de marshaler plusieurs lignes de données à partir d’une application cliente vers SQL Server sans avoir recours à plusieurs allers-retours ou à une logique côté serveur spéciale pour le traitement des données. Vous pouvez utiliser des paramètres table pour encapsuler des lignes de données dans une application cliente et envoyer les données au serveur dans une seule commande paramétrable. Les lignes de données entrantes sont stockées dans une variable de table qui peut être traitée à l’aide de Transact-SQL. Pour plus d’informations, consultez [Using Table-Valued paramètres](../../connect/jdbc/using-table-valued-parameters.md).  
  
 **Groupes de disponibilité AlwaysOn (AG)**  
  
 Le pilote prend désormais en charge les connexions transparentes aux groupes de disponibilité AlwaysOn. Le pilote détecte la topologie AlwaysOn actuelle de votre infrastructure serveur rapidement et se connecte au serveur actif actuel en toute transparence.  
  
## <a name="updates-in-microsoft-jdbc-driver-42-for-sql-server-and-later"></a>Mises à jour apportées à Microsoft JDBC Driver 4.2 pour SQL Server et versions ultérieures  
Microsoft JDBC Driver 4.2 pour SQL Server est entièrement conforme aux spécifications de JDBC 4.1 et 4.2. Les fichiers JAR contenues dans le package 4.2 sont nommées en fonction de leur conformité avec la version de l’API JDBC. Par exemple, le fichier sqljdbc42.jar à partir du package 4.2 est conforme à JDBC API 4.2. De même, le fichier sqljdbc41.jar est compatible avec l’API JDBC 4.1.

Pour garantir que vous avez le droit sqljdbc42.jar ou sqljdbc41.jar, exécutez les lignes de code suivantes. Si la sortie est « version du pilote : 4.2.6420.100 », vous disposez du package de JDBC Driver 4.2.
```
Connection conn = DriverManager.getConnection("jdbc:sqlserver://<server>;user=<user>;password=<password>;");
System.out.println("Driver version: " + conn.getMetaData().getDriverVersion());
```
 **Prise en charge de JDK 8**  
  
 Prise en charge de Java Development Kit (JDK) version 8.0 en plus de JDK 7.0, 6.0 et 5.0.  
  
 **JDBC 4.1 et 4.2**  
  
 Prise en charge des spécifications de l'API Java Database Connectivity 4.1 et 4.2, en plus de la version 4.0. Pour plus d’informations, consultez [conformité JDBC 4.1 pour le pilote JDBC](../../connect/jdbc/jdbc-4-1-compliance-for-the-jdbc-driver.md) et [mise en conformité de JDBC 4.2 pour le pilote JDBC](../../connect/jdbc/jdbc-4-2-compliance-for-the-jdbc-driver.md).  
  
 **Copie en bloc**  
  
 La fonctionnalité de copie en bloc est utilisée pour copier rapidement de grandes quantités de données dans des tables ou des vues de bases de données SQL Server. Pour plus d’informations, consultez [à l’aide de copie en bloc avec le pilote JDBC](../../connect/jdbc/using-bulk-copy-with-the-jdbc-driver.md).  
  
 **Option de restauration des transactions XA**  
  
 Ajout de nouvelles options de délai d'attente pour la restauration automatique existante des transactions non préparées. Pour plus de détails, consultez [compréhension des Transactions XA](../../connect/jdbc/understanding-xa-transactions.md).  
  
 **Nouvelle propriété de connexion principale Kerberos**  
  
 Ajout d'une nouvelle propriété de connexion pour faciliter la flexibilité avec les connexions Kerberos. Pour plus de détails, consultez [à l’aide de l’authentification intégrée Kerberos pour se connecter à SQL Server](../../connect/jdbc/using-kerberos-integrated-authentication-to-connect-to-sql-server.md).  
  
## <a name="updates-in-microsoft-jdbc-driver-41-for-sql-server-and-later"></a>Mises à jour apportées à Microsoft JDBC Driver 4.1 pour SQL Server et versions ultérieures  
 **Prise en charge de JDK 7**  
  
 Prise en charge de Java Development Kit (JDK) version 7.0, en plus des versions 6.0 et 5.0 de JDK.  
  
## <a name="updates-in-microsoft-jdbc-driver-40-for-sql-server-and-later"></a>Mises à jour apportées à Microsoft JDBC Driver 4.0 pour SQL Server et versions ultérieures  
 **Pour plus d’informations sur la connexion à une base de données SQL Azure**  
  
 Une rubrique comprenant des informations sur la connexion à une base de données SQL Azure a été ajoutée. Consultez [la connexion à une base de données SQL Azure](../../connect/jdbc/connecting-to-an-azure-sql-database.md) pour plus d’informations.  
  
 **Prise en charge pour la haute disponibilité, la récupération d’urgence**  
  
 Prise en charge pour les connexions de récupération d’urgence haute disponibilité, à des groupes de disponibilité AlwaysOn dans [!INCLUDE[ssSQL11](../../includes/sssql11_md.md)]. Consultez [prise en charge du pilote JDBC pour la haute disponibilité, la récupération d’urgence](../../connect/jdbc/jdbc-driver-support-for-high-availability-disaster-recovery.md) pour plus d’informations.  
  
 **À l’aide de l’authentification intégrée Kerberos pour se connecter à SQL Server**  
  
 Prise en charge de type 4 l’authentification intégrée Kerberos pour se connecter à [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] base de données. Pour plus d’informations, consultez [à l’aide de l’authentification intégrée Kerberos pour se connecter à SQL Server](../../connect/jdbc/using-kerberos-integrated-authentication-to-connect-to-sql-server.md). (Tapez 2 intégrée l’authentification Kerberos est disponible dans [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] versions antérieures à 4.0.)  
  
 **L’accès aux informations de Diagnostic dans le journal des événements étendus**  
  
 Vous pouvez accéder aux informations contenues dans le journal des événements étendus du serveur pour analyser les échecs de connexion. Pour plus d’informations, consultez [l’accès à des informations de Diagnostic dans le journal des événements étendus](../../connect/jdbc/accessing-diagnostic-information-in-the-extended-events-log.md).  
  
 **Prise en charge supplémentaire pour les colonnes éparses**  
  
 Si votre application a déjà accès aux données d’une table qui utilise des colonnes éparses, vous devriez constater une amélioration des performances. Vous pouvez obtenir des informations sur les colonnes (y compris les informations sur les colonnes éparses) avec [getColumns méthode &#40; SQLServerDatabaseMetaData &#41; ](../../connect/jdbc/reference/getcolumns-method-sqlserverdatabasemetadata.md). Pour plus d’informations sur [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] les colonnes éparses, consultez [à l’aide des colonnes éparses](http://go.microsoft.com/fwlink/?LinkId=224244).  
  
 **Xid.getFormatId**  
  
 À compter de [!INCLUDE[jdbc_40](../../includes/jdbc_40_md.md)], le pilote JDBC transmet l’identificateur de format de l’application vers le serveur de base de données. Pour obtenir le comportement mis à jour, vérifiez que le fichier sqljdbc_xa.dll est mis à jour. Pour plus d’informations sur la copie d’une version mise à jour de sqljdbc_xa.dll sur le serveur, consultez [compréhension des Transactions XA](../../connect/jdbc/understanding-xa-transactions.md).  
  
## <a name="itanium-not-supported-for-jdbc-driver-60-42-41-and-40-applications"></a>Itanium non pris en charge pour les Applications JDBC Driver 6.0, 4.2, 4.1 et 4.0  
  
 Pilotes Microsoft JDBC 6.0, 4.2, 4.1 et 4.0 pour les applications SQL Server ne sont pas pris en charge pour s’exécuter sur un ordinateur Itanium.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble du pilote JDBC](../../connect/jdbc/overview-of-the-jdbc-driver.md)  
  
  

