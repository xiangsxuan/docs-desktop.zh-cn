---
title: 如何区分单击和双击
description: 介绍用于区分 .NET 的 Windows 窗体的控件或窗体执行单击或双击的不同方式。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse [Windows Forms], click
- mouse [Windows Forms], double-click
- mouse clicks [Windows Forms], single versus double
ms.openlocfilehash: 7b58896a85ffd16ae2637b94d58845ed7a721c4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941910"
---
# <a name="how-to-distinguish-between-clicks-and-double-clicks-windows-forms-net"></a>如何区分单击和双击（Windows 窗体 .NET）

通常情况下，一次单击会启动一个用户界面操作，而一次双击则会扩展该操作 。 例如，一次单击通常可选择一个项，而双击则可编辑所选的项。 但是，Windows 窗体 Click 事件无法轻松应用于单击和双击执行多个不兼容操作的方案，因为绑定到 <xref:System.Windows.Forms.Control.Click> 或 <xref:System.Windows.Forms.Control.MouseClick> 事件的操作会在操作绑定到 <xref:System.Windows.Forms.Control.DoubleClick> 或 <xref:System.Windows.Forms.Control.MouseDoubleClick> 事件之前执行。 本主题演示此问题的两种解决方案。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

一种解决方案是处理双击事件，并回滚单击事件处理过程中的操作。 在极少数情况下，可能需要通过处理 <xref:System.Windows.Forms.Control.MouseDown> 事件并使用 <xref:System.Windows.Forms.SystemInformation> 类的 <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> 和 <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> 属性来模拟单击和双击行为。 度量点击之间的时间，如果在达到 <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> 值之前发生第二次单击，并且单击发生在由 <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> 定义的矩形范围内，请执行双击操作；否则，请执行单击操作。

## <a name="to-roll-back-a-click-action"></a>回滚单击操作

请确保你正在使用的控件具有标准双击行为。 如果不具有标准双击行为，请启用具有 <xref:System.Windows.Forms.Control.SetStyle%2A> 方法的控件。 处理双击事件，并回滚单击操作以及双击操作。 下面的代码示例演示了如何在启用了双击的情况下创建自定义按钮，以及如何回滚双击事件处理代码中的单击操作。

此代码示例使用可启用双击的新按钮控件：

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/DoubleClickButton.cs" id="DoubleClickButton":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/DoubleClickButton.vb" id="DoubleClickButton":::

下面的代码演示了窗体如何通过单击或双击新按钮控件来更改边框样式：

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/Form1.cs" id="RollbackForm":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/Form1.vb" id="RollbackForm":::

## <a name="to-distinguish-between-clicks"></a>区分点击

请使用 <xref:System.Windows.Forms.SystemInformation> 属性和 <xref:System.Windows.Forms.Timer> 组件来处理 <xref:System.Windows.Forms.Control.MouseDown> 事件和确定点击之间的位置和时间跨度。 根据是否发生单击或双击执行相应的操作。 下面的代码示例演示如何实现这一点。

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/Form2.cs":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/Form2.vb":::

## <a name="see-also"></a>另请参阅

- [使用鼠标的概述（Windows 窗体 .NET）](overview.md)
- [使用鼠标事件（Windows 窗体 .NET）](events.md)
- [管理鼠标指针（Windows 窗体 .NET）](how-to-manage-cursor-pointer.md)
- [如何模拟鼠标事件（Windows 窗体 .NET）](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Control.Click?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.MouseDown?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.SetStyle%2A?displayProperty=nameWithType>
