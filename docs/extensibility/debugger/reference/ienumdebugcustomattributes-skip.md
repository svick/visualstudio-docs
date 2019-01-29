---
title: "IEnumDebugCustomAttributes::Skip | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IEnumCustomAttributes::Skip"
helpviewer_keywords: 
  - "IEnumDebugCustomAttributes::Skip"
ms.assetid: 54c72e23-cd4c-4746-935c-abea8057dd1b
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IEnumDebugCustomAttributes::Skip
Skips a specified number of custom attributes in an enumeration sequence.  
  
## Syntax  
  
```cpp  
HRESULT Skip (   
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
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)