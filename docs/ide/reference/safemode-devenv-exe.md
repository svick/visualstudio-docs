---
title: -SafeMode (devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
  - "/SafeMode Devenv switch"
  - "Devenv, /SafeMode switch"
  - "SafeMode switch"
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
  - "multiple"
---
# /SafeMode (devenv.exe)

Starts Visual Studio in safe mode, loading only the default environment and services.

## Syntax

```shell
devenv /SafeMode
```

## Remarks

This switch prevents all third-party VSPackages from loading when Visual Studio starts, allowing stable execution.

## Example

The following example starts Visual Studio in safe mode.

```shell
devenv /safemode
```

## See also

- [Devenv command-line switches](../../ide/reference/devenv-command-line-switches.md)