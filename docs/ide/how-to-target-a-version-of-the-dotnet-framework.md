---
title: Target a .NET Framework version
ms.date: 02/06/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
  - "targeting .NET Framework [Visual Studio]"
  - ".NET Framework version [Visual Studio]"
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
  - "dotnet"
---
# How to: Target a version of the .NET Framework

This document describes how to target a version of the .NET Framework when you create a project, and how to change the targeted version in an existing Visual Basic, C#, or Visual F# project.

> [!IMPORTANT]
> For information about how to change the target version for C++ projects, see [How to: Modify the target framework and platform toolset](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

## To target a version when you create a project

When you create a project, the available .NET Framework versions depend on which versions are installed, and the selected template in the **New Project** dialog box.

1. On the menu bar, choose **File** > **New** > **Project**.

1. In the list of installed templates, choose the type of project that you want to create, and enter a name for the project.

1. From the **Framework** drop-down list at the bottom of the **New Project** dialog box, choose the version of the .NET Framework that you want your project to target.

    The list of frameworks shows only those versions that are applicable to the template that you chose. Some project types, such as .NET Core, do not require .NET Framework. In such instances, the **Framework** drop-down list is hidden.

    ![Framework drop-down in New Project dialog](media/vside-newproject-framework.png)

1. Choose the **OK** button.

## To change the targeted version

You can change the targeted version of the .NET Framework in a Visual Basic, C#, or Visual F# project by following this procedure.

For information about how to change the target version for C++ projects, see [How to: Modify the target framework and platform toolset](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

1. In **Solution Explorer**, open the shortcut menu for the project that you want to change, and then choose **Properties**.

    ![Visual Studio Solution Explorer Properties](../ide/media/vs_slnexplorer_properties.png)

1. In the left column of the **Properties** window, choose the **Application** tab.

    ![Visual Studio App Properties Application tab](../ide/media/vs_slnexplorer_properties_applicationtab.png)

    > [!NOTE]
    > After you create a UWP app, you can't change the targeted version of either Windows or the .NET Framework.

1. In the **Target Framework** list, choose the version that you want.

1. In the verification dialog box that appears, choose the **Yes** button.

    The project unloads. When it reloads, it targets the .NET Framework version that you just chose.

    > [!NOTE]
    > If your code contains references to a different version of the .NET Framework than the one that you targeted, error messages may appear when you compile or run the code. To resolve these errors, you must modify the references. See [Troubleshoot .NET Framework targeting errors](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).

## See also

- [Visual Studio multi-targeting overview](../ide/visual-studio-multi-targeting-overview.md)
- [Troubleshoot .NET Framework targeting errors](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)
- [Application page, Project Designer (C#)](../ide/reference/application-page-project-designer-csharp.md)
- [Application page, Project Designer (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)
- [How to: Modify the target framework and platform toolset (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)