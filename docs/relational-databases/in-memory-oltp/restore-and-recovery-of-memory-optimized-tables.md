---
title: "Restauration et r&#233;cup&#233;ration de tables m&#233;moire optimis&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine-imoltp"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 294975b7-e7d1-491b-b66a-fdb1100d2acc
caps.latest.revision: 10
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 10
---
# Restauration et r&#233;cup&#233;ration de tables m&#233;moire optimis&#233;es
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Le mécanisme de base utilisé pour récupérer ou restaurer une base de données avec des tables mémoire optimisées est similaire à celui utilisé pour les bases de données avec uniquement des tables sur disque. Mais à la différence des tables sur disque, les tables mémoire optimisées doivent être chargées dans la mémoire avant que la base de données soit disponible pour l'accès utilisateur. Cela ajoute une nouvelle étape à la récupération de la base de données.  
  
 Lors des opérations de récupération et de restauration, le moteur de l'OLTP en mémoire lit les fichiers delta et de données pour charger les données dans la mémoire physique. Le temps de chargement est déterminé par les facteurs suivants :  
  
-   Quantité de données à charger.  
  
-   Bande passante d'E/S séquentielle.  
  
-   Degré de parallélisme, déterminé par le nombre de conteneurs de fichiers et de noyaux de processeur.  
  
-   Nombre d'enregistrements de journal dans la partie active du journal devant être restaurés par progression.  
  
 Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] redémarre, chaque base de données passe via une phase de récupération qui comprend les trois phases suivantes :  
  
1.  Phase d'analyse. Pendant cette phase, un test est effectué sur les journaux des transactions actifs pour détecter les transactions validées et enregistrées. Le moteur OLTP en mémoire identifie le point de contrôle à charger et précharge ses entrées de journal de table système. Il traite également certains enregistrements du journal d'allocation de fichier.  
  
2.  Phase de restauration par progression. Cette étape est exécutée simultanément sur les tables sur disque et sur les tables mémoire optimisées.  
  
     Pour les tables sur disque, la base de données est déplacée à la date et heure actuelles et obtient les verrous pris par les transactions non validées.  
  
     Pour les tables mémoire optimisées, les données des paires de fichiers de données et delta sont chargées dans la mémoire puis mises à jour avec le journal des transactions actif en fonction du dernier point de contrôle durable.  
  
     Lorsque les opérations sur les tables sur disque et sur les tables mémoire optimisées sont terminées, la base de données est accessible.  
  
3.  Phase de restauration. Au cours de cette phase, les transactions non validées sont restaurées.  
  
 Le chargement des tables mémoire optimisées dans la mémoire peut affecter les performances de l'objectif de temps de récupération (RTO). Pour améliorer le temps de chargement des données mémoire optimisées à partir des fichiers de données et des fichiers delta, le moteur de l'OLTP en mémoire charge les fichiers de données/delta en parallèle, comme suit :  
  
-   Création d'un filtre de mappage de delta. Le magasin de fichiers delta référence les lignes supprimées. Un thread par conteneur lit les fichiers delta et crée un filtre de mappage de delta. (Un groupe de fichiers de données mémoire optimisé peut avoir un ou plusieurs conteneurs.)  
  
-   Flux des fichiers de données.  Une fois le filtre de mappage de delta créé, les fichiers de données sont lus en utilisant autant de thread qu'il existe d'UC logiques. Chaque thread qui lit le fichier de données lit les lignes de données, vérifie le mappage de delta associé et insère la ligne dans la table uniquement si cette ligne n'a pas été marquée comme supprimée. Cette partie de la récupération peut être liée à l'UC dans certains cas, comme indiqué ci-dessous.  
  
 ![Tables optimisées en mémoire.](../../relational-databases/in-memory-oltp/media/memory-optimized-tables.gif "Tables optimisées en mémoire.")  
  
 Les tables mémoire optimisées peuvent généralement être chargées dans la mémoire à la vitesse des E/S mais dans certains cas, le chargement des lignes de données dans la mémoire est plus lent. Les cas spécifiques sont les suivants :  
  
-   Un nombre de compartiments faible pour l'index de hachage peut entraîner une collision excessive ralentissant les insertions des lignes de données. Cela entraîne généralement une très forte utilisation du processeur tout le long, et en particulier à la fin de la récupération. Si vous avez configuré l'index de hachage correctement, il ne devrait pas affecter le temps de récupération.  
  
-   Dans les tables mémoire optimisées avec un ou plusieurs index non cluster, contrairement à un index de hachage dont le nombre de compartiments est dimensionné lors de la création, les index non cluster augmentent dynamiquement, ce qui entraîne une forte utilisation de l'UC.  
  
## Voir aussi  
 [Sauvegarder, restaurer et récupérer des tables optimisées en mémoire](../Topic/Backup,%20Restore,%20and%20Recovery%20of%20Memory-Optimized%20Tables.md)  
  
  