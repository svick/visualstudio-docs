---
title: "CA1044: Properties should not be write only"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
  - "PropertiesShouldNotBeWriteOnly"
  - "CA1044"
helpviewer_keywords:
  - "CA1044"
  - "PropertiesShouldNotBeWriteOnly"
ms.assetid: 8386bf3a-b161-4841-bf8b-92591595aea9
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
 - CSharp
 - VB
ms.workload:
  - "multiple"
---
# CA1044: Properties should not be write only

|||
|-|-|
|TypeName|PropertiesShouldNotBeWriteOnly|
|CheckId|CA1044|
|Category|Microsoft.Design|
|Breaking Change|Breaking|

## Cause
 The public or protected property has a set accessor but does not have a get accessor.

## Rule description
 Get accessors provide read access to a property and set accessors provide write access. Although it is acceptable and often necessary to have a read-only property, the design guidelines prohibit the use of write-only properties. This is because letting a user set a value and then preventing the user from viewing the value does not provide any security. Also, without read access, the state of shared objects cannot be viewed, which limits their usefulness.

## How to fix violations
 To fix a violation of this rule, add a get accessor to the property. Alternatively, if the behavior of a write-only property is necessary, consider converting this property to a method.

## When to suppress warnings
 It is recommended that you do not suppress a warning from this rule.

## Example
 In the following example, `BadClassWithWriteOnlyProperty` is a type with a write-only property. `GoodClassWithReadWriteProperty` contains the corrected code.

 [!code-vb[FxCop.Design.PropertiesNotWriteOnly#1](../code-quality/codesnippet/VisualBasic/ca1044-properties-should-not-be-write-only_1.vb)]
 [!code-csharp[FxCop.Design.PropertiesNotWriteOnly#1](../code-quality/codesnippet/CSharp/ca1044-properties-should-not-be-write-only_1.cs)]