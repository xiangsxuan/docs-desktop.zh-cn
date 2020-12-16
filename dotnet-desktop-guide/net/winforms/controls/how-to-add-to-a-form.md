---
title: 将控件添加到窗体
description: 了解如何在适用于 .NET 的 Windows 窗体中将控件添加到窗体
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.openlocfilehash: 44a20f135eb0f1503a6e5204a33aa8dca092123f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941967"
---
# <a name="add-a-control-windows-forms-net"></a>添加控件（Windows 窗体 .NET）

大多数窗体的设计方法如下：向窗体表面添加控件，以定义用户界面 (UI)。 控件是窗体上的组件，用于显示信息或接受用户输入。<!-- TODO For more information about controls, see [Forms overview](..\forms\overview.md). -->

将控件添加到窗体的主要方法是使用 Visual Studio 设计器，但你也可以在运行时使用代码来管理窗体上的控件。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="add-with-designer"></a>使用设计器添加

Visual Studio 使用窗体设计器设计窗体。 “控件”窗格列出了应用可使用的所有控件。 可以通过两种方式从窗格中添加控件：

### <a name="add-the-control-by-double-clicking"></a>通过双击添加控件

双击控件时，它将自动添加到当前打开的具有默认设置的窗体中。

:::image type="content" source="media/how-to-add-to-a-form/toolbox-double-click.gif" alt-text="双击适用于 .NET Windows 窗体的 Visual Studio 的工具箱中的控件":::

### <a name="add-the-control-by-drawing"></a>通过拖动添加控件

通过单击选择控件。 在窗体中，拖选一个区域。 放置控件以适应所选区域的大小。

:::image type="content" source="media/how-to-add-to-a-form/toolbox-drag-draw.gif" alt-text="拖选和拖放适用于 .NET Windows 窗体的 Visual Studio 的工具箱中的控件":::

## <a name="add-with-code"></a>使用代码添加

可以创建控件，然后在运行时使用窗体的 <xref:System.Windows.Forms.Control.Controls%2A> 集合将其添加到窗体。 还可以使用此集合将控件从窗体中删除。

以下代码添加并放置了两个控件，即 [Label](xref:System.Windows.Forms.Label) 和 [TextBox](xref:System.Windows.Forms.TextBox)：

:::code language="csharp" source="snippets/how-to-add-to-a-form/cs/Form1.cs" id="CreateControl":::

:::code language="vb" source="snippets/how-to-add-to-a-form/vb/Form1.vb" id="CreateControl":::

## <a name="see-also"></a>另请参阅

- [如何：设置 Windows 窗体控件所显示的文本](how-to-set-the-display-text.md)
- [如何：向控件添加访问键快捷方式](how-to-create-access-keys.md)
- <xref:System.Windows.Forms.Label>
- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.Button>
