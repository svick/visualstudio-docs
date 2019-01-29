---
title: "Create a network-based installation"
description: "Learn how to create a network install point for deploying Visual Studio within an enterprise."
ms.date: 01/15/2019
ms.custom: "seodec18"
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
  - "{{PLACEHOLDER}}"
  - "{{PLACEHOLDER}}"
ms.assetid: 4CABFD20-962E-482C-8A76-E4012052F701
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
  - "multiple"
---
# Create a network installation of Visual Studio 2017

Typically, an enterprise administrator creates a network install point for deployment to client workstations. We've designed Visual Studio 2017 to enable you to cache the files for the initial installation along with all product updates to a single folder. (This process is also referred to as _creating a layout_.) We've done this so that client workstations can use the same network location to manage their installation even if they haven't yet updated to the latest servicing update.

 > [!NOTE]
 > If you have multiple editions of Visual Studio in use within your enterprise (for example, both Visual Studio Professional and Visual Studio Enterprise), you must create a separate network install share for each edition.

## Download the Visual Studio bootstrapper

Download the edition of Visual Studio you want. Make sure to click **Save**, and then click **Open folder**.

Your setup executable&mdash;or to be more specific, a bootstrapper file&mdash;should match one of the following.

|Edition | Download|
|-------------|-----------------------|
|Visual Studio Enterprise | [**vs_enterprise.exe**](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=enterprise&rel=15?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=network+install&utm_content=download+vs2017) |
|Visual Studio Professional | [**vs_professional.exe**](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=professional&rel=15?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=network+install&utm_content=download+vs2017) |
|Visual Studio Community | [**vs_community.exe**](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&rel=15?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=network+install&utm_content=download+vs2017) |

