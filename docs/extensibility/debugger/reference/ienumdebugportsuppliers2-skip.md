---
title: "IEnumDebugPortSuppliers2::Skip | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IEnumDebugPortSuppliers2::Skip"
helpviewer_keywords: 
  - "IEnumDebugPortSuppliers2::Skip"
ms.assetid: bd95d7e9-274f-485d-8bf6-865306ae1b81
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IEnumDebugPortSuppliers2::Skip
Skips over the specified number of elements.  
  
## Syntax  
  
```cpp  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
);  
```  
  
#### Parameters  
 `celt`  
 [in] Number of elements to skip.  
  
## Return Value  
 If successful, returns `S_OK`. Returns `S_FALSE` if `celt` is greater than the number of remaining elements; otherwise, returns an error code.  
  
## Remarks  
 If `celt` specifies a value greater than the number of remaining elements, the enumeration is set to the end and `S_FALSE` is returned.  
  
## See Also  
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)