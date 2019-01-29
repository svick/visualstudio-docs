---
title: Deploy a layer model extension
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
  - "dependency diagrams, deploying extensions"
  - "layer models, deploying extensions"
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
  - "multiple"
ms.prod: visual-studio-dev15
---
# Deploy a layer model extension

Other users of Visual Studio can install layer modeling extensions that you create by using Visual Studio.

## Install your extension

Your extension is compiled to a VSIX file, which you can install on other computers. You can also install it on your development computer, to make the extension available in the main instance of Visual Studio.

### To install the extension

1. In the project that contains **source.vsix.manifest**, open the *bin* directory in File Explorer.

2. Copy the **\*.vsix** file to the computer on which you want to install the extension.

3. On the target computer, double-click the *.vsix file in Windows Explorer.

    The VSIX installer opens.

### To uninstall the extension

1.  In Visual Studio, on the **Tools** menu, click **Extensions and Updates**.

2.  Click the name of the extension and then click **Uninstall**.

## Install an Extension on Team Foundation Server

Team Foundation Server servers do not normally have Visual Studio installed, and so you cannot install the VSIX by double-clicking it. You must install the extension manually.

### To install your layer extension on a Team Foundation Server server

1.  Copy the .*vsix* files from your development computer to the Team Foundation Server (TFS) computer.

     Place the VSIX file in one of the following locations:

    -   To install for all users and services:

         %ProgramFiles%\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft

    -   To install only for the network service that runs the build:

         %WinDir%\ServiceProfiles\NetworkService\AppData\Local\Microsoft\VisualStudio\\[version]\Extensions\Microsoft

    -   If you have configured the build to run in interactive mode as a particular user, you can install just for that user:

         %LocalAppData%\Microsoft\VisualStudio\\[version]\Extensions\Microsoft

2.  Expand each VSIX file into a folder in the same location:

    1.  Change the file name extension from **.vsix** to **.zip**.

    2.  Extract the content of the .zip file to a folder.

    3.  Delete the .zip file

3.  Restart TFS.
