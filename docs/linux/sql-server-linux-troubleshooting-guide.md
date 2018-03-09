﻿---
title: "Résoudre les problèmes de SQL Server sur Linux | Documents Microsoft"
description: "Fournit des conseils de dépannage pour l’utilisation de SQL Server 2017 sur Linux."
author: annashres
ms.author: anshrest
manager: craigg
ms.date: 02/22/2018
ms.topic: article
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: 
ms.suite: sql
ms.custom: sql-linux
ms.technology: database-engine
ms.assetid: 99636ee8-2ba6-4316-88e0-121988eebcf9S
ms.workload: On Demand
ms.openlocfilehash: b3dc37601859ee4125f9f7885592e3a0653e8d0c
ms.sourcegitcommit: f0c5e37c138be5fb2cbb93e9f2ded307665b54ea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/24/2018
---
# <a name="troubleshoot-sql-server-on-linux"></a>Résoudre les problèmes de SQL Server sur Linux

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-linuxonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-linuxonly.md)]

Ce document décrit comment résoudre les problèmes de Microsoft SQL Server s'exécutant sur Linux ou dans un conteneur Docker. Lors du dépannage de SQL Server sur Linux, n’oubliez pas de consulter les fonctionnalités prises en charge et les limitations connues dans les [notes de publication de SQL Server sur Linux](sql-server-linux-release-notes.md).

> [!TIP]
> Pour obtenir des réponses aux questions fréquemment posées, consultez le [SQL Server sur le Forum aux questions sur Linux](sql-server-linux-faq.md).

## <a id="connection"></a> Résoudre les échecs de connexion
Si vous rencontrez des difficultés pour vous connecter à votre serveur SQL de Linux, il existe quelques éléments à vérifier. 

