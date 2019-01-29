---
title: "Remove Visual Studio"
titleSuffix: ""
description: "Learn how to completely remove Visual Studio from your computer, step-by-step."
ms.date: 09/12/2017
ms.custom: "seodec18"
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
  - "uninstall"
  - "uninstall Visual Studio"
  - "remove"
  - "remove Visual Studio"
  - "cleanup"
  - "cleanup Visual Studio"
  - "clean up"
  - "clean up Visual Studio"
ms.assetid: 9c81a777-9c95-4934-b517-c60c6dc78799
author: heaths
ms.author: tglee
manager: jillfra
ms.workload:
  - "multiple"
---
# Remove Visual Studio 2017

If you encounter a catastrophic error and cannot repair or uninstall Visual Studio, you can run the `InstallCleanup.exe` tool to remove installation files and product information for all installed instances of Visual Studio 2017 and newer. Running this tool is to be done as a last resort if repair or uninstall fail, and may uninstall features from other Visual Studio installations or other products which need to be repaired.

In the instructions below, you can run the tool with different command-line switches with the following behavior:

| Switch | Behavior |
| ------ | -------- |
| `-i`   | This switch is the default if no other switch is passed and removes only the main installation directory and product information. This behavior is preferable if you intend to reinstall the same version after you run the `InstallCleanup.exe` tool. |
| `-f`   | Specifying this switch removes the main installation directory, product information, and most other features installed outside the installation directory that may be shared with other Visual Studio installations or other products. This behavior is preferable if you intend to remove Visual Studio without reinstalling later. |

1. Close the Visual Studio Installer.
2. Open an administrator command prompt. To open an administrator command prompt, follow these steps:
   * Click the **Start** menu
   * Type **cmd**.
   * Right-click **Command Prompt**, and then click **Run as administrator**.
3. Type the full path of the `InstallCleanup.exe` utility and pass whichever command-line switch you desire. By default, the path of the utility is as follows:
   ```
   C:\Program Files (x86)\Microsoft Visual Studio\Installer\resources\app\layout\InstallCleanup.exe
   ```

If you do not find `InstallCleanup.exe` under the Visual Studio Installer directory - always located at `%ProgramFiles(x86)%\Microsoft Visual Studio` - follow the instructions to [install Visual Studio](install-visual-studio.md) and when the workload selection screen is displayed, close the window and follow the preceding steps again.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## See also

* [Install Visual Studio 2017](install-visual-studio.md)
* [Update Visual Studio 2017](update-visual-studio.md)
* [Modify Visual Studio 2017](modify-visual-studio.md)
* [Uninstall Visual Studio 2017](uninstall-visual-studio.md)
