---
title: 如何管理鼠标指针
description: 了解如何在 .NET 的 Windows 窗体中访问、控制和更改鼠标指针。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.openlocfilehash: b4439c34bf7a7f41a94ce5ec5971520d9c82e469
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941972"
---
# <a name="manage-mouse-pointers-windows-forms-net"></a>管理鼠标指针（Windows 窗体 .NET）

鼠标指针（有时被称为光标）是一个位图，通过鼠标在屏幕上为用户指定一个输入焦点。 本主题概述了 Windows 窗体中的鼠标指针，并介绍了一些修改和控制鼠标指针的方法。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="accessing-the-mouse-pointer"></a>访问鼠标指针

鼠标指针由 <xref:System.Windows.Forms.Cursor> 类表示，每个 <xref:System.Windows.Forms.Control> 都具有一个 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> 属性，该属性指定该控件的指针。 <xref:System.Windows.Forms.Cursor> 类包含描述指针的属性（如 <xref:System.Windows.Forms.Cursor.Position%2A> 和 <xref:System.Windows.Forms.Cursor.HotSpot%2A> 属性）以及可以修改指针外观的方法（如 <xref:System.Windows.Forms.Cursor.Show%2A>、<xref:System.Windows.Forms.Cursor.Hide%2A> 和 <xref:System.Windows.Forms.Cursor.DrawStretched%2A> 方法）。

在下面的示例中，会在光标悬停在按钮上时隐藏光标：

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="ShowHideCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="ShowHideCursor":::

## <a name="controlling-the-mouse-pointer"></a>控制鼠标指针

有时，你可能想要限制可以使用鼠标指针的区域或更改鼠标的位置。 可以使用 <xref:System.Windows.Forms.Cursor> 的 <xref:System.Windows.Forms.Cursor.Position%2A> 属性获取或设置鼠标的当前位置。 此外，可以通过设置 <xref:System.Windows.Forms.Cursor.Clip%2A> 属性来限制可以使用鼠标指针的区域。 默认情况下，剪辑区域是整个屏幕。

在下面的示例中，会在单击两个按钮时将鼠标指针放置在这两个按钮之间：

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="MoveCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="MoveCursor":::

## <a name="changing-the-mouse-pointer"></a>更改鼠标指针

更改鼠标指针是向用户提供反馈的重要方式。 例如，可以在 <xref:System.Windows.Forms.Control.MouseEnter> 和 <xref:System.Windows.Forms.Control.MouseLeave> 事件的处理程序中修改鼠标指针，以告知用户正在进行计算并限制控件中的用户交互。 有时，鼠标指针会因系统事件而发生变化，例如当应用程序涉及拖放操作时。

更改鼠标指针的主要方式是将控件的 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> 或 <xref:System.Windows.Forms.Control.DefaultCursor%2A> 属性设置为新的 <xref:System.Windows.Forms.Cursor>。 有关更改鼠标指针的示例，请参阅 <xref:System.Windows.Forms.Cursor> 类中的代码示例。 此外，<xref:System.Windows.Forms.Cursors> 类公开了许多不同类型的指针（如手形指针）的一组 <xref:System.Windows.Forms.Cursor> 对象。

下面的示例将按钮的鼠标指针的光标更改为手形形状：

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="SetControlCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="SetControlCursor":::

若要在鼠标指针位于控件上方时显示等待指针（沙漏状），请使用 <xref:System.Windows.Forms.Control> 类的 <xref:System.Windows.Forms.Control.UseWaitCursor%2A> 属性。

## <a name="see-also"></a>另请参阅

- [使用鼠标的概述（Windows 窗体 .NET）](overview.md)
- [使用鼠标事件（Windows 窗体 .NET）](events.md)
- [如何区分单击和双击（Windows 窗体 .NET）](how-to-distinguish-between-clicks-and-double-clicks.md)
- [如何模拟鼠标事件（Windows 窗体 .NET）](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>
