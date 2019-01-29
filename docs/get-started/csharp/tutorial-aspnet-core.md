---
title: "Tutorial: Get started with C# and ASP.NET Core"
titleSuffix: ""
description: "Learn how to create an ASP.NET Core web app in Visual Studio with C#, step-by-step."
ms.custom: "seodec18, get-started"
ms.date: 10/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.prod: visual-studio-dev15
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
  - CSharp
ms.workload:
  - "aspnet"
  - "dotnetcore"
---
# Tutorial: Get started with C# and ASP.NET Core in Visual Studio

In this tutorial for C# development with ASP.NET Core using Visual Studio, you'll create a C# ASP.NET Core web app, make changes to it, explore some features of the IDE, and then run the app.

## Before you begin

### Install Visual Studio

If you haven't already installed Visual Studio, go to the [Visual Studio downloads](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) page to install it for free.

### Update Visual Studio

If you've already installed Visual Studio, make sure that you are running the most recent release. For more information about how to update your installation, see the [Update Visual Studio 2017 to the most recent release](../../install/update-visual-studio.md) page.

### Choose your theme (optional)

This tutorial includes screenshots that use the dark theme. If you aren't using the dark theme but would like to, see the [Personalize the Visual Studio IDE and Editor](../../ide/quickstart-personalize-the-ide.md) page to learn how.

## Create a project

First, you'll create a ASP.NET Core project. The project type comes with all the template files you'll need for a fully functional website, before you've even added anything!

1. Open Visual Studio 2017.

2. From the top menu bar, choose **File** > **New** > **Project**.

3. In the **New Project** dialog box in the left pane, expand **Visual C#**, expand **Web**, and then choose **.NET Core**. In the middle pane, choose **ASP.NET Core Web Application**. Then, name the file *MyCoreApp* and choose **OK**.

   ![ASP.NET Core Web Application project template in the New Project dialog box in the Visual Studio IDE](media/csharp-aspnet-choose-template-name-razor-mycoreapp-file.png)

### Add a workload (optional)

If you don't see the **ASP.NET Core Web Application** project template, you can get it by adding the **ASP.NET and web development** workload. You can add this workload in one of the two following ways, depending on which Visual Studio 2017 updates are installed on your machine.

#### Option 1: Use the New Project dialog box

1. Select the **Open Visual Studio Installer** link in the left pane of the **New Project** dialog box. (Depending on your display settings, you might have to scroll to see it.)

   ![Select the Open Visual Studio Installer link from the New Project dialog box](../media/open-visual-studio-installer-mycoreapp.png)

1. The Visual Studio Installer launches. Choose the **ASP.NET and web development** workload, and then choose **Modify**.

   ![.NET Core cross-platform development workload in the Visual Studio Installer](../media/tutorial-aspnet-workload.png)

   (You might have to close Visual Studio before you can continue installing the new workload.)

#### Option 2: Use the Tools menu bar

1. Cancel out of the **New Project** dialog box. Then, from the top menu bar, choose **Tools** > **Get Tools and Features**.

1. The Visual Studio Installer launches. Choose the **ASP.NET and web development** workload, and then choose **Modify**.

   (You might have to close Visual Studio before you can continue installing the new workload.)

### Add a project template

1. In the **New ASP.NET Core Web Application** dialog box, choose the **Web Application** project template.

1. Verify that **ASP.NET Core 2.1** appears in the top drop-down menu. Then, choose **OK**.

   ![New ASP.NET Core Web Application dialog box](media/new-project-csharp-aspnet-razor-web-app.png)

   > [!NOTE]
   > If you don't see **ASP.NET Core 2.0** or later from the top drop-down menu, make sure that you are running the most recent release of Visual Studio. For more information about how to update your installation, see the [Update Visual Studio 2017 to the most recent release](../../install/update-visual-studio.md) page.

### About your solution

This solution follows the **Razor Page** design pattern. It is different than the [Model-View-Controller (MVC)](/aspnet/core/tutorials/first-mvc-app/start-mvc?view=aspnetcore-2.1&tabs=aspnetcore2x) design pattern in that its streamlined to include the model and controller code within the Razor Page itself.

## Tour your solution

 1. The project template creates a solution with a single ASP.NET Core project that is named _MyCoreApp_. Choose the **Solution Explorer** tab to view its contents.

    ![ASP.NET Solution Explorer in Visual Studio for Razor Pages solution that is named MyCoreApp](media/csharp-aspnet-razor-solution-explorer-mycoreapp.png)

 1. Expand the **Pages** folder, and then expand *About.cshtml*.

     ![The About.cshtml file in the Solution Explorer in Visual Studio](media/csharp-aspnet-razor-solution-explorer-aboutcshtml.png)

 1. View the **About.cshtml** file in the code editor.

     ![View the About.cshtml file in the Visual Studio code editor](media/csharp-aspnet-razor-aboutcshtml-mycoreapp-code.png)

 1. Choose the **About.cshtml.cs** file.

     ![Choose the About.cshtml.cs file in the Visual Studio code editor](media/csharp-aspnet-razor-solution-explorer-aboutcshtmlcs.png)

 1. View the **About.cshtml.cs** file in the code editor.

     ![View the About.cshtml file in the Visual Studio code editor](media/csharp-aspnet-razor-aboutcshtmlcs-mycoreapp-code.png)

 1. The project contains a **wwwroot** folder that is the root for your website. Expand the folder to view its contents.

     ![wwwroot folder in the Solution Explorer in Visual Studio](media/csharp-aspnet-razor-solution-explorer-wwwroot.png)

    You can put static site content&mdash;such as CSS, images, and JavaScript libraries&mdash;directly in the paths where you want them.

 1. The project also contains configuration files that manage the web app at runtime. The default application [configuration](/aspnet/core/fundamentals/configuration) is stored in *appsettings.json*. However, you can override these settings by using *appsettings.Development.json*. Expand the **appsettings.json** file to view the **appsettings.Development.json** file.

     ![Configuration files in the Solution Explorer in Visual Studio](media/csharp-aspnet-razor-solution-explorer-appsettingsjson.png)

