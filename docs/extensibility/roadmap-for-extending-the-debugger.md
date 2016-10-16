---
title: "Roadmap for Extending the Debugger"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "debugging [Debugging SDK], roadmap"
  - "Debugging SDK, roadmap"
ms.assetid: 1f4096a8-f7aa-4dfa-84e1-6d59263e70bb
caps.latest.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
translation.priority.mt: 
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
# Roadmap for Extending the Debugger
This documentation provides guide and reference information for extending the [!INCLUDE[vs_current_short](../codequality/includes/vs_current_short_md.md)] debugger with the [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)].  
  
 [!INCLUDE[vsprvs](../codequality/includes/vsprvs_md.md)] debugging documentation includes samples, a comprehensive reference, and several representative scenarios that demonstrate typical ways to customize the debugger.  
  
 Your compiler and its output determine what you need to do to implement debugging in your product. If your compiler:  
  
-   Targets the Windows native operating system and writes a .PDB file, you can debug programs with the native code debug engine (DE), which is integrated into [!INCLUDE[vsprvs](../codequality/includes/vsprvs_md.md)]. You do not need to implement a DE or expression evaluator. The expression evaluator is written for the syntax of the C++ programming language.  
  
-   Produces Microsoft intermediate language (MSIL) output, you can debug programs with the managed code debug engine DE, which is also integrated into [!INCLUDE[vsprvs](../codequality/includes/vsprvs_md.md)]. Thus, you need only implement an expression evaluator. A sample expression evaluator is provided for you. For more information, see the following topics:  
  
     [Expression Evaluation](../extensibility/expression-evaluation--visual-studio-debugging-sdk-.md)  
  
     [Evaluating Expressions](../extensibility/evaluating-expressions.md)  
  
     [Expression Evaluation Context](../extensibility/expression-evaluation-context.md)  
  
     [Expression Evaluation in Break Mode](../extensibility/expression-evaluation-in-break-mode.md)  
  
     [Writing a Common Language Runtime Expression Evaluator](../extensibility/writing-a-common-language-runtime-expression-evaluator.md)  
  
-   Targets a proprietary operating system or some other run-time environment, you need to write your own DE. A tutorial that creates a simple DE using ATL COM is provided. For more information, see the following topics:  
  
     [Creating a Custom Debug Engine](../extensibility/creating-a-custom-debug-engine.md)  
  
     [Tutorial: Building a Debug Engine Using ATL COM](assetId:///9097b71e-1fe7-48f7-bc00-009e25940c24)  
  
     [Implementing a Port Supplier](../extensibility/implementing-a-port-supplier.md)  
  
     [Samples](../extensibility/visual-studio-debugging-samples.md)  
  
## See Also  
 [Getting Started](../extensibility/getting-started-with-debugger-extensibility.md)