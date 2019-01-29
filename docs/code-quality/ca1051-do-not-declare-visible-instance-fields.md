---
title: "CA1051: Do not declare visible instance fields"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
  - "CA1051"
  - "DoNotDeclareVisibleInstanceFields"
helpviewer_keywords:
  - "CA1051"
  - "DoNotDeclareVisibleInstanceFields"
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
  - "multiple"
---
# CA1051: Do not declare visible instance fields

|||
|-|-|
|TypeName|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|Category|Microsoft.Design|
|Breaking Change|Breaking|

## Cause
 An externally visible type has an externally visible instance field.

## Rule description
 The primary use of a field should be as an implementation detail. Fields should be `private` or `internal` and should be exposed by using properties. It is as easy to access a property as it is to access a field, and the code in the accessors of a property can change as the features of the type expand without introducing breaking changes. Properties that just return the value of a private or internal field are optimized to perform on par with accessing a field; very little performance gain is associated with the use of externally visible fields over properties.

 Externally visible refers to `public`, `protected`, and `protected internal` (`Public`, `Protected`, and `Protected Friend` in Visual Basic) accessibility levels.

## How to fix violations
 To fix a violation of this rule, make the field `private` or `internal` and expose it by using an externally visible property.

## When to suppress warnings
 Do not suppress a warning from this rule. Externally visible fields do not provide any benefits that are unavailable to properties. Additionally, public fields cannot be protected by [Link Demands](/dotnet/framework/misc/link-demands). See [CA2112: Secured types should not expose fields](../code-quality/ca2112-secured-types-should-not-expose-fields.md).

## Example
 The following example shows a type (`BadPublicInstanceFields`) that violates this rule. `GoodPublicInstanceFields` shows the corrected code.

 [!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]

## Related rules
 [CA2112: Secured types should not expose fields](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## See also
 [Link Demands](/dotnet/framework/misc/link-demands)