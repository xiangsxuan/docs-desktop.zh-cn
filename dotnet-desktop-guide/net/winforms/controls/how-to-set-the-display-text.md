---
title: 设置控件显示的文本
description: 了解如何设置 Windows 窗体控件所显示的文本。 使用 Text 属性设置或返回文本，或使用 Font 属性更改字体。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.openlocfilehash: 2fd5a62310ae5e7d6e0528c7f12f37ed40f8a626
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941920"
---
# <a name="how-to-set-the-text-displayed-by-a-control-windows-forms-net"></a>操作说明：设置控件显示的文本（Windows 窗体 .NET）

Windows 窗体控件通常会显示一些与控件的主要功能相关的文本。 例如，<xref:System.Windows.Forms.Button> 控件通常会显示一个题注，用于指示单击按钮时将执行的操作。 对于所有控件而言，都可通过使用 <xref:System.Windows.Forms.Control.Text%2A> 属性来设置或返回文本。 可以使用 <xref:System.Windows.Forms.Control.Font%2A> 属性更改字体。

还可使用[设计器](#designer)来设置文本。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a>Designer

01. 在 Visual Studio 中的“属性”窗口中，将控件的 Text 属性设置为相应的字符串 。

    若要创建一个带下划线的快捷键，请在将作为快捷键的字母前添加一个 & 符号。

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/properties-text.png" alt-text="显示了 Text 属性的 .NET Windows 窗体的 Visual Studio“属性”窗格。":::

01. 在“属性”窗口中，选择 Font 属性旁边的省略号按钮（![Visual Studio 的“属性”窗口中的省略号按钮 (...)](../media/visual-studio-ellipsis-button.png)） 。

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/properties-font.png" alt-text="显示了 Font 属性的 .NET Windows 窗体的 Visual Studio“属性”窗格。":::

    在标准字体对话框中，用类型、大小和样式等设置调整字体。

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/font-window.png" alt-text="显示了 Font 设置窗口的 .NET Windows 窗体的 Visual Studio“属性”窗格。":::

## <a name="programmatic"></a>编程

01. 将 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为字符串。

    若要创建一个带下划线的访问键，请在将作为访问键的字母前添加一个 & 符号。

01. 将 <xref:System.Windows.Forms.Control.Font%2A> 属性设置为类型 <xref:System.Drawing.Font> 的对象。

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    > [!NOTE]
    > 可使用转义符来显示用户界面元素中的特殊字符，通常对这些元素（如菜单项）有着不同的解释。 例如，下面的代码行将菜单项的文本设置为“& 现读取完全不同的内容”：

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [如何：创建 Windows 窗体控件的访问键](how-to-create-access-keys.md)
