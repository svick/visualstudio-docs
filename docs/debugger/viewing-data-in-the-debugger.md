---
title: "Create custom views of data in the debugger | Microsoft Docs"
ms.date: "01/09/2019"
ms.topic: "conceptual"
f1_keywords: 
  - "vs.debug"
dev_langs: 
  - "CSharp"
  - "VB"
  - "FSharp"
  - "C++"
  - "JScript"
helpviewer_keywords: 
  - "debugging [Visual Studio], inspecting programs"
  - "debugger, viewing data"
ms.assetid: 13e1105f-f987-402e-9108-ec6ac12be042
author: "mikejo5000"
ms.author: "mikejo"
manager: jillfra
ms.workload: 
  - "multiple"
---
# Create custom views of data in the Visual Studio debugger (C#, Visual Basic, C++)

The [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] debugger provides many tools for inspecting and modifying the state of your program. Most of these tools function only in break mode.

## Create custom views of data in variable windows and DataTips

 Many of the [debugger windows](../debugger/debugger-windows.md), such as the **Autos** and **Watch** windows, allow you to inspect variables. You can customize how native types, managed objects, and your own types are shown in the debugger variable windows and in [DataTips](../debugger/view-data-values-in-data-tips-in-the-code-editor.md). For more information, see [Create custom views of native objects](../debugger/create-custom-views-of-native-objects.md) and [Create custom views of objects](../debugger/create-custom-views-of-dot-managed-objects.md).
  
## Create custom visualizers

 Visualizers enable you to view the contents of an object or variable in a meaningful way. In the Visual Studio debugger, a visualizer refers to the different windows that you can open using the magnifying glass ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Visualizer icon") icon. For example, the HTML visualizer shows how an HTML string would be interpreted and displayed in a browser. You can access visualizers from DataTips, the **Watch** window, the **Autos** window, and the **Locals** window. The **QuickWatch** dialog box also provides a visualizer. For more information, see [Create custom visualizers](../debugger/create-custom-visualizers-of-data.md).
  
## See also

 [First look at the debugger](../debugger/debugger-feature-tour.md) 
 [Command window](../ide/reference/command-window.md)   
 [Debugger security](../debugger/debugger-security.md)