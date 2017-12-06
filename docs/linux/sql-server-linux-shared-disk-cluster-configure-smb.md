---
title: Configurer le stockage instance cluster de basculement SMB - SQL Server sur Linux | Documents Microsoft
description: 
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.date: 08/28/2017
ms.topic: article
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: sql-linux
ms.suite: sql
ms.custom: 
ms.technology: database-engine
ms.workload: Inactive
ms.openlocfilehash: 8043cd57758749399500b206410694c1735b30e8
ms.sourcegitcommit: 531d0245f4b2730fad623a7aa61df1422c255edc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/01/2017
---
# <a name="configure-failover-cluster-instance---smb---sql-server-on-linux"></a>Configuration d’instance de cluster de basculement - SMB - SQL Server sur Linux

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

Cet article explique comment configurer le stockage SMB pour une instance de cluster de basculement (FCI) sur Linux. 
 
Dans le monde non Windows, SMB est souvent désigné comme un commun CIFS Internet File System () partagent et implémentée via Samba. Dans l’univers Windows, l’accès à un partage SMB s’effectue ainsi : \\Nom_Serveur\Nom_Partage. Pour les installations de SQL serveur Linux, le partage SMB doit être monté en tant que dossier.

## <a name="important-source-and-server-information"></a>Informations importantes sur la source et le serveur

