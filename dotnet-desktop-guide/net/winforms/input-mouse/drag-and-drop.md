---
title: 拖放鼠标行为
description: 了解 Windows 窗体上拖放操作的工作原理，包括如何使用鼠标执行拖放操作。
ms.date: 10/26/2020
ms.topic: conceptual
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag and drop [Windows Forms], Windows Forms
- Windows Forms, drag and drop
ms.openlocfilehash: d434b0f0e80c610fffeea26a6fff44b43ca07fed
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941904"
---
# <a name="drag-and-drop-mouse-behavior-overview-windows-forms-net"></a>拖放鼠标行为概述（Windows 窗体 .NET）

Windows 窗体包含一组实现拖放行为的方法、事件和类。 本主题概述了 Windows 窗体对拖放功能的支持。<!-- TODO Also see [Drag-and-Drop Operations and Clipboard Support](./advanced/drag-and-drop-operations-and-clipboard-support.md).-->

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="drag-and-drop-events"></a>拖放事件

拖放操作中有两类事件：一类是拖放操作的当前目标上发生的事件，一类是拖放操作的源上发生的事件。 若要执行拖放操作，必须处理这些事件。 通过使用这些事件的事件参数中的可用信息，可以轻松地实现拖放操作。

## <a name="events-on-the-current-drop-target"></a>当前拖放目标上的事件

下表显示在拖放操作的当前目标上发生的事件。

| 鼠标事件                                   | 描述                                                                                                                                                                                            |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <xref:System.Windows.Forms.Control.DragEnter> | 将对象拖入控件的边界时此事件发生。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.DragEventArgs> 的参数。                              |
| <xref:System.Windows.Forms.Control.DragOver>  | 在鼠标指针位于控件的边界内时如果拖动对象则此事件发生。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.DragEventArgs> 的参数。 |
| <xref:System.Windows.Forms.Control.DragDrop>  | 拖放操作完成时此事件发生。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.DragEventArgs> 的参数。                                      |
| <xref:System.Windows.Forms.Control.DragLeave> | 将对象拖出控件的边界时此事件发生。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。                                              |

<xref:System.Windows.Forms.DragEventArgs> 类提供鼠标指针的位置、鼠标按钮和键盘修改键的当前状态、正在拖动的数据以及 <xref:System.Windows.Forms.DragDropEffects> 值（指定拖动事件的源所允许的操作以及操作的目标放置效果）。

## <a name="events-on-the-drop-source"></a>放置源上的事件

下表显示在拖放操作的源上发生的事件。

|鼠标事件|描述|
|-----------------|-----------------|
|<xref:System.Windows.Forms.Control.GiveFeedback>|此事件在执行拖动操作期间发生。 借助此事件，可向用户提供可视提示（例如更改鼠标指针），通知拖放操作正在发生。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.GiveFeedbackEventArgs> 的参数。|
|<xref:System.Windows.Forms.Control.QueryContinueDrag>|此事件在拖放操作期间引发，并使拖动源可以确定是否应取消拖放操作。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.QueryContinueDragEventArgs> 的参数。|

<xref:System.Windows.Forms.QueryContinueDragEventArgs> 类提供鼠标按钮和键盘修改键的当前状态、指定是否按 ESC 键的值以及 <xref:System.Windows.Forms.DragAction> 值（可设置为指定是否应继续拖放操作）。

## <a name="performing-drag-and-drop"></a>执行拖放操作

拖放操作始终涉及两个组件 - 放置源和拖放目标 。 若要启动拖放操作，请指定一个控件作为源，并处理 <xref:System.Windows.Forms.Control.MouseDown> 事件。 在事件处理程序中，调用 <xref:System.Windows.DragDrop.DoDragDrop%2A> 方法，该方法提供与放置关联的数据和 <xref:System.Windows.DragDropEffects> 值。

将目标控件的 <xref:System.Windows.Forms.Control.AllowDrop> 属性设置为 `true`，以允许该控件接受拖放操作。 目标处理两个事件，第一个是响应控件上的拖动的事件，如 <xref:System.Windows.Forms.Control.DragOver>。 第二个事件是放置操作本身 - <xref:System.Windows.Forms.Control.DragDrop>。

下面的示例演示一个从 <xref:System.Windows.Forms.Label> 控件到 <xref:System.Windows.Forms.TextBox> 的拖动操作。 拖动操作完成后，`TextBox` 通过将标签的文本分配给其自身来做出响应。

```csharp
// Initiate the drag
private void label1_MouseDown(object sender, MouseEventArgs e) =>
    DoDragDrop(((Label)sender).Text, DragDropEffects.All);

// Set the effect filter and allow the drop on this control
private void textBox1_DragOver(object sender, DragEventArgs e) =>
    e.Effect = DragDropEffects.All;

// React to the drop on this control
private void textBox1_DragDrop(object sender, DragEventArgs e) =>
    textBox1.Text = (string)e.Data.GetData(typeof(string));
```

```vb
' Initiate the drag
Private Sub Label1_MouseDown(sender As Object, e As MouseEventArgs)
    DoDragDrop(DirectCast(sender, Label).Text, DragDropEffects.All)
End Sub

' Set the effect filter and allow the drop on this control
Private Sub TextBox1_DragOver(sender As Object, e As DragEventArgs)
    e.Effect = DragDropEffects.All
End Sub

' React to the drop on this control
Private Sub TextBox1_DragDrop(sender As Object, e As DragEventArgs)
    TextBox1.Text = e.Data.GetData(GetType(String))
End Sub
```

有关拖动效果的详细信息，请参阅<xref:System.Windows.Forms.DragEventArgs.Data%2A> 和 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>。

## <a name="see-also"></a>另请参阅

- [使用鼠标的概述（Windows 窗体 .NET）](overview.md)
- <xref:System.Windows.Forms.Control.DragDrop?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragEnter?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragLeave?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragOver?displayProperty=nameWithType>
