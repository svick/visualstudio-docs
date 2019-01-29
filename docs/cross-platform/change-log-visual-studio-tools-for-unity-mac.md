---
title: "Change Log (Visual Studio Tools for Unity, Mac) | Microsoft Docs"
ms.custom: ""
ms.date: "11/13/2018"
ms.technology: vs-unity-tools
ms.topic: "conceptual"
ms.assetid: 33a6ac54-d997-4308-b5a0-af7387460849
author: therealjohn
ms.author: johmil
manager: crdun
ms.workload:
  - "unity"
---
# Change Log (Visual Studio Tools for Unity, Mac)
Visual Studio Tools for Unity change log.

## 1.7.0.0
 Released November 13, 2018

### New Features

-   **Debugger:**

    -   Added more client information (IP, machine name) on the attach dialog.

### Bug fixes

-   **Debugger:**

     -   Fixed a deadlock in the library used to communicate with Unity’s debugger engine, making Visual Studio or Unity freeze, especially when hitting ‘Attach to Unity’ or restarting game.
     
-   **Integration:**

     -   Fixed Unity plugin activation when another default editor was selected.
     
     -   Fixed Unity file template creation.

## 1.6.0.2
 Released July 24, 2018

### Bug fixes

-   **Integration:**

     -   Rolled back the workaround for a Unity performance bug that has been fixed by Unity.
     
## 1.6.0.1
 Released July 10, 2018

### Bug fixes

-   **Integration:**

     -   Fixed Shader code coloration support.
     
## 1.6.0.0
 Released June 26, 2018

### Bug fixes

-   **Wizards:**

    -   Fixed typo with OnApplicationFocus message.

-   **Project Generation:**

     -   Transient workaround for a Unity performance bug: cache MonoIslands when generating projects.
     
     -   Do not convert portable pdb to mdb anymore when using the new Unity runtime.
     
## 1.5.0.2
 Released April 18, 2018
 
### New Features

-   **Integration:**

    -   Added support for basic Shader code completion.
    
    -   Added support for toggling comments in Shader files.

## 1.5.0.1
 Released March 28, 2018
 
### New Features

-   **Integration:**

    -   Added support for extra templates in the Unity Project Explorer.

## 1.5.0.0
 Released March 21, 2018
 
### New Features

-   **Integration:**

    -   Added support for detecting and attaching to Android players connected through USB.

## 1.4.0.3
 Released March 5, 2018
 
### New Features

-   **Project Generation:**

    -   Added support for the new project generator in Unity 2018.1.

-   **Integration:**

    -   Added option panel for dedicated settings.

## 1.4.0.2
 Released January 24, 2018
 
### Bug fixes

-   **Project Generation:**

    -   Fixed Mono version detection.

-   **Integration:**

    -   Fixed timing issues with 2018.1 and plugin activation.

    -   Fixed notifications when detecting a new player.

## 1.4.0.1
 Released January 23, 2018
 
### Bug fixes

-   **Integration:**

    -   Fixed Expand/Collapse folders on double-click

## 1.4.0.0
 Released December 13, 2017
 
### New Features

-   **Project Generation:**

    -   Added support for .NET Standard.

### Bug fixes

-   **Integration:**

    -   Fixed automatic pdb to mdb debug symbol conversion.

## 1.3.0.1
 Released December 12, 2017
 
### Bug fixes

-   **Integration:**

    -   Fixed indirect call to EditorPrefs.GetBool impacting the inspector while trying to change array size.

-   **Wizards:**

    -   Refresh roslyn context before inserting method.

## 1.3.0.0
 Released November 20, 2017
 
### New Features

-   **Wizards:**

    -   Added "Implement Unity message" wizard.

    -   Added support for the new completion API in VS for Mac 7.4.

## 1.2.0.0
 Released October 23, 2017
 
### New Features

-   **Debugger:**

    -   Added support for portable debug symbol files.

### Bug fixes

-   **Project Generation:**

    -   Fixed extra .dll extension wrongly added to the assembly filename.

    -   Do not force the AllowAttachedDebuggingOfEditor Unity flag as the default is now 'true'.

## 1.1.0.3
 Released October 23, 2017
 
### New Features

-   **Project Generation:**

    -   Added support for .NET 4.6 profile.

## 1.1.0.2
 Released August 8, 2017
 
### New Features

-   **Debugger:**

    -   Start the attach to process dialog if not sure which Unity to attach to.

-   **Project Generation:**

    -   Always enable unsafe compilation switch when Unity 5.6 is used.

## 1.1.0.1
 Released July 20, 2017
 
### New Features

-   **Integration:**

    -   Added support for localized resources.

## 1.1.0.0
 Released July 12, 2017
 
### New Features

-   **Integration:**

    -   Added support for attaching to players and editors through the Attach to process window.

-   **Project Generation:**

    -   Fixed assembly name references with mcs.rsp files.

    -   Added support for assembly.json compilation units.    

    -   Fixed defines with API levels.    

### Bug fixes

-   **Integration:**

    -   Fixed shader error message when compiling.

## 1.0.0.1
 Released May 4, 2017
 
### Bug fixes

-   **Integration:**

    -   Fixed active document tracking with hybrid and regular projects.

## 1.0.0.0
 Released May 3, 2017
