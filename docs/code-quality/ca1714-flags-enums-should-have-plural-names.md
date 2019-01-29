---
title: "CA1714: Flags enums should have plural names"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
  - "FlagsEnumsShouldHavePluralNames"
  - "CA1714"
helpviewer_keywords:
  - "CA1714"
  - "FlagsEnumsShouldHavePluralNames"
ms.assetid: 95ef5b43-7681-49e9-a5a3-ac0357cf1be7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
  - "multiple"
---
# CA1714: Flags enums should have plural names

|||
|-|-|
|TypeName|FlagsEnumsShouldHavePluralNames|
|CheckId|CA1714|
|Category|Microsoft.Naming|
|Breaking Change|Breaking|

## Cause
 A public enumeration has the <xref:System.FlagsAttribute?displayProperty=fullName> and its name does not end in 's'.

## Rule description
 Types that are marked with <xref:System.FlagsAttribute> have names that are plural because the attribute indicates that more than one value can be specified. For example, an enumeration that defines the days of the week might be intended for use in an application where you can specify multiple days. This enumeration should have the <xref:System.FlagsAttribute> and could be called 'Days'. A similar enumeration that allows only a single day to be specified would not have the attribute, and could be called 'Day'.

 Naming conventions provide a common look for libraries that target the common language runtime. This reduces the learning curve that is required for new software libraries, and increases customer confidence that the library was developed by someone who has expertise in developing managed code.

## How to fix violations
 Make the name of the enumeration a plural word, or remove the <xref:System.FlagsAttribute> attribute if multiple enumeration values should not be specified simultaneously.

## When to suppress warnings
 It is safe to suppress a violation if the name is a plural word but does not end in 's'. For example, if the multiple-day enumeration that was described previously were named 'DaysOfTheWeek', this would violate the logic of the rule but not its intent. Such violations should be suppressed.

## Related rules
 [CA1027: Mark enums with FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: Do not mark enums with FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## See also

- <xref:System.FlagsAttribute?displayProperty=fullName>
- [Enum Design](/dotnet/standard/design-guidelines/enum)