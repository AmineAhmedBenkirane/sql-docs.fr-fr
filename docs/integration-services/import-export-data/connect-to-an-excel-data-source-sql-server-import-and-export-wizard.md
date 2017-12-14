---
title: "Se connecter à une source de données Excel (Assistant Importation et Exportation SQL Server) | Microsoft Docs"
ms.custom: 
ms.date: 06/20/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: import-export-data
ms.reviewer: 
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43fbaca0-36d8-4583-9056-af7010209b87
caps.latest.revision: "12"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 2aeb225037970b8a77169db18c204ecf6d4c19d6
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="connect-to-an-excel-data-source-sql-server-import-and-export-wizard"></a>Se connecter à une source de données Excel (Assistant Importation et Exportation SQL Server)
Cette rubrique vous montre comment se connecter à une source de données **Microsoft Excel** à partir de la page **Choisir une source de données** ou **Choisir une destination** de l’Assistant Importation et Exportation SQL Server.

La capture d’écran suivante montre un exemple de connexion à un classeur Microsoft Excel.

![Connexion à Excel](../../integration-services/import-export-data/media/excel-connection.png) 

## <a name="options-to-specify"></a>Options à spécifier

> [!NOTE]
> Les options de connexion de ce fournisseur de données sont les mêmes, qu’Excel soit la source ou la destination. Autrement dit, les options que vous affichez sont identiques dans les pages **Choisir une source de données** et **Choisir une destination** de l’Assistant.

**Chemin de fichier Excel**  
 Spécifiez le chemin et le nom du fichier Excel. Exemple :
-   Pour un fichier sur un ordinateur local, **C:\\MyData.xlsx**.
-   Pour un fichier sur un partage réseau, **\\\\Ventes\\Base de données\\Northwind.xlsx**.

Ou cliquez sur **Parcourir**.  
  
 **Parcourir**  
 Permet de rechercher la feuille de calcul à l’aide de la boîte de dialogue **Ouvrir**.  

> [!NOTE]
> L’Assistant ne peut pas ouvrir un fichier Excel protégé par mot de passe.

 **Version Excel**  
Permet de sélectionner la version d’Excel utilisée par le classeur source.

> [!IMPORTANT]
> Vous pouvez être amené à télécharger et installer des fichiers supplémentaires pour vous connecter aux fichiers Excel. Pour plus d’informations, consultez [Se procurer les fichiers nécessaires pour se connecter à Excel](#officeDownloads).

**La première ligne possède des noms de colonnes**  
Indiquez si la première ligne de données contient des noms de colonne.
-   Si les données ne contiennent aucun nom de colonne et que vous activez cette option, l’Assistant traite la première ligne de données comme des noms de colonne.
-   Si les données contiennent des noms de colonne, mais que vous désactivez cette option, l’Assistant traite la ligne de noms de colonne comme étant la première ligne de données.

Si vous précisez que les données sources n’ont pas de noms de colonne, l’Assistant utilise F1, F2, et ainsi de suite comme titres de colonne.

## <a name="i-dont-see-excel-in-the-list-of-data-sources"></a>Je ne vois pas Excel dans la liste des sources de données
Si vous ne voyez pas Excel dans la liste des sources de données, utilisez-vous l’Assistant 64 bits ? Les fournisseurs pour Excel et Access sont généralement en 32 bits et ils ne sont donc pas visibles dans l’Assistant 64 bits. Exécutez l’Assistant 32 bits à la place.

> [!NOTE]
> Pour utiliser la version 64 bits de l’Assistant Importation et Exportation SQL Server, vous devez installer SQL Server. SQL Server Data Tools (SSDT) et SQL Server Management Studio (SSMS) sont des applications 32 bits qui installent uniquement des fichiers 32 bits, notamment la version 32 bits de l’Assistant.

## <a name="officeDownloads"></a>Se procurer les fichiers nécessaires pour se connecter à Excel  
Vous pouvez être amené à télécharger les composants de connectivité des sources de données Microsoft Office, notamment Excel et Access s’ils ne sont pas déjà installés. Téléchargez la dernière version des composants de connectivité pour les fichiers Excel et Access ici : [Microsoft Access Database Engine 2016 Redistributable](https://www.microsoft.com/download/details.aspx?id=54920).
  
La dernière version des composants peut ouvrir les fichiers créés dans des versions antérieures d’Excel.

Si la version 32 bits de Microsoft Office est installée sur l’ordinateur, vous devez installer la version 32 bits des composants et vérifier que vous exécutez le package en mode 32 bits.

Si vous avez un abonnement Office 365, veillez à télécharger Access Database Engine 2016 Redistributable et non Microsoft Access 2016 Runtime. Lorsque vous exécutez le programme d’installation, il est possible qu’un message d’erreur s’affiche indiquant que vous ne pouvez pas installer le téléchargement côte à côte avec les composants Office « Démarrer en un clic ». Pour contourner ce message d’erreur, exécutez l’installation en mode silencieux en ouvrant une fenêtre d’invite de commandes et en exécutant le fichier .EXE que vous avez téléchargé avec l’option `/quiet`. Exemple :

`C:\Users\<user name>\Downloads\AccessDatabaseEngine.exe /quiet`

## <a name="see-also"></a>Voir aussi
[Choisir une source de données](../../integration-services/import-export-data/choose-a-data-source-sql-server-import-and-export-wizard.md)  
[Choisir une destination](../../integration-services/import-export-data/choose-a-destination-sql-server-import-and-export-wizard.md)