- Vérifiez que le nom du serveur ou l’adresse IP est accessible à partir de votre ordinateur client.

   > [!TIP]
   > Pour rechercher l’adresse IP de votre machine Ubuntu, vous pouvez exécuter la commande ifconfig comme dans l’exemple suivant :
   >
   >   ```bash
   >   sudo ifconfig eth0 | grep 'inet addr'
   >   ```
   > Pour Red Hat, vous pouvez utiliser l’adresse ip, comme dans l’exemple suivant :
   >
   >   ```bash
   >   sudo ip addr show eth0 | grep "inet"
   >   ```
   > Une exception à cette technique concerne les machines virtuelles Azure. Pour les machines virtuelles Azure, [rechercher l’adresse IP publique de la machine virtuelle dans le portail Azure](https://docs.microsoft.com/azure/virtual-machines/linux/sql/provision-sql-server-linux-virtual-machine#connect).

- Le cas échéant, vérifiez que vous avez ouvert le port SQL Server (1433 par défaut) sur le pare-feu.

- Pour les machines virtuelles Azure, vérifiez que vous avez une [règle de groupe de sécurité réseau pour le port de SQL Server par défaut](https://docs.microsoft.com/azure/virtual-machines/linux/sql/provision-sql-server-linux-virtual-machine#remote).

- Vérifiez que le nom d’utilisateur et le mot de passe ne contiennent pas de fautes de frappe, ni d'espaces, ni une casse incorrecte.

- Essayez de définir explicitement le numéro de port et de protocole avec le nom du serveur à l’exemple suivant : **tcp:servername, 1433**.

- Des problèmes de connectivité réseau peuvent également entraîner des délais d’attente et des erreurs de connexion. Après avoir vérifié vos informations de connexion et la connectivité réseau, recommencez l’opération.

## <a name="manage-the-sql-server-service"></a>Gérer le service SQL Server

Les sections suivantes montrent comment démarrer, arrêter, redémarrer et vérifier l’état du service SQL Server. 

### <a name="manage-the-mssql-server-service-in-red-hat-enterprise-linux-rhel-and-ubuntu"></a>Gérer le service mssql-server sous Red Hat Enterprise Linux (RHEL) et Ubuntu 

Vérifiez l’état du service SQL Server à l’aide de cette commande :

   ```bash
   sudo systemctl status mssql-server
   ```

Vous pouvez arrêter, démarrer ou redémarrer le service SQL Server en fonction des besoins à l’aide des commandes suivantes :

   ```bash
   sudo systemctl stop mssql-server
   sudo systemctl start mssql-server
   sudo systemctl restart mssql-server
   ```

### <a name="manage-the-execution-of-the-mssql-docker-container"></a>Gérer l’exécution du conteneur Docker mssql

Vous pouvez obtenir l’ID de conteneur et d’état du dernier conteneur Docker de serveur SQL créé en exécutant la commande suivante (l’ID est sous le **ID de conteneur** colonne) :

   ```bash
   sudo docker ps -l
   ```
   
Vous pouvez arrêter ou redémarrer le service SQL Server en fonction des besoins à l’aide des commandes suivantes :
   
   ```bash
   sudo docker stop <container ID>
   sudo docker restart <container ID>
   ```

> [!TIP]
> Pour obtenir des conseils de dépannage supplémentaires pour Docker, consultez [conteneurs dépannage de SQL Server Docker](sql-server-linux-configure-docker.md#troubleshooting).

## <a name="access-the-log-files"></a>Accéder aux fichiers journaux
   
SQL Server stocke ses journaux dans le fichier /var/opt/mssql/log/errorlog dans les installations sous Linux et Docker. Vous devez être en mode de 'super utilisateur' pour parcourir ce répertoire.

Le programme d’installation enregistre ici : /var/opt/mssql/setup-<horodatage qui représente l'heure d’installation> Vous pouvez parcourir les fichiers journaux des erreurs avec n’importe quel outil compatible UTF-16 tel que « vim » ou « cat » comme suit : 

   ```bash
   sudo cat errorlog
   ```

Si vous préférez, vous pouvez également convertir les fichiers vers UTF-8 pour les lire avec « more » ou « less » avec la commande suivante :
   
   ```bash
   sudo iconv –f UTF-16LE –t UTF-8 <errorlog> -o <output errorlog file>
   ```
## <a name="extended-events"></a>Événements étendus

Les événements étendus peuvent être interrogées via une commande SQL. Plus d’informations sur les événements étendus accessibles [ici](https://technet.microsoft.com/en-us/library/bb630282.aspx):

## <a name="crash-dumps"></a>Vidages sur incident 

Recherchez les vidages dans le répertoire de journaux dans Linux. Recherchez dans le répertoire /var/opt/mssql/log les vidages Linux Core (extension .tar.gz2) ou les mini-vidages SQL (extension .mdmp)

Pour les vidages 
   ```bash
   sudo ls /var/opt/mssql/log | grep .tar.gz2 
   ```

Pour les sauvegardes SQL 
   ```bash
   sudo ls /var/opt/mssql/log | grep .mdmp 
   ```
   
## <a name="start-sql-server-in-minimal-configuration-or-in-single-user-mode"></a>Démarrage de SQL Server dans une Configuration minimale ou en Mode mono-utilisateur

### <a name="start-sql-server-in-minimal-configuration-mode"></a>Démarrage de SQL Server en Mode Configuration minimale
Cette option est utile lorsqu'une valeur de configuration définie (espace mémoire insuffisant, par exemple) a empêché le serveur de démarrer.
  
   ```bash
   sudo -u mssql /opt/mssql/bin/sqlservr -f
   ```

### <a name="start-sql-server-in-single-user-mode"></a>Démarrage de SQL Server en Mode mono-utilisateur
Vous pouvez par exemple vouloir modifier les options de configuration du serveur ou rétablir une base de données maître ou une autre base de données système endommagée. Par exemple, vous pouvez vouloir modifier les options de configuration du serveur ou récupérer une base de données maître endommagée ou une autre base de données système   

Démarrage de SQL Server en Mode mono-utilisateur
   ```bash
   sudo -u mssql /opt/mssql/bin/sqlservr -m
   ```

Démarrage de SQL Server en Mode mono-utilisateur avec SQLCMD
   ```bash
   sudo -u mssql /opt/mssql/bin/sqlservr -m SQLCMD
   ```
  
> [!WARNING]  
>  Démarrez SQL Server sur Linux avec l’utilisateur « mssql » afin d’éviter les problèmes de démarrage futurs. Exemple « sudo -u mssql /opt/mssql/bin/sqlservr [OPTIONS DE DÉMARRAGE] » 

Si vous avez démarré par inadvertance SQL Server avec un autre utilisateur, vous devez changer la propriété des fichiers de base de données SQL Server pour l'attribuer à l’utilisateur 'mssql' avant de démarrer SQL Server avec systemd. Par exemple, exécutez la commande suivante pour modifier la propriété de tous les fichiers de base de données sous /var/opt/mssql sur l’utilisateur « mssql »

   ```bash
   chown -R mssql:mssql /var/opt/mssql/
   ```

## <a name="common-issues"></a>Problèmes courants

1. Impossible de se connecter à votre instance de SQL Server à distance.

   Consultez la section Dépannage de l’article, [se connecter à SQL Server sur Linux](#connection).

2. Erreur : Le nom d’hôte doit compter 15 caractères maximum.

   Il s’agit d’un problème connu qui se produit chaque fois que le nom de l’ordinateur sur lequel on tente d’installer le package Debian SQL Server est supérieur à 15 caractères. Il n’existe actuellement aucune solution de contournement autre que la modification du nom de l’ordinateur. Une façon d’effectuer cette opération est de modifier le fichier de nom d’hôte et de redémarrer l’ordinateur. Les éléments suivants [guide Web](http://www.cyberciti.biz/faq/ubuntu-change-hostname-command/) explique cela en détail.

3. La réinitialisation de mot de passe système (SA) d’administration.

   Si vous avez oublié le mot de passe d’administrateur système ou que vous devez le réinitialiser pour une raison quelconque, procédez comme suit.

   > [!NOTE]
   > Les étapes suivantes arrêter le service SQL Server temporairement.

   Se connecter dans le terminal de l’ordinateur hôte, exécutez les commandes suivantes, suivez les invites pour réinitialiser le mot de passe SA :

   ```bash
   sudo systemctl stop mssql-server
   sudo /opt/mssql/bin/mssql-conf setup
   ```

4. Utiliser des caractères spéciaux dans le mot de passe.

   Si vous utilisez des caractères dans le mot de passe du compte de connexion SQL Server, vous devrez peut-être d’échappement lors de leur utilisation dans le terminal Linux. Vous devez isoler le $ à tout moment à l’aide de la barre oblique vous l’utilisez dans un script de shell de commande/Terminal Server :

   Ne fonctionne pas :

   ```bash
   sudo sqlcmd -S myserver -U sa -P Test$$
   ```

   Fonctionne :

   ```bash
   sqlcmd -S myserver -U sa -P Test\$\$
   ```

   Ressources : [des caractères spéciaux](http://tldp.org/LDP/abs/html/special-chars.html)
   [Escaping](http://tldp.org/LDP/abs/html/escapingsection.html)

[!INCLUDE[Get Help Options](../includes/paragraph-content/get-help-options.md)]
