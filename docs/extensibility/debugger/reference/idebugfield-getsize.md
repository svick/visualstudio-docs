---
title: "IDebugField::GetSize | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IDebugField::GetSize"
helpviewer_keywords: 
  - "IDebugField::GetSize method"
ms.assetid: 73329924-3751-4f44-af54-5986b7943374
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IDebugField::GetSize
This method gets the size of a field, in bytes.  
  
## Syntax  
  
```cpp  
HRESULT GetSize(   
   DWORD* pdwSize  
);  
```  
  
```csharp  
int GetSize(  
   out uint pdwSize  
);  
```  
  
#### Parameters  
 `pdwSize`  
 [out] Returns the size.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## Remarks  
 All fields have a type and all types have a size. For example, a field with a type of byte has a size of 1 byte.  
  
## See Also  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)