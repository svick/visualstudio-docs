---
title: "IEnumDebugPropertyInfo2::Reset | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IEnumDebugPropertyInfo2::Reset"
helpviewer_keywords: 
  - "IEnumDebugPropertyInfo2::Reset"
ms.assetid: fa4201c1-4633-4596-93aa-bd415c4ed71a
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IEnumDebugPropertyInfo2::Reset
Resets the enumeration to the first element.  
  
## Syntax  
  
```cpp  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## Remarks  
 After this method is called, the next call to the [Next](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-next.md) method returns the first element of the enumeration.  
  
## See Also  
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)