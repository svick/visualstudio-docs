---
title: "CA1711: Identifiers should not have incorrect suffix"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
  - "CA1711"
  - "IdentifiersShouldNotHaveIncorrectSuffix"
helpviewer_keywords:
  - "CA1711"
  - "IdentifiersShouldNotHaveIncorrectSuffix"
ms.assetid: a63359ab-386d-44ae-b381-ee3a983aca29
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
  - "multiple"
---
# CA1711: Identifiers should not have incorrect suffix

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectSuffix|
|CheckId|CA1711|
|Category|Microsoft.Naming|
|Breaking Change|Breaking|

## Cause

An identifier has an incorrect suffix.

## Rule description

By convention, only the names of types that extend certain base types or that implement certain interfaces, or types derived from these types, should end with specific reserved suffixes. Other type names should not use these reserved suffixes.

The following table lists the reserved suffixes and the base types and interfaces with which they are associated.

|Suffix|Base type/Interface|
|------------|--------------------------|
|Attribute|<xref:System.Attribute?displayProperty=fullName>|
|Collection|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|
|Dictionary|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|
|EventHandler|An event-handler delegate|
|Exception|<xref:System.Exception?displayProperty=fullName>|
|Permission|<xref:System.Security.IPermission?displayProperty=fullName>|
|Queue|<xref:System.Collections.Queue?displayProperty=fullName>|
|Stack|<xref:System.Collections.Stack?displayProperty=fullName>|
|Stream|<xref:System.IO.Stream?displayProperty=fullName>|

In addition, the following suffixes should **not** be used:

- `Delegate`

- `Enum`

- `Impl` (use `Core` instead)

- `Ex` or similar suffix to distinguish it from an earlier version of the same type

Naming conventions provide a common look for libraries that target the common language runtime. This reduces the learning curve that is required for new software libraries, and increases customer confidence that the library was developed by someone who has expertise in developing managed code.

## How to fix violations

Remove the suffix from the type name.

## When to suppress warnings

Do not suppress a warning from this rule unless the suffix has an unambiguous meaning in the application domain.

## Related rules

- [CA1710: Identifiers should have correct suffix](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)

## See also

- [Attributes](/dotnet/standard/design-guidelines/attributes)
- [Handling and raising events](/dotnet/standard/events/index)