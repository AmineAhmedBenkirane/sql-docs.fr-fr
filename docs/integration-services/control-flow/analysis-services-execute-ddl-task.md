---
title: "T&#226;che DDL d&#39;ex&#233;cution de SQL Server Analysis Services | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.designer.asexecuteddltask.f1"
helpviewer_keywords: 
  - "tâche DDL d'exécution SQL Server Analysis Services"
  - "DDL"
ms.assetid: 7f25c8c6-b601-41f2-9553-be0a2ee0751a
caps.latest.revision: 48
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 48
---
# T&#226;che DDL d&#39;ex&#233;cution de SQL Server Analysis Services
  La tâche DDL d'exécution de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] exécute des instructions DDL (Data Definition Language) qui peuvent créer, supprimer ou modifier des modèles d'exploration de données et des objets multidimensionnels tels que des cubes et des dimensions. Par exemple, une instruction DDL peut créer une partition dans le cube **Adventure Works** ou supprimer une dimension dans [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], l’exemple de base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] inclus dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 La tâche DDL d'exécution de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilise un gestionnaire de connexions [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour se connecter à une instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou à un projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Pour plus d'informations, consultez [Analysis Services Connection Manager](../../integration-services/connection-manager/analysis-services-connection-manager.md).  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] comprend une série de tâches qui effectuent des opérations de Business Intelligence, telles que le traitement des objets analytiques et l’exécution des requêtes de prédiction d’exploration de données.  
  
 Pour plus d'informations sur les tâches Business Intelligence associées, cliquez sur l'une des rubriques suivantes :  
  
