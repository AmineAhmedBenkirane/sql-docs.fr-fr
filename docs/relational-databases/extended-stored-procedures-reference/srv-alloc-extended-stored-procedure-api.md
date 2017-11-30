---
title: "srv_alloc (API de procédure stockée étendue) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: extended-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: reference
apiname: srv_alloc
apilocation: opends60.dll
apitype: DLLExport
dev_langs: C++
helpviewer_keywords: srv_alloc
ms.assetid: 91505c59-a273-452f-b71d-5e8205c21863
caps.latest.revision: "32"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: a51631ea770f50051fba94ace61ea406d2a31c29
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="srvalloc-extended-stored-procedure-api"></a>srv_alloc (API de procédure stockée étendue)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Utilisez l’intégration CLR à la place.  
  
 Alloue la mémoire dynamiquement.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
void * srv_alloc ( DBINT  
size  
);  
```  
  
## <a name="arguments"></a>Arguments  
 *size*  
 Spécifie le nombre d'octets à allouer.  
  
## <a name="returns"></a>Valeur renvoyée  
 Un pointeur vers l'espace qui vient d'être alloué. Si *size* octets ne peuvent pas être alloués, un pointeur Null est retourné.  
  
## <a name="remarks"></a>Notes  
 La fonction **srv_alloc** est équivalente à la fonction API [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows **GlobalAlloc**. Les fonctions ordinaires de gestion de la mémoire du runtime C de l'API Windows peuvent être utilisées dans une application API de procédure stockée étendue.  
  
> [!IMPORTANT]  
>  Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production. Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
  
