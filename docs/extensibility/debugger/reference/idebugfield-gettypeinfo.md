---
title: "IDebugField::GetTypeInfo | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IDebugField::GetTypeInfo"
helpviewer_keywords: 
  - "IDebugField::GetTypeInfo method"
ms.assetid: bb5acfa3-04c3-4088-be84-9ff8926cd16f
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IDebugField::GetTypeInfo
This method gets type-independent information about the symbol or type.  
  
## Syntax  
  
```cpp  
HRESULT GetTypeInfo(   
   TYPE_INFO* pTypeInfo  
);  
```  
  
```csharp  
int GetTypeInfo(  
   TYPE_INFO[] pTypeInfo  
);  
```  
  
#### Parameters  
 `pTypeInfo`  
 [out] Returns type information in the supplied [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) structure.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## Remarks  
 Type-independent information would include, for example, the AppDomain, the module, and the class that contains the symbol.  
  
## See Also  
 [GetType](../../../extensibility/debugger/reference/idebugfield-gettype.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)