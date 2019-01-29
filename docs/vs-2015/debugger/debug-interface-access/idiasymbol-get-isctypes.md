---
title: "IDiaSymbol::get_isCTypes | Microsoft Docs"
ms.date: 11/15/2016
ms.prod: "visual-studio-dev14"
ms.technology: "vs-ide-debug"
ms.topic: reference
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaStackWalker2 interface"
ms.assetid: 00c73cf9-2933-472e-bc1d-d041f4d7e412
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
---
# IDiaSymbol::get_isCTypes
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Retrieves a flag indicating whether the symbol file contains C types.  
  
## Syntax  
  
```cpp#  
HRESULT get_isCTypes(  
   BOOL *pFlag  
);  
```  
  
#### Parameters  
 `pFlag`  
 [out] Returns `TRUE` if the symbol file contains C types; otherwise, returns `FALSE`.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns `S_FALSE` or an error code.  
  
> [!NOTE]
>  A return value of `S_FALSE` means that the property is not available for the symbol.  
  
## Remarks  
 This property is available from the `SymTagExe` symbol type (see [Exe](../../debugger/debug-interface-access/exe.md)).  
  
## Requirements  
  
|Requirement|Description|  
|-----------------|-----------------|  
|Header:|dia2.h|  
|Version:|DIA SDK v8.0|  
  
## See Also  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Exe](../../debugger/debug-interface-access/exe.md)