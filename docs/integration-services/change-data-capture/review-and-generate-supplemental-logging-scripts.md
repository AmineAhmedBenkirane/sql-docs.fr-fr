---
title: "Examiner et générer des Scripts de journalisation supplémentaires | Documents Microsoft"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scripts
ms.assetid: 5c858ae2-37d6-42e8-a252-7f6ed4e628a7
caps.latest.revision: 6
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: b3213f6e757e9fc3bcff63d0833d7f0c7fdee201
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---
# <a name="review-and-generate-supplemental-logging-scripts"></a>Examiner et générer des scripts de journalisation supplémentaires
  L’onglet **Scripts** permet d’exécuter ou de réexécuter un script sur la base de données source Oracle qui configure une journalisation supplémentaire.  
  
 Avant d'exécuter les scripts, sélectionnez l'une des opérations suivantes :  
  
 **Inclure les modifications de cette session**  
 Sélectionnez cette option pour exécuter le script sur toute nouvelle table qui a été ajoutée à l'instance de capture de données modifiées ou sur des tables qui ont été modifiées à l'aide de l'éditeur de propriétés.  
  
> [!NOTE]  
>  Si aucune modification n'a été apportée aux tables de l'instance de capture de données modifiées, la zone de script de journalisation supplémentaire Oracle est vide.  
  
 **Inclure toutes les tables/instances de capture**  
 Sélectionnez cette option pour exécuter le script sur toutes les tables et instances de capture dans l'instance de capture de données modifiées.  
  
 Après avoir sélectionné une de ces options, exécutez le script de journalisation supplémentaire.  
  
### <a name="to-run-the-supplemental-logging-scripts"></a>Pour exécuter les scripts de journalisation supplémentaire  
  
1.  Cliquez sur **Exécuter le script** pour exécuter le script de journalisation supplémentaire sur les tables définies pour l'instance de capture de données modifiées. Ce script demande à la base de données Oracle d'écrire toutes les colonnes d'intérêt dans ses journaux des transactions lors de la journalisation des opérations de mise à jour (UPDATE) dans les tables capturées. Ce script est normalement examiné et exécuté par un administrateur système Oracle.  
  
2.  Lorsque vous exécutez des scripts de journalisation supplémentaires, la boîte de dialogue des informations d'identification Oracle pour l'exécution de script s'ouvre et vous permet de spécifier un nom d'utilisateur et un mot de passe Oracle valides. Pour plus d'informations sur la façon de fournir les informations d'identification Oracle appropriées, consultez [Oracle Credentials for Running Script](../../integration-services/change-data-capture/oracle-credentials-for-running-script.md).  
  
 Vous pouvez également exécuter les scripts manuellement à l'aide de SQL*PLUS, si nécessaire.  
  
### <a name="to-run-the-scripts-manually"></a>Pour exécuter les script manuellement  
  
1.  Cliquez sur **Copier** pour coller le script dans le Presse-papiers. Ouvrez SQL*PLUS et accédez au répertoire contenant votre base de données source Oracle. Collez le script dans SQL\*Plus pour l’exécuter.  
  
### <a name="to-save-the-supplemental-logging-script-in-a-text-file"></a>Pour enregistrer le script de journalisation supplémentaire dans un fichier texte  
  
1.  Cliquez sur **Enregistrer sous** et accédez à l'emplacement où vous souhaitez enregistrer le fichier.  
  
2.  Donnez un nom au fichier, puis cliquez sur **Enregistrer** pour enregistrer le fichier.  
  
## <a name="see-also"></a>Voir aussi  
 [Comment modifier les propriétés d’Instance de capture de données modifiées](../../integration-services/change-data-capture/how-to-edit-the-cdc-instance-properties.md)   
 [Informations d’identification Oracle pour l’exécution de Script](../../integration-services/change-data-capture/oracle-credentials-for-running-script.md)  
  
  
