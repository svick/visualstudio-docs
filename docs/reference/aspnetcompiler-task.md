---
title: "AspNetCompiler Task"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#AspNetCompiler"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild, AspNetCompiler task"
  - "AspNetCompiler task [MSBuild]"
ms.assetid: f811c019-a67b-4d54-82e6-e29549496f6e
caps.latest.revision: 11
ms.author: "kempb"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# AspNetCompiler Task
The `AspNetCompiler` task wraps aspnet_compiler.exe, a utility to precompile [!INCLUDE[vstecasp](../codequality/includes/vstecasp_md.md)] applications.  
  
## Task Parameters  
 The following table describes the parameters of the `AspNetCompiler` task.  
  
|Parameter|Description|  
|---------------|-----------------|  
|`AllowPartiallyTrustedCallers`|Optional `Boolean` parameter.<br /><br /> If this parameter is `true`,, the strong-name assembly will allow partially trusted callers.|  
|`Clean`|Optional `Boolean` parameter<br /><br /> If this parameter is `true`, the precompiled application will be built clean. Any previously compiled components will be recompiled. The default value is `false`. This parameter corresponds to the **-c** switch on aspnet_compiler.exe.|  
|`Debug`|Optional `Boolean` parameter.<br /><br /> If this parameter is `true`, debug information (.PDB file) is emitted during compilation. The default value is `false`. This parameter corresponds to the **-d** switch on aspnet_compiler.exe.|  
|`DelaySign`|Optional `Boolean` parameter.<br /><br /> If this parameter is `true`, the assembly is not fully signed when created.|  
|`FixedNames`|Optional `Boolean` parameter.<br /><br /> If this parameter is `true`, the compiled assemblies will be given fixed names..|  
|`Force`|Optional `Boolean` parameter<br /><br /> If this parameter is `true`, the task will overwrite the target directory if it already exists. Existing contents are lost. The default value is `false`. This parameter corresponds to the **-f** switch on aspnet_compiler.exe.|  
|`KeyContainer`|Optional `String` parameter.<br /><br /> Specifies a strong name key container.|  
|`KeyFile`|Optional `String` parameter.<br /><br /> Specifies the physical path to the strong name key file..|  
|`MetabasePath`|Optional `String` parameter.<br /><br /> Specifies the full IIS metabase path of the application. This parameter cannot be combined with the `VirtualPath` or `PhysicalPath` parameters. This parameter corresponds to the **-m** switch on aspnet_compiler.exe.|  
|`PhysicalPath`|Optional `String` parameter.<br /><br /> Specifies the physical path of the application to be compiled. If this parameter is missing, the IIS metabase is used to locate the application. This parameter corresponds to the **-p** switch on aspnet_compiler.exe.|  
|`TargetFrameworkMoniker`|Optional `String` parameter.<br /><br /> Specifies the TargetFrameworkMoniker indicating which .NET Framework version of aspnet_compiler.exe should be used. Only accepts .NET Framework monikers.|  
|`TargetPath`|Optional `String` parameter.<br /><br /> Specifies the physical path to which the application is compiled. If not specified, the application is precompiled in-place.|  
|`Updateable`|Optional `Boolean` parameter.<br /><br /> If this parameter is `true`, the precompiled application will be updateable.  The default value is `false`. This parameter corresponds to the **-u** switch on aspnet_compiler.exe.|  
|`VirtualPath`|Optional `String` parameter.<br /><br /> The virtual path of the application to be compiled. If `PhysicalPath` specified, the physical path is used to locate the application. Otherwise, the IIS metabase is used, and the application is assumed to be in the default site. This parameter corresponds to the **-v** switch on aspnet_compiler.exe.|  
  
## Remarks  
 In addition to the parameters listed above, this task inherits parameters from the \<xref:Microsoft.Build.Tasks.ToolTaskExtension> class, which itself inherits from the \<xref:Microsoft.Build.Utilities.ToolTask> class. For a list of these additional parameters and their descriptions, see [ToolTaskExtension Base Class](../reference/tooltaskextension-base-class.md).  
  
## Example  
 The following code example uses the `AspNetCompiler` task to precompile an [!INCLUDE[vstecasp](../codequality/includes/vstecasp_md.md)] application.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="PrecompileWeb">  
        <AspNetCompiler  
            VirtualPath="/MyWebSite"  
            PhysicalPath="c:\inetpub\wwwroot\MyWebSite\"  
            TargetPath="c:\precompiledweb\MyWebSite\"  
            Force="true"  
            Debug="true"  
        />  
    </Target>  
</Project>  
```  
  
## See Also  
 [Tasks](../reference/msbuild-tasks.md)   
 [Task Reference](../reference/msbuild-task-reference.md)