Voici quelques conseils et les remarques à l’utilisation de SMB :
- Le partage SMB peut être sur Windows, Linux, ou même à partir d’une application en tant qu’il utilise SMB 3.0 ou version ultérieure. Pour plus d’informations sur Samba et SMB 3.0, consultez [SMB 3.0](https://wiki.samba.org/index.php/Samba3/SMB2#SMB_3.0) pour voir si votre implémentation Samba est compatible avec SMB 3.0.
- Le partage SMB doit être hautement disponible.
- La sécurité doit être définie correctement sur le partage SMB. Voici un exemple de /etc/samba/smb.conf, où SQLData1 est le nom du partage.

![05-smbsource][1]

## <a name="instructions"></a>Instructions

1.  Dans la configuration ICF, choisissez un des serveurs participant à la. Quel que soit l’application.

2.  Obtenir des informations relatives à l’utilisateur mssql.

    ```bash
    sudo id mssql
    ```
    
    Notez l’uid, gid et les groupes. 

3. Exécutez `sudo smbclient -L //NameOrIP/ShareName -U User`.

    \<NameOrIP > est le nom DNS ou l’adresse IP du serveur hébergeant le partage SMB.

    \<Nom de partage > est le nom du partage SMB. 

4. Pour le système de bases de données ou les informations stockées dans l’emplacement de données par défaut, procédez comme suit. Sinon, passez à l’étape 5. 

   *    Vérifiez que SQL Server est arrêté sur le serveur que vous utilisez.
    ```bash
    sudo systemctl stop mssql-server
    sudo systemctl status mssql-server
    ```

   *    Commutateur entièrement le super utilisateur. Vous ne recevrez pas tout accusé de réception en cas de réussite.

    ```bash
    sudo -i
    ```

   *    Basculer vers l’utilisateur mssql. Vous ne recevrez pas tout accusé de réception en cas de réussite.

    ```bash
    su mssql
    ```

   *    Créez un répertoire temporaire pour stocker les données de SQL Server et les fichiers journaux. Vous ne recevrez pas tout accusé de réception en cas de réussite.

    ```bash
    mkdir <TempDir>
    ```

    <TempDir>est le nom du dossier. L’exemple suivant crée un dossier nommé /var/opt/mssql/tmp.

    ```bash
    mkdir /var/opt/mssql/tmp
    ```

   *    Copiez les fichiers journaux et de données de SQL Server dans le répertoire temporaire. Vous ne recevrez pas tout accusé de réception en cas de réussite.

    ```bash
    cp /var/opt/mssql/data/* <TempDir>
    ```

    \<TempDir > est le nom du dossier à partir de l’étape précédente.
    
   *    Vérifiez que les fichiers se trouvent dans le répertoire.

    ```bash
    ls <TempDir>
    ```

    \<TempDir > est le nom du dossier à partir de l’étape d.
    
   *    Supprimez les fichiers à partir du répertoire de données SQL Server existant. Vous ne recevrez pas tout accusé de réception en cas de réussite.
 
    ```bash
    rm – f /var/opt/mssql/data/*
    ```

   *    Vérifiez que les fichiers ont été supprimés. 

    ```bash
    ls /var/opt/mssql/data
    ```
 
   *    Tapez exit pour revenir à l’utilisateur racine.

   *    Montez le partage SMB dans le dossier de données SQL Server. Vous ne recevrez pas tout accusé de réception en cas de réussite. Cet exemple montre la syntaxe permettant de se connecter à un partage Windows serveur SMB 3.0.

    ```bash
    Mount -t cifs //<ServerName>/<ShareName> /var/opt/mssql/data -o vers=3.0,username=<UserName>,password=<Password>,domain=<domain>,uid=<mssqlUID>,gid=<mssqlGID>,file_mode=0777,dir_mode=0777
    ```

    \<ServerName > est le nom du serveur avec le partage SMB
    
    \<Nom de partage > est le nom du partage

    \<Nom d’utilisateur > est le nom de l’utilisateur pour accéder au partage

    \<Mot de passe > est le mot de passe pour l’utilisateur

    \<domaine > est le nom d’Active Directory

    \<mssqlUID > est l’UID de l’utilisateur mssql 
 
    \<mssqlGID > est codé de l’utilisateur mssql
 
   *    Vérifiez que le montage a réussi en émettant un montage sans commutateurs.

    ```bash
    mount
    ```
 
   *    Basculez vers l’utilisateur mssql. Vous ne recevrez pas tout accusé de réception en cas de réussite.

    ```bash
    su mssql
    ```

   *    Copiez les fichiers à partir du répertoire temporaire /var/opt/mssql/data. Vous ne recevrez pas tout accusé de réception en cas de réussite.

    ```bash
    cp /var/opt/mssql/tmp/* /var/opt/mssql/data
    ```

   *    Vérifiez les fichiers.

    ```bash
    ls /var/opt/mssql/data
    ```

   *    Entrez exit pour ne pas être mssql 

   *    Entrez exit pour être racine

   *    Démarrez SQL Server. Si tout a été correctement copié et sécurité appliquée, SQL Server doit afficher correctement a démarré.

    ```bash
    sudo systemctl start mssql-server
    sudo systemctl status mssql-server
    ```
 
   *    Pour tester plus, créez une base de données pour vérifier que les autorisations sont correctement. L’exemple ci-dessous utilise Transact-SQL ; Vous pouvez utiliser SSMS.

    ![10_testcreatedb][2] 
  
   *    Arrêt de SQL Server et vérifiez qu’il est arrêté. Si vous vous apprêtez à ajouter ou autres disques de test, n’arrêtez pas SQL Server jusqu'à ce que ceux sont ajoutés et testés.

    ```bash
    sudo systemctl stop mssql-server
    sudo systemctl status mssql-server
    ```

   *    Uniquement si vous avez terminé, démontez le partage. Si ce n’est pas le cas, démontez après avoir terminé le test / d’ajout des disques supplémentaires.

    ```bash
    sudo umount //<IPAddressorServerName>/<ShareName /<FolderMountedIn>
    ```

    \<IPAddressOrServerName > est l’adresse IP ou le nom de l’hôte SMB

    \<Nom de partage > est le nom du partage
    
    \<FolderMountedIn > est le nom du dossier où est monté SMB

5.  Pour les éléments autres que des bases de données système, telles que les bases de données utilisateur ou des sauvegardes, procédez comme suit. Si uniquement à l’aide de l’emplacement par défaut, passez à l’étape 14.
    
   *    Commutateur le super utilisateur. Vous ne recevrez pas tout accusé de réception en cas de réussite.

    ```bash
    sudo -i
    ```
    
   *    Créez un dossier qui sera utilisé par SQL Server. 

    ```bash
    mkdir <FolderName>
    ```

    \<Nom_dossier > est le nom du dossier. Le chemin du dossier complet sera doivent être spécifiés if pas au bon emplacement. L’exemple suivant crée un dossier nommé /var/opt/mssql/userdata.

    ```bash
    mkdir /var/opt/mssql/userdata
    ```

   *    Montez le partage SMB dans le dossier de données SQL Server. Vous ne recevrez pas tout accusé de réception en cas de réussite. Cet exemple montre la syntaxe permettant de se connecter à un partage en fonction de Samba SMB 3.0.

    ```bash
    Mount -t cifs //<ServerName>/<ShareName> <FolderName> -o vers=3.0,username=<UserName>,password=<Password>,uid=<mssqlUID>,gid=<mssqlGID>,file_mode=0777,dir_mode=0777
    ```

    \<ServerName > est le nom du serveur avec le partage SMB

    \<Nom de partage > est le nom du partage

    \<Nom_dossier > est le nom du dossier créé dans la dernière étape  

    \<Nom d’utilisateur > est le nom de l’utilisateur pour accéder au partage

    \<Mot de passe > est le mot de passe pour l’utilisateur

    \<mssqlUID > est l’UID de l’utilisateur mssql

    \<mssqlGID > est codé de l’utilisateur mssql.
 
   * Vérifiez que le montage a réussi en émettant un montage sans commutateurs.
 
   * Type de sortie ne peut plus être le super utilisateur.

   * Pour tester, créez une base de données dans ce dossier. L’exemple ci-dessous utilise sqlcmd pour créer une base de données, basculer vers elle, vérifiez les fichiers existent au niveau du système d’exploitation, puis supprime l’emplacement temporaire. Vous pouvez utiliser SSMS.
 
   * Démontez le partage 

    ```bash
    sudo umount //<IPAddressorServerName>/<ShareName> /<FolderMountedIn>
    ```
    
    \<IPAddressOrServerName > est l’adresse IP ou le nom de l’hôte SMB
 
    \<Nom de partage > est le nom du partage
 
    \<FolderMountedIn > est le nom du dossier où SMB est monté.
 
6.  Répétez les étapes sur les autres nœuds.

Vous êtes maintenant prêt à configurer l’instance FCI.

## <a name="next-steps"></a>Étapes suivantes

[Configurer l’instance de cluster de basculement - SQL Server sur Linux](sql-server-linux-shared-disk-cluster-configure.md)

<!--Image references-->
[1]: ./media/sql-server-linux-shared-disk-cluster-configure-smb/05-smbsource.png 
[2]: ./media/sql-server-linux-shared-disk-cluster-configure-smb/10-testcreatedb.png 
