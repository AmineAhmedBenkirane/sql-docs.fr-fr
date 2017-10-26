---
title: PDOStatement::execute | Documents Microsoft
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2e80566-fa41-4918-8521-cf2e05374cbd
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: b98b91afada5f484843188729996e0b55472f765
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="pdostatementexecute"></a>PDOStatement::execute
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Exécute une instruction.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
bool PDOStatement::execute ([ $input ] );  
```  
  
#### <a name="parameters"></a>Paramètres  
*$input*: (facultatif) tableau associatif qui contient les valeurs des marqueurs de paramètre.  
  
## <a name="return-value"></a>Valeur retournée  
true en cas de réussite, false dans le cas contraire.  
  
## <a name="remarks"></a>Notes  
Les instructions exécutées avec PDOStatement::execute doivent d’abord être préparées avec [PDO::prepare](../../connect/php/pdo-prepare.md). Pour plus d’informations sur la spécification d’une exécution d’instruction directe ou préparée, consultez [Exécution d’instruction directe et exécution d’instruction préparée dans le pilote PDO_SQLSRV](../../connect/php/direct-statement-execution-prepared-statement-execution-pdo-sqlsrv-driver.md) .  
  
Toutes les valeurs du tableau de paramètres d’entrée sont traitées comme des valeurs PDO::PARAM_STR.  
  
Si l’instruction préparée inclut des marqueurs de paramètre, vous devez soit appeler PDOStatement::bindParam pour lier les variables PHP aux marqueurs de paramètre, soit passer un tableau de valeurs de paramètre d’entrée uniquement.  
  
La prise en charge de PDO a été ajoutée dans la version 2.0 de [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)].  
  
## <a name="example"></a>Exemple  
  
```  
<?php  
$database = "AdventureWorks";  
$server = "(local)";  
$conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "");  
  
$query = "select * from Person.ContactType";  
$stmt = $conn->prepare( $query );  
$stmt->execute();  
  
while ( $row = $stmt->fetch( PDO::FETCH_ASSOC ) ){  
   print "$row[Name]\n";  
}  
  
echo "\n";  
$param = "Owner";  
$query = "select * from Person.ContactType where name = ?";  
$stmt = $conn->prepare( $query );  
$stmt->execute(array($param));  
  
while ( $row = $stmt->fetch( PDO::FETCH_ASSOC ) ){  
   print "$row[Name]\n";  
}  
?>  
```  
  
## <a name="see-also"></a>Voir aussi  
[Classe PDOStatement](../../connect/php/pdostatement-class.md)  
[PDO](http://go.microsoft.com/fwlink/?LinkID=187441)  
  

