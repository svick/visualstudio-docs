---
title: "Accessibility tips and tricks for Visual Studio"
description: "Learn more about tips and tricks that can help make the Visual Studio integrated development environment (IDE) more accessible for everyone to use, including people with disabilities."
ms.date: 09/15/2017
ms.prod: visual-studio-dev15
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
  - "accessibility [Visual Studio]"
ms.assetid: 6b491d88-f79e-4686-8841-857624bdcfda
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
  - "multiple"
---
# Accessibility tips and tricks for Visual Studio

> [!TIP]
> To learn more about recent accessibility updates, see the [Accessibility improvements in Visual Studio 2017 version 15.3](https://blogs.msdn.microsoft.com/visualstudio/2017/08/14/accessibility-improvements-in-visual-studio-2017-version-15-3/) blog post.

Visual Studio has built-in accessibility features that are compatible with screen readers and other assistive technologies. This topic lists common shortcut key combinations that you can use to perform tasks with the keyboard only, and includes information about using high-contrast themes to improve visibility. As well, it shows you how to use annotations to reveal useful information about your code, and how to set sound cues for build and breakpoint events.

> [!NOTE]
> This topic applies to Visual Studio on Windows. For Visual Studio for Mac, see [Accessibility for Visual Studio for Mac](/visualstudio/mac/accessibility).

## Save your IDE settings

 You can customize your IDE experience by saving your window layout, keyboard mapping scheme, and other preferences. For more information, see [Personalize the Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).

## Modify your IDE for high-contrast viewing

For some folks, some colors are more difficult to see. If you want more contrast as you code but do not want to use the typical "High Contrast" themes, we now offer a “Blue (Extra Contrast)” theme.

  ![Compare the Blue theme and Blue Extra Contrast theme](media/blue-extra-contrast-theme.png)

## Use annotations to reveal useful information about your code

The Visual Studio editor includes many text "adornments" that let you know about characteristics and features at particular points on a line of code, such as lightbulbs, error and warning “squiggles”, bookmarks, and so on. You can use the “Show Line Annotations” command set to help you discover and then navigate between these adornments.

  ![Use the Show Line Annotations command set](media/show-line-annotations-command-set.png)

## Access toolbars by using shortcut key combinations

The Visual Studio IDE has toolbars as do many tool windows. The following shortcut key combinations help you access them.

|Feature|Description|Key Combination|
|-------------|-----------------| - |
|IDE toolbars|Select the first button on the Standard toolbar.|**ALT**, **CTRL** + **TAB**|
|Tool window toolbars|Move focus to the toolbars in a tool window. <br> <br> **NOTE:** This works for most tool windows, but only when the focus is in a tool window. Also, you must choose the SHIFT key before the ALT key. In some tool windows, such as Team Explorer, you must hold the SHIFT key for a moment before choosing the ALT key.|**SHIFT** + **ALT**|
|Toolbars|Go to the first item in the next toolbar (when a toolbar has focus).|**CTRL** + **TAB**|

### Other useful shortcut key combinations

Some other useful shortcut key combinations include the following.

|Feature|Description|Key Combination|
|-------------|-----------------| - |
|IDE|Switch High Contrast on and off. <br> <br> **NOTE:** Standard Windows shortcut|**Left ALT + Left SHIFT + PRINT SCREEN**|
|Dialog box|Select or clear the check box option in a dialog box. <br> <br> **NOTE:** Standard Windows shortcut|**SPACEBAR**|
|Context menus|Open a context (right-click) menu. <br> <br> **NOTE:** Standard Windows shortcut|**SHIFT** + **F10**|
|Menus|Quickly access a menu item by using its accelerator keys. Choose the **ALT** key followed by the underlined letters in a menu to activate the command. For example, to view the Open Project dialog box in Visual Studio, you would choose **ALT** + **F** + **O** + **P**.  <br><br> **NOTE:** Standard Windows shortcut|**ALT** + **[letter]**|
|Toolbox window|Move among Toolbox tabs.|**CTRL** + **UPARROW**<br /><br /> and<br /><br /> **CTRL** + **DOWNARROW**|
|Toolbox window|Add a control from the Toolbox to a form or designer.|**ENTER**|
|Keyboard, Environment, Options dialog box|Delete a key combination entered in the **Press shortcut keys** option.|**BACKSPACE**|

> [!NOTE]
> The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.

## Use the Sound applet to set build and breakpoint cues

You can use the Sound applet in Windows to assign a sound to Visual Studio program events. Specifically, you can assign sounds to the following program events:

 * Breakpoint hit
 * Build canceled
 * Build failed
 * Build succeeded

Here's how.

1. In the **Search** box on a computer running Windows 10, type **Change system sounds**.

   ![Search box in Windows 10](media/type-here-to-search.png)

   (Alternatively, if you have Cortana enabled, say "Hey Cortana", and then say "Change system sounds".)

2. Double-click **Change system sounds**.

   ![Search results in Windows 10](media/change-system-sounds.png)

3. In the **Sound** dialog box, click the **Sounds** tab. <br><br>
   Then, in **Program Events**, scroll to **Microsoft Visual Studio**, and select the sounds that you want to apply to the events that you choose.

   ![Sounds tab of the Sound applet in Windows 10](media/sound-applet.png)

4. Click **OK**.

## See also

* [Accessibility features of Visual Studio](../../ide/reference/accessibility-features-of-visual-studio.md)
* [How to: Customize menus and toolbars in Visual Studio](../../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md)
* [Personalize the Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)
* [Microsoft Accessibility](https://www.microsoft.com/Accessibility)
* [Accessibility (Visual Studio for Mac)](/visualstudio/mac/accessibility)