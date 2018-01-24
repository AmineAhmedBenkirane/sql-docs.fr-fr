---
title: "Procédures stockées système XML | Microsoft Docs"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: xml
ms.reviewer: 
ms.suite: sql
ms.technology: dbe-xml
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system stored procedures [SQL Server], XML
- sp_xml_removedocument
- OPENXML statement, system stored procedures
- sp_xml_preparedocument
- XML [SQL Server], system stored procedures
ms.assetid: e60c7f85-6823-4d28-93d6-b053d08cc830
caps.latest.revision: "27"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 3c1c1927af5850eaed93430ce47e45ef9eb71b24
ms.sourcegitcommit: 6c54e67818ec7b0a2e3c1f6e8aca0fdf65e6625f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2018
---
# <a name="xml-system-stored-procedures"></a>Procédures stockées système XML
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)] SQL Server propose les procédures stockées système suivantes utilisées en conjonction avec la clause OPENXML :  
  
-   [sp_xml_preparedocument &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql.md)  
  
-   [sp_xml_removedocument &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql.md)  
  
 Pour écrire des requêtes à l’aide d’OPENXML, vous devez d’abord créer une représentation interne du document XML en appelant **sp_xml_preparedocument**. Celle-ci renvoie un descripteur vers la représentation interne du document XML. Ce descripteur est ensuite transmis à OPENXML. OPENXML fournit des vues sur les ensembles de lignes du document s'appuyant sur des chemins XPaths. Plus précisément, ces vues correspondent à un modèle de ligne et à un ou plusieurs modèles de colonnes.  
  
> [!NOTE]  
>  Le descripteur du document renvoyé par **sp_xml_preparedocument** reste valide pendant toute la durée de la session.  
  
 Vous pouvez supprimer la représentation interne d’un document XML de la mémoire en appelant la procédure stockée système **sp_xml_removedocument** .  
  
## <a name="see-also"></a> Voir aussi  
 [OPENXML &#40;Transact-SQL&#41;](../../t-sql/functions/openxml-transact-sql.md)   
 [OPENXML &#40;SQL Server&#41;](../../relational-databases/xml/openxml-sql-server.md)  
  
  
