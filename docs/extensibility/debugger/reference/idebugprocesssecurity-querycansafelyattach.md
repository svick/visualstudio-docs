---
title: "IDebugProcessSecurity::QueryCanSafelyAttach | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
helpviewer_keywords: 
  - "IDebugProcessSecurity::QueryCanSafelyAttach"
ms.assetid: 63ec1ae8-27da-4574-aa15-1c986fe9fe58
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IDebugProcessSecurity::QueryCanSafelyAttach
This method allows the port supplier to display a warning before the user attaches to an unsafe process.  
  
## Syntax  
  
```cpp  
HRESULT QueryCanSafelyAttach();  
```  
  
```csharp  
int QueryCanSafelyAttach();  
```  
  
## Return Value  
 The return values are as follows:  
  
-   `S_OK`: Attaching to process is safe and no warning dialog box is shown.  
  
-   `S_FALSE`: Attaching could be a security problem and a dialog box with a warning is shown.  
  
-   `FAILURE`: Attaching to process fails.  
  
## See Also  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)