---
title: "IDebugField::GetKind | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IDebugField::GetKind"
helpviewer_keywords: 
  - "IDebugField::GetKind method"
ms.assetid: e7c9c60a-8e55-4ecc-aa63-0c814a1e92cc
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IDebugField::GetKind
This method gets the kind of field.  
  
## Syntax  
  
```cpp  
HRESULT GetKind(   
   FIELD_KIND* pdwKind  
);  
```  
  
```csharp  
int GetKind(  
   out enum_FIELD_KIND pdwKind  
);  
```  
  
#### Parameters  
 `pdwKind`  
 [out] Returns the kind of field as a combination of [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) constants.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## See Also  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)