---
title: Options, Text Editor, XML, Formatting
ms.date: 10/29/2018
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
  - "VS.ToolsOptionsPages.Text_Editor.XML.Formatting"
ms.assetid: 203e60b2-7b80-4ff4-9fa1-aa9f4374377b
author: gewarren
ms.author: gewarren
manager: jillfra
---
# Options, Text Editor, XML, Formatting

Use the **Formatting** property page to specify how elements and attributes are formatted in your XML documents. To open the **Options** dialog box, click the **Tools** menu and then click **Options**. To access the **Formatting** property page, expand the **Text Editor** > **XML** > **Formatting** node.

## Attributes

**Preserve manual attribute formatting**

Do not reformat attributes. This setting is the default.

> [!NOTE]
> If the attributes are on multiple lines, the editor indents each line of attributes to match the indentation of the parent element.

**Align attributes each on a separate line**

Align the second and subsequent attributes vertically to match the indentation of the first attribute. The following XML text is an example of how the attributes would be aligned.

```xml
<item id = "123-A"
      name = "hammer"
      price = "9.95">
</item>
```

## Auto Reformat

**On paste from clipboard**

Reformat XML text pasted from the clipboard.

**On completion of end tag**

Reformat the element when the end tag is completed.

## Mixed Content

**Format mixed content by default.**

Attempt to reformat mixed content, except when the content is found in an `xml:space="preserve"` scope. This setting is the default.

If an element contains a mix of text and markup, the contents are considered to be mixed content. Following is an example of an element with mixed content.

```xml
<dir>c:\data\AlphaProject\
  <file readOnly="false">test1.txt</file>
  <file readOnly="false">test2.txt</file>
</dir>
```

## See also

- [How to: Create XML documentation (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/how-to-create-xml-documentation)
- [Code generation](../code-generation-in-visual-studio.md)