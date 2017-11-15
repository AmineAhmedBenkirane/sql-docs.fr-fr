---
title: MSSQLSERVER_137 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords: 137 (Database Engine error)
ms.assetid: 47fb4212-2165-4fec-bc41-6d548465d7be
caps.latest.revision: "12"
author: edmacauley
ms.author: edmaca
manager: cguyer
ms.workload: Inactive
ms.openlocfilehash: 3f0f551bb3239408a9a985b2758cbb7e68f770ae
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="mssqlserver137"></a>MSSQLSERVER_137
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|137|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|P_SCALAR_VAR_NOTFOUND|  
|Texte du message|La variable scalaire « %.*ls » doit être déclarée.|  
  
## <a name="explanation"></a>Explication  
Cette erreur se produit lorsqu'une variable utilisée dans un script SQL n'a pas été préalablement déclarée. L’exemple suivant retourne l’erreur 137 pour les instructions SET et SELECT parce que **@mycol** n’a pas été déclarée.  
  
SET @mycol = 'ContactName';  
  
SELECT @mycol;  
  
L'une des causes les plus compliquées de cette erreur est l'utilisation d'une variable qui a été déclarée en dehors de l'instruction EXECUTE. Par exemple, la variable **@mycol** spécifiée dans l’instruction SELECT est locale par rapport à cette instruction SELECT ; elle se situe donc en dehors de l’instruction EXECUTE.  
  
USE AdventureWorks2012 ;  
  
GO  
  
DECLARE @mycol nvarchar(20);  
  
SET @mycol = 'Name';  
  
EXECUTE ('SELECT @mycol FROM Production.Product;');  
  
## <a name="user-action"></a>Action de l'utilisateur  
Vérifiez que toutes variables utilisées dans un script SQL ont été déclarées avant d'être utilisées par ailleurs dans le script.  
  
Réécrivez le script afin qu'il ne fasse pas référence aux variables de l'instruction EXECUTE déclarées en dehors. Par exemple :  
  
USE AdventureWorks2012 ;  
  
GO  
  
DECLARE @mycol nvarchar(20) ;  
  
SET @mycol = 'Name';  
  
EXECUTE ('SELECT ' + @mycol + ' FROM Production.Product';) ;  
  
## <a name="see-also"></a>Voir aussi  
[EXECUTE &#40;Transact-SQL&#41;](~/t-sql/language-elements/execute-transact-sql.md)  
[Instructions SET &#40;Transact-SQL&#41;](~/t-sql/statements/set-statements-transact-sql.md)  
[DECLARE @local_variable &#40;Transact-SQL&#41;](~/t-sql/language-elements/declare-local-variable-transact-sql.md)  
  
