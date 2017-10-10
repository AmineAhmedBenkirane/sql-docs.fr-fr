---
title: "Comment éviter les erreurs sur les packages R sont installés dans les bibliothèques utilisateur | Documents Microsoft"
ms.custom: 
ms.date: 09/29/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- r-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99ffd9b8-aa6d-4ac2-9840-4e66d0463978
caps.latest.revision: 2
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 29122bdf543e82c1f429cf401b5fe1d8383515fc
ms.openlocfilehash: 0de06ebee16d903b4b00c9d8e4673bf450c485d1
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="avoiding-errors-on-r-packages-installed-in-user-libraries"></a>Comment éviter les erreurs sur les packages R sont installés dans les bibliothèques utilisateur

Les utilisateurs expérimentés de R sont habitués à l’installation des packages R dans une bibliothèque de l’utilisateur, chaque fois que la bibliothèque par défaut est bloqué ou non disponible. Toutefois, cette approche n’est pas pris en charge dans SQL Server, et l’installation dans une bibliothèque de l’utilisateur se termine généralement une erreur « package introuvable ».

Cette rubrique fournit des solutions de contournement pour vous aider à éviter cette erreur. Il explique comment vous pouvez modifier votre code R et suggère le processus d’installation de package R correct pour l’utilisation de packages R à partir d’une instance de SQL Server.

## <a name="why-r-user-libraries-cannot-be-accessed-from-sql-server"></a>Pourquoi les bibliothèques d’utilisateur R ne sont pas accessibles à partir de SQL Server

Les développeurs R qui ont besoin d’installer de nouveaux packages R sont habitués à l’installation des packages à volonté et à l’aide d’une bibliothèque d’utilisateur privé, chaque fois que la bibliothèque par défaut n’est pas disponible, ou lorsque le développeur n’est pas un administrateur sur l’ordinateur.

Par exemple, dans un environnement de développement R classique, l’utilisateur devez ajouter l’emplacement du package à la variable d’environnement R `libPath`, ou référence le chemin d’accès complet du package, comme suit :

```R
library("c:/Users/<username>/R/win-library/packagename")  
```

Toutefois, cela peut ne jamais fonctionne lors de l’exécution des solutions R dans SQL Server, car les packages R doivent être installés dans une bibliothèque spécifique par défaut qui est associée à l’instance.

Sinon, vous risquez d’obtenir ce type d’erreur quand vous essayez d’appeler le package :

*Erreur dans library(xxx) : il n’existe aucun package appelé 'package-name'*

Il est également une pratique de développement incorrecte pour installer les packages R requis dans une bibliothèque d’utilisateur personnalisée, tel qu’il peut entraîner des erreurs si une solution est exécutée par un autre utilisateur qui n’a pas accès à l’emplacement de la bibliothèque.

## <a name="how-to-install-r-packages-to-an-accessible-library"></a>Comment installer des packages R pour une bibliothèque accessible

**Pour SQL Server 2016**

Utilisez la bibliothèque de package associée à l’instance. Pour plus d’informations, consultez [packages R sont installés avec SQL Server](installing-and-managing-r-packages.md)

**Pour SQL Server 2017**

SQL Server fournit des fonctionnalités pour vous aider à gérer plusieurs versions de package et d’autoriser les utilisateurs à des packages individuels, sans nécessiter que les utilisateurs ont accès au système de fichiers.

Pour plus d’informations sur la façon de configurer une bibliothèque de package partagé et affecter des utilisateurs aux rôles, consultez [gestion des packages R pour SQL Server](r-package-management-for-sql-server-r-services.md).

Si vous prenez l’approche de gestion de package basée sur les rôles de base de données, il n’est pas nécessaire d’installer plusieurs copies du même package dans les répertoires de l’autre utilisateur. Installer une seule copie du package que vous avez besoin et le partager avec des utilisateurs authentifiés. Étant donné que les packages sont gérées au niveau de la base de données, vous pouvez également copier des groupes, des packages et des autorisations associées entre bases de données.

## <a name="tips-for-avoiding-package-not-found-errors"></a>Conseils pour éviter des erreurs « package introuvable »

+ Modifier le code afin d’éliminer les dépendances vis-à-vis des bibliothèques de l’utilisateur. Lorsque vous migrez des solutions R à exécuter dans [!INCLUDE [ssNoVersion_md](..\..\includes\ssnoversion-md.md)], il est important que vous procédez comme suit :

    + Installer les packages dont vous avez besoin pour la bibliothèque par défaut associée à l’instance.

    + Modifier le code pour vous assurer que les packages sont chargés à partir de la bibliothèque par défaut, et non à partir de répertoires ad hoc ou les bibliothèques utilisateur.

+ Évitez d’installation du package ad hoc dans le cadre d’une solution. Vérifiez votre code pour vous assurer qu’il n’y a aucun appel à des packages désinstallés ou le code qui installe les packages de façon dynamique. Si vous n’êtes pas autorisé, le code échoue, et si vous ne disposez pas des autorisations, vous devez installer séparément les packages à partir de tout autre code que vous souhaitez exécuter.

+ Modifier les chemins d’accès directs aux bibliothèques de package de R. Si un package est installé dans la bibliothèque par défaut, le runtime R charge ce package à partir de la bibliothèque par défaut, même si une autre bibliothèque est spécifiée dans le code R.

