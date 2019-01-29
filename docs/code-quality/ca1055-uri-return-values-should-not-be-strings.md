---
title: "CA1055: URI return values should not be strings"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
  - "CA1055"
  - "UriReturnValuesShouldNotBeStrings"
helpviewer_keywords:
  - "UriReturnValuesShouldNotBeStrings"
  - "CA1055"
ms.assetid: 40e39873-7872-4988-8195-9eb0ade9ece0
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
 - CPP
 - CSharp
 - VB
ms.workload:
  - "multiple"
---
# CA1055: URI return values should not be strings

|||
|-|-|
|TypeName|UriReturnValuesShouldNotBeStrings|
|CheckId|CA1055|
|Category|Microsoft.Design|
|Breaking Change|Breaking|

## Cause
 The name of a method contains "uri", "Uri", "urn", "Urn", "url", or "Url", and the method returns a string.

## Rule description
 This rule splits the method name into tokens based on the Pascal casing convention and checks whether each token equals "uri", "Uri", "urn", "Urn", "url", or "Url". If there is a match, the rule assumes that the method returns a uniform resource identifier (URI). A string representation of a URI is prone to parsing and encoding errors, and can lead to security vulnerabilities. The <xref:System.Uri?displayProperty=fullName> class provides these services in a safe and secure manner.

## How to fix violations
 To fix a violation of this rule, change the return type to a <xref:System.Uri>.

## When to suppress warnings
 It is safe to suppress a warning from this rule if the return value does not represent a URI.

## Example
 The following example shows a type, `ErrorProne`, that violates this rule, and a type, `SaferWay`, that satisfies the rule.

 [!code-csharp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1055-uri-return-values-should-not-be-strings_1.cs)]
 [!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1055-uri-return-values-should-not-be-strings_1.vb)]
 [!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1055-uri-return-values-should-not-be-strings_1.cpp)]

## Related rules
 [CA1056: URI properties should not be strings](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1054: URI parameters should not be strings](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA2234: Pass System.Uri objects instead of strings](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

 [CA1057: String URI overloads call System.Uri overloads](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)