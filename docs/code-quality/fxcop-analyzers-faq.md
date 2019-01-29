---
title: FxCop code analysis and FxCop analyzers
ms.date: 09/06/2018
ms.prod: visual-studio-dev15
ms.topic: overview
helpviewer_keywords:
  - "code analysis FAQ"
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
  - "dotnet"
---
# Frequently asked questions about FxCop and FxCop analyzers

It can be a little confusing to understand the differences between legacy FxCop and FxCop analyzers. This article aims to address some of questions you might have.

## What's the difference between legacy FxCop and FxCop analyzers?

Legacy FxCop runs post-build analysis on a compiled assembly. It runs as a separate executable called **FxCopCmd.exe**. FxCopCmd.exe loads the compiled assembly, runs code analysis, and then reports the results (or *diagnostics*).

FxCop analyzers are based on the .NET Compiler Platform ("Roslyn"). You [install them as a NuGet package](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-nuget-package) that's referenced by the project or solution. FxCop analyzers run source-code based analysis during compiler execution. FxCop analyzers are hosted within the compiler process, either **csc.exe** or **vbc.exe**, and run analysis when the project is built. Analyzer results are reported along with compiler results.

> [!NOTE]
> You can also [install FxCop analyzers as a Visual Studio extension](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-vsix). In this case, the analyzers execute as you type in the code editor, but they don't execute at build time. If you want to run FxCop analyzers as part of continuous integration (CI), install them as a NuGet package instead.

## Does the Run Code Analysis command run FxCop analyzers?

No. When you select **Analyze** > **Run Code Analysis** in Visual Studio 2017, it executes static code analysis or legacy FxCop. **Run Code Analysis** has no effect on Roslyn-based analyzers, including the Roslyn-based FxCop analyzers.

## Does the RunCodeAnalysis msbuild project property run analyzers?

No. The **RunCodeAnalysis** property in a project file (for example, *.csproj*) is only used to execute legacy FxCop. It runs a post-build msbuild task that invokes **FxCopCmd.exe**. This is equivalent to selecting **Analyze** > **Run Code Analysis** in Visual Studio.

## So how do I run FxCop analyzers then?

To run FxCop analyzers, first [install the NuGet package](install-fxcop-analyzers.md) for them. Then build your project or solution from Visual Studio or using msbuild. The warnings and errors that the FxCop analyzers generate will appear in the **Error List** or the command window.

## See also

- [Overview of .NET Compiler Platform analyzers](roslyn-analyzers-overview.md)
- [Get started with analyzers](fxcop-analyzers.yml)
- [Install FxCop analyzers](install-fxcop-analyzers.md)
