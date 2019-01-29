---
title: "IDebugProgram2::GetEngineInfo | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IDebugProgram2::GetEngineInfo"
helpviewer_keywords: 
  - "IDebugProgram2::GetEngineInfo"
ms.assetid: 3a4f2dc0-e082-4d8d-aeaf-463ab09d279b
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IDebugProgram2::GetEngineInfo
Gets the name and GUID of the debug engine (DE) running this program.  
  
## Syntax  
  
```cpp  
HRESULT GetEngineInfo(   
   BSTR* pbstrEngine,  
   GUID* pguidEngine  
);  
```  
  
```csharp  
int GetEngineInfo(   
   out string pbstrEngine,  
   out GUID   pguidEngine  
);  
```  
  
#### Parameters  
 `pbstrEngine`  
 [out] Returns the name of the DE running this program.  
  
 `pguidEngine`  
 [out] Returns the GUID of the DE running this program.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## Remarks  
 Each DE defines its own GUID for identification.  
  
## See Also  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)