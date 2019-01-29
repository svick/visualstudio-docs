---
title: "IDebugStackFrame2::GetExpressionContext | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IDebugStackFrame2::GetExpressionContext"
helpviewer_keywords: 
  - "IDebugStackFrame2::GetExpressionContext"
ms.assetid: a2604e6a-502d-473b-868f-b11ac64c7a35
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IDebugStackFrame2::GetExpressionContext
Gets an evaluation context for expression evaluation within the current context of a stack frame and thread.  
  
## Syntax  
  
```cpp  
HRESULT GetExpressionContext (   
   IDebugExpressionContext2** ppExprCxt  
);  
```  
  
```csharp  
int GetExpressionContext (   
   out IDebugExpressionContext2 ppExprCxt  
);  
```  
  
#### Parameters  
 `ppExprCxt`  
 [out] Returns an [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) object that represents a context for expression evaluation.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## Remarks  
 Generally, an expression evaluation context can be thought of as a scope for performing expression evaluation. Call the [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) method to parse an expression and then call the resulting [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) or [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) methods to evaluate the parsed expression.  
  
## See Also  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)   
 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)