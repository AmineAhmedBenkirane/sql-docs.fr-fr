---
title: Installer les Packs d’administration SCOM (système de plateforme Analytique)
author: barbkess
ms.author: barbkess
manager: craigg
ms.prod: analytics-platform-system
ms.prod_service: mpp-data-warehouse
ms.service: ''
ms.component: ''
ms.technology: mpp-data-warehouse
ms.custom: ''
ms.date: 01/05/2017
ms.reviewer: na
ms.suite: sql
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ab3985d8-0a71-4b28-9d28-9886ae2a110f
caps.latest.revision: 16
ms.openlocfilehash: 2f05a947f09940fc1dd676ec6ca316863f567a7f
ms.sourcegitcommit: 9351e8b7b68f599a95fb8e76930ab886db737e5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2018
---
# <a name="install-the-scom-management-packs"></a>Installer les Packs d’administration SCOM
Suivez ces étapes pour télécharger et installer les packs d’administration de System Center Operations Manager (SCOM) pour SQL Server PDW. Les packs d’administration sont requises pour analyser SQL Server PDW de SCOM.  
  
## <a name="BeforeBegin"></a>Avant de commencer  
**Configuration requise**  
  
System Center Operations Manager doivent être installés et en cours d’exécution. SQL Server 2012 PDW nécessite System Center Operations Manager 2007 R2, System Center Operations Manager 2012 ou System Center Operations Manager 2012 service pack 1.  
  
## <a name="Step1"></a>Étape 1 : Télécharger les packs d’administration  
Pour la charge de travail APS PDW, téléchargez le [System Center Management Pack pour le système de plateforme Microsoft Analytique](http://go.microsoft.com/fwlink/?LinkId=396857).  
  
Pour la gestion du matériel, téléchargez le [Pack d’administration SQL Server Appliance Base](http://www.microsoft.com/en-us/download/details.aspx?displaylang=en&id=11436).  
  
Pour les versions antérieures de PDW sans points d’accès, téléchargez le[System Center Monitoring Pack pour Microsoft SQL Server 2012 parallèle données Warehouse Appliance](http://go.microsoft.com/fwlink/p/?LinkId=282661).  
  
Pour la charge de travail HDInsight, téléchargez le [System Center Management Pack pour HDInsight](http://go.microsoft.com/fwlink/?LinkId=390208).  
  
## <a name="Step2"></a>Étape 2 : Installer les packs d’administration  
  
### <a name="install-the-sql-server-appliance-base-management-pack"></a>Installer le Pack d’administration de Base SQL Server Appliance  
  
1.  Pour exécuter l’installation, double-cliquez sur le Pack de gestion Base téléchargé SQL Server Appliance.  
  
2.  Acceptez le contrat de licence, puis cliquez sur **suivant**.  
  
    ![Acceptez le contrat de licence](./media/install-the-scom-management-packs/SCOM_licnse_agrmt.png "SCOM_licnse_agrmt")  
  
3.  Sélectionnez votre dossier d’installation, ou utiliser la valeur par défaut du dossier d’Installation de pack d’administration.  
  
    ![Sélectionnez le dossier d’Installation](./media/install-the-scom-management-packs/SCOM_licnse_agrmt2.png "SCOM_licnse_agrmt2")  
  
4.  Cliquez sur **Installer**.  
  
    ![Confirmer l’installation](./media/install-the-scom-management-packs/SCOM_licnse_agrmt3.png "SCOM_licnse_agrmt3")  
  
5.  Cliquez sur **Fermer**.  
  
    ![Cliquez sur Fermer](./media/install-the-scom-management-packs/SCOM_licnse_agrmt4.png "SCOM_licnse_agrmt4")  
  
### <a name="install-the-monitoring-pack-for-sql-server-pdw-appliance"></a>Installer le Pack de surveillance pour SQL Server PDW Appliance  
  
1.  Pour exécuter l’installation, double-cliquez sur téléchargé SQL Server PDW Appliance Management Pack.  
  
2.  Acceptez le contrat de licence, puis cliquez sur **suivant**.  
  
    ![Acceptez le contrat de licence](./media/install-the-scom-management-packs/SCOM_licnse_agmtB.png "SCOM_licnse_agmtB")  
  
3.  Sélectionnez le répertoire qui contiendra les fichiers extraits. Le dossier d’installation de pack d’administration par défaut est affiché par défaut. Sélectionnez la valeur par défaut, ou sélectionner votre propre dossier d’installation.  
  
    ![Dossier d’installation sélectionnez](./media/install-the-scom-management-packs/SCOM_licnse_agmtB1.png "SCOM_licnse_agmtB1")  
  
4.  Cliquez sur **Installer**.  
  
    ![Confirmer l’installation](./media/install-the-scom-management-packs/SCOM_licnse_agmtB2.png "SCOM_licnse_agmtB2")  
  
5.  Cliquez sur **Fermer**.  
  
    ![Installation complète](./media/install-the-scom-management-packs/SCOM_licnse_agmtB3.png "SCOM_licnse_agmtB3")  
  
## <a name="next-step"></a>Étape suivante  
Maintenant que vous avez les packs d’administration installés, passez à l’étape suivante : [importer le Pack d’administration SCOM pour PDW &#40;système de plateforme Analytique&#41;](import-the-scom-management-pack-for-pdw.md).  
  
<!-- MISSING LINKS ## See Also  
[Common Metadata Query Examples &#40;SQL Server PDW&#41;](../sqlpdw/common-metadata-query-examples-sql-server-pdw.md)  -->  
  