-   [Tâche de traitement d'Analysis Services](../../integration-services/control-flow/analysis-services-processing-task.md)  
  
-   [Tâche de requête d'exploration de données](../../integration-services/control-flow/data-mining-query-task.md)  
  
## Instructions DDL  
 Les instructions DDL sont représentées en tant qu'instructions en langage ASSL ([!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language) et insérées dans une commande XMLA (XML for Analysis).  
  
-   Le langage ASSL permet de définir et de décrire une instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], ainsi que les bases de données et les objets de base de données qu’elle contient. Pour plus d’informations, consultez [Référence Analysis Services Scripting Language &#40;ASSL&#41;](../../analysis-services/scripting/analysis-services-scripting-language-assl-for-xmla.md).  
  
-   XMLA est un langage de commande qui permet d'envoyer des commandes d'action, telles que Create, Alter ou Process, à une instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Pour plus d’informations, consultez [Référence XML for Analysis &#40;XMLA&#41;](../../analysis-services/xmla/xml-for-analysis-xmla-reference.md).  
  
 Si le code DDL est stocké dans un fichier distinct, la tâche DDL d’exécution de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilise un gestionnaire de connexions de fichiers pour spécifier le chemin du fichier. Pour plus d’informations, consultez [File Connection Manager](../../integration-services/connection-manager/file-connection-manager.md).  
  
 Étant donné que les instructions DDL peuvent contenir des mots de passe et d’autres informations sensibles, un package qui comporte une ou plusieurs tâches DDL d’exécution [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] doit utiliser le niveau de protection de package **EncryptAllWithUserKey** ou **EncryptAllWithPassword**. Pour plus d’informations, consultez [Integration Services &#40;SSIS&#41;, packages](../../integration-services/integration-services-ssis-packages.md).  
  
### Exemples d'instructions DDL  
 Les trois instructions DDL suivantes ont été générées en créant des scripts d’objets dans [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] incluse dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 L’instruction DDL suivante supprime la dimension **Promotion**.  
  
```  
<Delete xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DimensionID>Dim Promotion</DimensionID>  
    </Object>  
</Delete>  
  
```  
  
 L'instruction DDL suivante traite le cube [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)].  
  
```  
<Batch xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">  
  <Parallel>  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
      <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      </Object>  
      <Type>ProcessFull</Type>  
      <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
    </Process>  
  </Parallel>  
</Batch>  
  
```  
  
 L’instruction DDL suivante crée le modèle d’exploration de données **Forecasting**.  
  
```  
<Create xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <MiningStructureID>Forecasting</MiningStructureID>  
    </ParentObject>  
    <ObjectDefinition>  
        <MiningModel xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
            <ID>Forecasting</ID>  
            <Name>Forecasting</Name>  
            <Algorithm>Microsoft_Time_Series</Algorithm>  
            <AlgorithmParameters>  
                <AlgorithmParameter>  
                    <Name>PERIODICITY_HINT</Name>  
                    <Value xsi:type="xsd:string">{12}</Value>  
                </AlgorithmParameter>  
            </AlgorithmParameters>  
            <Columns>  
                <Column>  
                    <ID>Amount</ID>  
                    <Name>Amount</Name>  
                    <SourceColumnID>Amount</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Model Region</ID>  
                    <Name>Model Region</Name>  
                    <SourceColumnID>Model Region</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
                <Column>  
                    <ID>Quantity</ID>  
                    <Name>Quantity</Name>  
                    <SourceColumnID>Quantity</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Time Index</ID>  
                    <Name>Time Index</Name>  
                    <SourceColumnID>Time Index</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
            </Columns>  
            <Collation>Latin1_General_CS_AS_KS</Collation>  
        </MiningModel>  
    </ObjectDefinition>  
</Create>  
  
```  
  
 Les trois instructions DDL suivantes ont été générées en créant des scripts d’objets dans [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] incluse dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 L’instruction DDL suivante supprime la dimension **Promotion**.  
  
```  
<Delete xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DimensionID>Dim Promotion</DimensionID>  
    </Object>  
</Delete>  
  
```  
  
 L'instruction DDL suivante traite le cube [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)].  
  
```  
<Batch xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">  
  <Parallel>  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
      <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      </Object>  
      <Type>ProcessFull</Type>  
      <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
    </Process>  
  </Parallel>  
</Batch>  
  
```  
  
 L’instruction DDL suivante crée le modèle d’exploration de données **Forecasting**.  
  
```  
<Create xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <MiningStructureID>Forecasting</MiningStructureID>  
    </ParentObject>  
    <ObjectDefinition>  
        <MiningModel xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
            <ID>Forecasting</ID>  
            <Name>Forecasting</Name>  
            <Algorithm>Microsoft_Time_Series</Algorithm>  
            <AlgorithmParameters>  
                <AlgorithmParameter>  
                    <Name>PERIODICITY_HINT</Name>  
                    <Value xsi:type="xsd:string">{12}</Value>  
                </AlgorithmParameter>  
            </AlgorithmParameters>  
            <Columns>  
                <Column>  
                    <ID>Amount</ID>  
                    <Name>Amount</Name>  
                    <SourceColumnID>Amount</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Model Region</ID>  
                    <Name>Model Region</Name>  
                    <SourceColumnID>Model Region</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
                <Column>  
                    <ID>Quantity</ID>  
                    <Name>Quantity</Name>  
                    <SourceColumnID>Quantity</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Time Index</ID>  
                    <Name>Time Index</Name>  
                    <SourceColumnID>Time Index</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
            </Columns>  
            <Collation>Latin1_General_CS_AS_KS</Collation>  
        </MiningModel>  
    </ObjectDefinition>  
</Create>  
  
```  
  
## Configuration de la tâche DDL d'exécution d'Analysis Services  
 Vous pouvez définir des propriétés au moyen du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.  
  
 Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur l'une des rubriques suivantes :  
  
-   [Éditeur de tâche DDL d’exécution Analysis Services &#40;page Général&#41;](../../integration-services/control-flow/analysis-services-execute-ddl-task-editor-general-page.md)  
  
-   [Éditeur de tâche DDL d’exécution Analysis Services &#40;page DDL&#41;](../../integration-services/control-flow/analysis-services-execute-ddl-task-editor-ddl-page.md)  
  
-   [Page Expressions](../../integration-services/expressions/expressions-page.md)  
  
 Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :  
  
-   [Définir les propriétés d'une tâche ou d'un conteneur](../Topic/Set%20the%20Properties%20of%20a%20Task%20or%20Container.md)  
  
## Configuration par programmation de la tâche DDL d'exécution d'Analysis Services  
 Pour plus d'informations sur la définition par programmation de ces propriétés, cliquez sur la rubrique suivante :  
  
-   <xref:Microsoft.DataTransformationServices.Tasks.DTSProcessingTask.ASExecuteDDLTask>  
  
  