Other supported bootstrappers include [vs_buildtools.exe](https://aka.ms/vs/15/release/vs_buildtools.exe), [vs_feedbackclient.exe](https://aka.ms/vs/15/release/vs_feedbackclient.exe), [vs_teamexplorer.exe](https://aka.ms/vs/15/release/vs_teamexplorer.exe), [vs_testagent.exe](https://aka.ms/vs/15/release/vs_testagent.exe), [vs_testcontroller.exe](https://aka.ms/vs/15/release/vs_testcontroller.exe), and [vs_testprofessional.exe](https://aka.ms/vs/15/release/vs_testprofessional.exe).

## Create an offline installation folder

You must have an internet connection to complete this step. To create an offline installation with all languages and all features, use one of the commands from the following examples.

   > [!IMPORTANT]
   > A complete Visual Studio 2017 layout requires at least 35 GB of disk space and can take some time to download.  See the [Customizing the network layout](#customizing-the-network-layout) section for details on how to create a layout with only the components you want to install.
   >
   > [!TIP]
   > Make sure that you run the command from your Download directory. Typically, that's `C:\Users\<username>\Downloads` on a computer running Windows 10.

- For Visual Studio Enterprise, run:

  ```vs_enterprise.exe --layout c:\vs2017offline```

- For Visual Studio Professional, run:

  ```vs_professional.exe --layout c:\vs2017offline```

- For Visual Studio Community, run:

  ```vs_community.exe --layout c:\vs2017offline```

## Modify the response.json file

You can modify the response.json to set default values that are used when setup is run.  For example, you can configure the `response.json` file to select a specific set of workloads selected automatically.
See [Automate Visual Studio installation with a response file](automated-installation-with-response-file.md) for details.

## Copy the layout to a network share

Host the layout on a network share so it can be run from other machines.
* Example:<br>
```xcopy /e c:\vs2017offline \\server\products\VS2017```

## Customizing the network layout

There are several options you can use to customize your network layout. You can create a partial layout that only contains a specific set of [language locales](use-command-line-parameters-to-install-visual-studio.md#list-of-language-locales), [workloads, components, and their recommended or optional dependencies](workload-and-component-ids.md). This might be useful if you know that you are going to deploy only a subset of workloads to client workstations. Typical command-line parameters for customizing the layout include:

* ```--add``` to specify [workload or component IDs](workload-and-component-ids.md).  If `--add` is used, only those workloads and components specified with `--add` are downloaded.  If `--add` is not used, all workload and components are downloaded.
* ```--includeRecommended``` to include all the recommended  components for the specified workload IDs
* ```--includeOptional``` to include all the recommended and optional components for the specified workload IDs.
* ```--lang``` to specify [language locales](use-command-line-parameters-to-install-visual-studio.md#list-of-language-locales).

Here are a few examples of how to create a custom partial layout.

* To download all workloads and components for only one language, run: <br>```vs_enterprise.exe --layout C:\vs2017offline --lang en-US```
* To download all workloads and components for multiple languages, run: <br>```vs_enterprise.exe --layout C:\vs2017offline --lang en-US de-DE ja-JP```
* To download one workload for all languages, run <br> ```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure --includeRecommended```
* To download two workloads and one optional component for three languages, run: <br>```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Component.GitHub.VisualStudio --includeRecommended --lang en-US de-DE ja-JP ```
* To download two workloads and all of their recommended components, run: <br>```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Component.GitHub.VisualStudio --includeRecommended ```
* To download two workloads and all of their recommended and optional components, run: <br>```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Component.GitHub.VisualStudio --includeOptional ```

### New in 15.3

When you run a layout command, the options that you specify are saved (such as the workloads and languages). Subsequent layout commands will include all of the previous options.  Here is an example of a layout with one workload for English only:

```vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --lang en-US```

When you want to update that layout to a newer version, you don't have to specify any additional command-line parameters. The previous settings are saved and used by any subsequent layout commands in this layout folder.  The following command will update the existing partial layout.

```vs_enterprise.exe --layout c:\VS2017Layout```

When you want to add an additional workload, here's an example of how to do so. In this case, we'll add the Azure workload and a localized language.  Now, both Managed Desktop and Azure are included in this layout.  The language resources for English and German are include for all these workloads. The layout is updated to the latest available version.

```vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.Azure --lang de-DE```

If you want to update an existing layout to a full layout, use the --all option, as shown in the following example.

```vs_enterprise.exe --layout c:\VS2017Layout --all```

## Deploying from a network installation

Administrators can deploy Visual Studio onto client workstations as part of an installation script. Or, users who have administrator rights can run setup directly from the share to install Visual Studio on their machine.

* Users can install by running: <br>```\\server\products\VS2017\vs_enterprise.exe```
* Administrators can install in an unattended mode by running: <br>```\\server\products\VS2017\vs_enterprise.exe --quiet --wait --norestart```

> [!IMPORTANT]
> To prevent an error, make sure that your full installation path is less than 80 characters.
>
> [!TIP]
> When executed as part of a batch file, the `--wait` option ensures that the `vs_enterprise.exe` process waits until the installation is complete before it returns an exit code. This is useful if an enterprise administrator wants to perform further actions on a completed installation (for example, to [apply a product key to a successful installation](automatically-apply-product-keys-when-deploying-visual-studio.md)) but must wait for the installation to finish to handle the return code from that installation.  If you do not use `--wait`, the `vs_enterprise.exe` process exits before the installation is complete and returns an inaccurate exit code that doesn't represent the state of the install operation.


When you install from a layout, the content that is installed is acquired from the layout. However, if you select a component that is not in the layout, it will be acquired from the internet.  If you want to prevent Visual Studio setup from downloading any content that is missing in your layout, use the `--noWeb` option.  If `--noWeb` is used and the layout is missing any content that is selected to be installed, setup fails.

### Error codes

If you used the `--wait` parameter, then depending on the result of the operation, the `%ERRORLEVEL%` environment variable is set to one of the following values:

  | **Value** | **Result** |
  | --------- | ---------- |
  | 0 | Operation completed successfully |
  | 3010 | Operation completed successfully, but install requires reboot before it can be used |
  | Other | Failure condition occurred - check the logs for more information |

## Updating a network install layout

As product updates become available, you might want to [update the network install layout](update-a-network-installation-of-visual-studio.md) to incorporate updated packages.

## How to create a layout for a previous Visual Studio 2017 release

> [!NOTE]
> The Visual Studio 2017 bootstrappers that are available on [visualstudio.microsoft.com](http://visualstudio.microsoft.com) download and install the latest Visual Studio 2017 release available whenever they are run. If you download a Visual Studio bootstrapper today and run it six months from now, it installs the Visual Studio 2017 release that is available at that later time. If you create a layout, installing Visual Studio from that layout installs the specific version of Visual Studio that exists in the layout. Even though a newer version might exist online, you get the version of Visual Studio that is in the layout.

If you need to create a layout for an older version of Visual Studio 2017, you can go to https://my.visualstudio.com to download "fixed" versions of the Visual Studio 2017 bootstrappers.

### How to get support for your offline installer

If you experience a problem with your offline installation, we want to know about it. The best way to tell us is by using the [Report a Problem](../ide/how-to-report-a-problem-with-visual-studio-2017.md) tool. When you use this tool, you can send us the telemetry and logs we need to help us diagnose and fix the problem.

We also offer a [**live chat**](https://visualstudio.microsoft.com/vs/support/#talktous) (English only) support option for installation-related issues.

We have other support options available, too. For a list, see our [Talk to us](../ide/how-to-report-a-problem-with-visual-studio-2017.md) page.

## See also

* [Install Visual Studio](install-visual-studio.md)
* [Visual Studio administrator guide](visual-studio-administrator-guide.md)
* [Use command-line parameters to install Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio workload and component IDs](workload-and-component-ids.md)
