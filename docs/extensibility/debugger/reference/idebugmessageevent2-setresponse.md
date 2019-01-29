---
title: "IDebugMessageEvent2::SetResponse | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IDebugMessageEvent2::SetResponse"
helpviewer_keywords: 
  - "IDebugMessageEvent2::SetResponse method"
  - "SetResponse method"
ms.assetid: 2a5e318d-3225-4abd-83f1-28323baff6c0
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IDebugMessageEvent2::SetResponse
Sets the response, if any, from the message box.  
  
## Syntax  
  
```cpp  
HRESULT SetResponse(   
   DWORD dwResponse  
);  
```  
  
```csharp  
int SetResponse(   
   uint dwResponse  
);  
```  
  
#### Parameters  
 `dwResponse`  
 [in] Specifies the response, using the conventions of the Win32 `MessageBox` function. See the [AfxMessageBox](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox) function for details.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## See Also  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [AfxMessageBox](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox)