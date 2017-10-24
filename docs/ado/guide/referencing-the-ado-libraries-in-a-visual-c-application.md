---
title: "Référencer les bibliothèques ADO dans une Application Visual C++ | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.prod: sql-non-specified
ms.technology: "“drivers”"
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- libraries [ADO]
- referencing libraries in a Visual C++ application[ADO]
- ADO, libraries
ms.assetid: d3ea12ec-bca8-48c3-af57-ce14576108c9
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 44d731d8c9e61c29f1dc9eb0c8ea12d57402639c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="referencing-the-ado-libraries-in-a-visual-c-application"></a>Référencer les bibliothèques ADO dans une Application Visual C++
Pour utiliser la dernière version de l’objet ADO dans une application Visual C++, utilisez ce qui suit `#import` directive :  
  
```  
#import "msado15.dll" \  
    no_namespace rename("EOF", "EndOfFile")  
```  
  
 Pour utiliser ADO MD ou ADOX, vous devez importer *msadomd.dll* ou *msadox.dll*, en utilisant la syntaxe ci-dessus.  
  
## <a name="backward-compatibility"></a>Compatibilité descendante  
 Pour utiliser une version antérieure de l’objet ADO, remplacez *msado15.dll* ci-dessus avec l’une des bibliothèques de types suivantes.  
  
-   *msado27.tlb*, bibliothèque de types 2.7 ADO  
  
-   *msado26.tlb*, bibliothèque de types 2.6 ADO  
  
-   *Msado25.tlb*, bibliothèque de types 2,5 ADO  
  
-   *Msado21.tlb*, bibliothèque de types 2.1 ADO  
  
-   *msado20.tlb*, bibliothèque de types 2.0 ADO

