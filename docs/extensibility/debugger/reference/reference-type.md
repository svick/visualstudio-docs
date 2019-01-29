---
title: "REFERENCE_TYPE | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "REFERENCE_TYPE"
helpviewer_keywords: 
  - "REFERENCE_TYPE enumeration"
ms.assetid: b1ffba10-eb9d-48ba-bf48-6d8b71d6f270
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# REFERENCE_TYPE
Specifies the reference type.  
  
## Syntax  
  
```cpp  
enum enum_REFERENCE_TYPE {   
   REF_TYPE_WEAK   = 0x0001,  
   REF_TYPE_STRONG = 0x0002  
};  
typedef DWORD REFERENCE_TYPE;  
```  
  
```csharp  
public enum enum_REFERENCE_TYPE {   
   REF_TYPE_WEAK   = 0x0001,  
   REF_TYPE_STRONG = 0x0002  
};  
```  
  
## Members  
 REF_TYPE_WEAK  
 Specifies a weak reference. Cannot be combined with `REF_TYPE_STRONG`.  
  
 REF_TYPE_STRONG  
 Specifies a strong reference. Cannot be combined with `REF_TYPE_WEAK`.  
  
## Remarks  
 Used as the `dwRefType` member of the [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) structure.  
  
 Passed as a parameter to the [SetReferenceType](../../../extensibility/debugger/reference/idebugreference2-setreferencetype.md) method.  
  
## Requirements  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## See Also  
 [Enumerations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [SetReferenceType](../../../extensibility/debugger/reference/idebugreference2-setreferencetype.md)