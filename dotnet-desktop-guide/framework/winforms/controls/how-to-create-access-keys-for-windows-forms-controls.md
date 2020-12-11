---
title: 为控件创建访问键
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: 7f6b0a5838cacfc1189fba819a54b3423d567ea0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972055"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>如何：为 Windows 窗体控件创建访问键

*访问键* 是菜单、菜单项或控件（如按钮）的标签文本中带下划线的字符。 使用访问键，用户可以通过将 Alt 键与预定义访问键结合使用来 "单击" 按钮。 例如，如果按钮运行过程来打印窗体，因此其 `Text` 属性设置为 "打印"，则在字母 "p" 之前添加 "&" 符会导致在运行时将字母 "p" 添加到按钮文本中的下划线。 用户可以通过按 Alt + P 运行与该按钮关联的命令。

无法接收焦点的控件不能有访问密钥。

## <a name="programmatic"></a>编程

将 `Text` 属性设置为一个字符串，该字符串包含与将作为快捷方式的字母 ( # A0) 的符号。

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

```cpp
// Set the letter "P" as an access key.
button1->Text = "&Print";
```

> [!NOTE]
> 若要在标题中使用 "and" 符而不创建访问键，请包含两个与 ( # A2) 。 标题中将显示单个号，并且不会有任何字符带有下划线。

## <a name="designer"></a>Designer

在 Visual Studio 的 " **属性** " 窗口中，将 " **Text** " 属性设置为一个字符串，该字符串包含与将为访问键的字母 ( "&" ) 。 例如，若要将字母 "P" 设置为访问键，请输入 **&Print**。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Button>
- [如何：响应 Windows 窗体按钮的单击](how-to-respond-to-windows-forms-button-clicks.md)
- [如何：设置 Windows 窗体控件所显示的文本](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [标记单个 Windows 窗体控件并提供它们的快捷方式](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
