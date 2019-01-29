---
title: "Parameter Element | Microsoft Docs"
ms.date: 11/15/2016
ms.prod: "visual-studio-dev14"
ms.technology: msbuild
ms.topic: conceptual
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Parameter element [MSBuild]"
  - "<Parameter> element [MSBuild]"
ms.assetid: b273afff-b500-4e97-8cfd-31f39fa64a51
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: jillfra
---
# Parameter Element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Contains information about a specific parameter for a task that is generated by a `UsingTask``TaskFactory`.  The name of the element is the name of the parameter.  For more informations, see [UsingTask Element (MSBuild)](../msbuild/usingtask-element-msbuild.md).  
  
 \<Project>  
 \<UsingTask>  
 \<ParameterGroup>  
 \<Parameter>  
  
## Syntax  
  
```  
<ParameterGroup ParameterType="SystemType"  
    Output="true/false"  
    Required="true/false" />  
```  
  
## Attributes and Elements  
 The following sections describe attributes, child elements, and parent elements.  
  
### Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|`ParameterType`|Optional attribute.<br /><br /> The .NET type of the parameter, for example, "System.String".|  
|`Output`|Optional Boolean attribute.<br /><br /> If `true`, this parameter is an output parameter for the task. By default, the value is `false`.|  
|`Required`|Optional Boolean attribute.<br /><br /> If `true`, this parameter is an required parameter for the task. By default, the value is `false`.|  
  
### Child Elements  
 None.  
  
### Parent Elements  
  
|Element|Description|  
|-------------|-----------------|  
|[ParameterGroup](../msbuild/parametergroup-element.md)|Contains an optional list of parameters that will be present on the task that is generated by a `UsingTask``TaskFactory`.|  
  
## Example  
 The following example shows how to use the `Parameter` element.  
  
```  
<UsingTask TaskName="MyTask" AssemblyName="My.Assembly" TaskFactory="MyTaskFactory">  
       <ParameterGroup>  
              <Parameter1 ParameterType="System.String" Required="False" Output="False"/>  
              <Parameter2 ParameterType="System.Int" Required="True" Output="False"/>  
             ...  
</ParameterGroup>  
       <TaskBody Evaluate="true">  
      ... Task factory-specific data ...  
       </TaskBody>  
</UsingTask>  
```  
  
## See Also  
 [Tasks](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md)