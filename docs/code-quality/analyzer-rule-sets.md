---
title: Analyzer rule sets
ms.date: 07/20/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
  - "analyzers, rule sets"
  - "rule sets for analyzers"
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
  - "multiple"
---
# Rule sets for Roslyn analyzers

Predefined rule sets are included with some NuGet analyzer packages. For example, the rule sets that are included with the [Microsoft.CodeAnalysis.FxCopAnalyzers NuGet analyzer package](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/) (starting in version 2.6.2) enable or disable rules based on their category, such as security, naming, or performance. Using rule sets makes it easy to quickly see only those rule violations that pertain to a particular category of rule.

If you're migrating from legacy "FxCop" static code analysis to Roslyn analyzers, these rule sets enable you to continue using the same rule configurations you used previously.

## Use analyzer rule sets

After you [install a NuGet analyzer package](install-roslyn-analyzers.md), locate the predefined rule set in its *rulesets* directory, for example *%USERPROFILE%\\.nuget\packages\microsoft.codequality.analyzers\<version>\rulesets*. From there, you can drag and drop, or copy and paste, one or more of the rulesets to your Visual Studio project in **Solution Explorer**.

To make a rule set the active rule set for analysis, right-click on the project in **Solution Explorer** and choose **Properties**. In the project property pages, select the **Code Analysis** tab. Under **Run this rule set**, select **Browse**, and then select the desired rule set that you copied to the project directory. Now you only see rule violations for those rules that are enabled in the selected rule set.

You can also [customize a predefined rule set](how-to-create-a-custom-rule-set.md#create-a-custom-rule-set) to your preference. For example, you can change the severity of one or more rules so that violations appear as errors or warnings in the **Error List**.

## Available rule sets

The predefined analyzer rule sets include three rulesets that affect all the rules in the package&mdash;one that enables them all, one that disables them all, and one that honors each rule's default severity and enablement settings:

- AllRulesEnabled.ruleset
- AllRulesDisabled.ruleset
- AllRulesDefault.ruleset

Additionally, there are two rule sets for each category of rules in the package, such as performance or security. One rule set enables all rules for the category, and one rule set honors the default severity and enablement settings for each rule in the category.

 The [Microsoft.CodeAnalysis.FxCopAnalyzers NuGet analyzer package](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/) includes rule sets for the following categories, to match the rule sets available for legacy "FxCop" static code analysis:

- design
- documentation
- maintainability
- naming
- performance
- reliability
- security
- usage

## See also

- [Overview of .NET Compiler Platform analyzers](roslyn-analyzers-overview.md)
- [Install .NET Compiler Platform analyzers](install-roslyn-analyzers.md)
- [Configure and use Roslyn analyzer rules](use-roslyn-analyzers.md)
- [Use rule sets to group code analysis rules](using-rule-sets-to-group-code-analysis-rules.md)