## Run, debug, and make changes

1. Choose the **IIS Express** button in the IDE to build and run the app in Debug mode. (Alternatively, press **F5**, or choose **Debug** > **Start Debugging** from the menu bar.)

     ![Select the IIS Express button in Visual Studio](media/csharp-aspnet-razor-iisexpress.png)

     > [!NOTE]
     > If you get an error message that says **Unable to connect to web server 'IIS Express'**, close Visual Studio and then open it by using the **Run as administrator** option from the right-click or context menu. Then, run the application again.

1. Visual Studio launches a browser window. You should then see **Home**, **About**, and **Contact** pages in the menu bar. (If you do not, choose the "hamburger" menu item to view them.)

    ![Select the "hamburger" menu item from the menu bar in your web app](media/csharp-aspnet-razor-browser-page.png)

1. Choose **About** from the menu bar.

   ![Select About in the browser window's menu bar for your app](media/csharp-aspnet-razor-browser-page-about-menu.png)

   Among other things, the **About** page in the browser renders the text that is set in the *About.cshtml* file.

   ![View the text on the About page](media/csharp-aspnet-razor-browser-page-about.png)

1. Keep the browser window open and return to Visual Studio.

1. In Visual Studio, choose **About.cshtml**. Then, delete the word _additional_ and in its place, add the words _file and directory_.

    ![Change the text in the About.cshtml file](media/csharp-aspnet-razor-aboutcshtml-mycoreapp-code-changed.png)

1. Choose **About.cshtml.cs**. Then, clean up the `using` directives at the top of the file by using the following shortcut:

   Choose any of the grayed-out `using` directives and a [Quick Actions](../../ide/quick-actions.md) light bulb will appear just below the caret or in the left margin. Choose the light bulb, and then choose **Remove Unnecessary Usings**.

   ![Remove unnecessary Usings in the About.cshtml.cs file](media/csharp-aspnet-razor-remove-unnecessary-usings.png)

     Visual Studio deletes the unnecessary `using` directives from the file.

1. Next, in the `OnGet()` method, change the body to the following code:

     ```csharp
     public void OnGet()
     {
         string directory = Environment.CurrentDirectory;
     Message = String.Format("Your directory is {0}.", directory);
     }
    ```
1. Notice that two wavy underlines appear under **Environment** and **String**. The wavy underlines appear because these types are not in scope.

   ![Errors marked with wavy underlines in OnGet method](media/csharp-aspnet-razor-add-new-on-get-method.png)

    Open the **Error List** toolbar to see the same errors listed there. (If you don't see the **Error List** toolbar, choose **View** > **Error List** from the top menu bar.)

   ![Error List in Visual Studio](media/csharp-aspnet-razor-error-list.png)

1. Let's fix this. In the code editor, place your cursor on either line that contains the error, and then choose the Quick Actions light bulb in the left margin. Then, from the drop-down menu, choose **using System;** to add this directive to the top of your file and resolve the errors.

   ![Add the "using System;" directive](media/csharp-aspnet-razor-add-usings.png)

1. Press **Ctrl**+**S** to save your changes and refresh your app in the web browser.

1. At the top of the web site, choose **About** to view your changes.

   ![View the updated About page that includes the changes you made](media/csharp-aspnet-razor-browser-page-about-changed.png)

1. Close the web browser, press **Shift**+**F5** to stop Debug mode, and then close Visual Studio.

## Quick answers FAQ

Here's a quick FAQ to highlight some key concepts.

### What is C#?

[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework) is a type-safe and object-oriented programming language that's designed to be both robust and easy to learn.

### What is ASP.NET Core?

ASP.NET Core is an open-source and cross-platform framework for building internet-connected applications, such as web apps and services. ASP.NET Core apps can run on either .NET Core or the .NET Framework. You can develop and run your ASP.NET Core apps cross-platform on Windows, Mac, and Linux. ASP.NET Core is open source at [GitHub](https://github.com/aspnet/home).

### What is Visual Studio?

Visual Studio is an integrated development suite of productivity tools for developers. Think of it as a program you can use to create programs and applications.

## Next steps

Congratulations on completing this tutorial! We hope you learned a little bit about C#, ASP.NET Core, and the Visual Studio IDE. To learn more about creating a web app or website with C# and ASP.NET, continue with the following tutorials:

> [!div class="nextstepaction"]
> [Create a Razor Pages web app with ASP.NET Core](/aspnet/core/tutorials/razor-pages/?view=aspnetcore-2.1)

## See also

[Publish your web app to Azure App Service by using Visual Studio](../../deployment/quickstart-deploy-to-azure.md)
