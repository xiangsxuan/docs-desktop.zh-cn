---
title: 创建控件访问键
description: 了解如何在适用于 .NET 的 Windows 窗体中对控件或标签设置访问键快捷方式。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.openlocfilehash: 4d746082ffbaa749b882dcb1a769b5f9541c6fe8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941996"
---
# <a name="add-an-access-key-shortcut-to-a-control-windows-forms-net"></a>向控件添加访问键快捷方式（Windows 窗体 .NET）

访问键是菜单、菜单项或控件（如按钮）标签的文本中带下划线的字符。 使用访问键，用户可通过同时按 <kbd>Alt</kbd> 键和预定义的访问键来“单击”按钮。 例如，如果某个按钮运行打印窗体的过程，因此其 `Text` 属性设置为“Print”，则在字母“P”之前添加 & 号将导致在运行时为按钮文本中的字母“P”添加下划线。 用户可通过按 <kbd>Alt</kbd> 来运行与该按钮关联的命令。

不能接收焦点的控件不能有访问键，但标签控件除外。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a>Designer

在 Visual Studio 的“属性”窗口中，将 Text 属性设置为一个字符串，该字符串在将作为访问键的字母之前包含一个 & 符号 。 例如，若要将字母“P”设置为访问键，请输入 &Print。

:::image type="content" source="media/how-to-create-access-keys/properties-text.png" alt-text="包含已选择的 Text 属性和访问键的属性对话框":::

## <a name="programmatic"></a>编程

将 `Text` 属性设置为一个字符串，该字符串在将作为快捷方式的字母之前包含一个 & 符号。

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

## <a name="use-a-label-to-focus-a-control"></a>使用标签聚焦控件

尽管标签无法被聚焦，它也能够按窗体的 Tab 键顺序来聚焦下一个控件。 每个控件都分配有一个 <xref:System.Windows.Forms.Control.TabIndex> 属性的值，通常以升序顺序排列。 为 [Label.Text](xref:System.Windows.Forms.Label.Text) 属性分配访问键时，将聚焦于按 Tab 键顺序排列的下一个控件。

使用[计划](#programmatic)部分中的示例，如果该按钮未设置任何文本，而是显示打印机的图像，则可使用标签来聚焦该按钮。

```vb
' Set the letter "P" as an access key.
Label1.Text = "&Print"
Label1.TabIndex = 9
Button1.TabIndex = 10
```

```csharp
// Set the letter "P" as an access key.
label1.Text = "&Print";
label1.TabIndex = 9
button1.TabIndex = 10
```

## <a name="display-an-ampersand"></a>显示 & 符号

设置将 & 符号解释为访问键的控件的文本或描述文字时，请使用两个连续的 & 符号 (&&) 来显示单个 & 符号。 例如，设置为 `"Print && Close"` 的按钮的文本显示在 `Print & Close` 的描述文字中：

```vb
' Set the letter "P" as an access key.
Button1.Text = "Print && Close"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "Print && Close";
```

:::image type="content" source="media/how-to-create-access-keys/double-ampersand.png" alt-text="在按钮中显示 & 符号":::

## <a name="see-also"></a>另请参阅

- [如何：设置 Windows 窗体控件显示的文本](how-to-set-the-display-text.md)
- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.Label>
