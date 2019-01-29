---
title: "IDebugManagedObject::GetManagedObject | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IDebugManagedObject::GetManagedObject"
helpviewer_keywords: 
  - "IDebugManagedObject::GetManagedObject method"
ms.assetid: 6abe1402-6aad-41e6-8ec1-ae12d5945992
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IDebugManagedObject::GetManagedObject
Returns an interface that represents the managed object.  
  
## Syntax  
  
```cpp  
HRESULT GetManagedObject(   
   IUnknown** ppManagedObject  
);  
```  
  
```cpp  
int GetManagedObject(  
   out object ppManagedObject  
);  
```  
  
#### Parameters  
 `ppManagedObject`  
 [out] Returns an interface that represents the managed object.  
  
## Return Value  
 If successful, returns S_OK; otherwise, returns an error code.  
  
## Remarks  
 The interface returned from this method can be queried for any interface implemented by the managed class, allowing its methods to be called.  
  
## See Also  
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)