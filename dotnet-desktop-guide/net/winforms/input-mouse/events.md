---
title: 使用鼠标事件
description: 使用鼠标事件处理鼠标输入的概述。 每个事件都可以提供关联的数据。 本文提供与鼠标相关的事件的列表。
ms.date: 10/26/2020
ms.topic: conceptual
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Click event [Windows Forms]
- mouse [Windows Forms], mouse events
- Click event
- MouseClick event
- DoubleClick event
- MouseDown event
- MouseEnter event
- MouseHover event
- MouseLeave event
- MouseMove event
- MouseUp event
- MouseWheel event
- mouse events
- events [Windows Forms], mouse
ms.openlocfilehash: 84d3fc0ef8bca25defead65590d1e50369e628b4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941908"
---
# <a name="using-mouse-events-windows-forms-net"></a>使用鼠标事件（Windows 窗体 .NET）

大多数 Windows 窗体程序通过处理鼠标事件来处理鼠标输入。 本文概述了鼠标事件，包括有关何时使用每个事件和为每个事件提供的数据的详细信息。 有关一般事件的详细信息，请参阅[事件概述（Windows 窗体 .NET）](../forms/events.md)。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="mouse-events"></a>鼠标事件

响应鼠标输入的主要方法是处理鼠标事件。 下表显示了鼠标事件并说明了这些事件的引发时间。

| 鼠标事件                                          | 描述                                             |
|------------------------------------------------------|---------------------------------------------------------|
| <xref:System.Windows.Forms.Control.Click>            | 此事件在释放鼠标按钮时发生，通常在 <xref:System.Windows.Forms.Control.MouseUp> 事件之前。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。 如果只需确定何时发生单击，处理此事件。                                                                             |
| <xref:System.Windows.Forms.Control.MouseClick>       | 此事件在用户使用鼠标单击控件时发生。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。 如果需要在发生单击时获取有关鼠标的信息，处理此事件。                                                                                                   |
| <xref:System.Windows.Forms.Control.DoubleClick>      | 此事件在双击控件时发生。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。 如果只需确定何时发生双击，处理此事件。                                                                                                                                             |
| <xref:System.Windows.Forms.Control.MouseDoubleClick> | 此事件在用户使用鼠标双击控件时发生。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。 如果需要在发生双击时获取有关鼠标的信息，处理此事件。                                                                                     |
| <xref:System.Windows.Forms.Control.MouseDown>        | 当鼠标指针位于控件上方并且用户按下鼠标按钮时，会发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。                                                                                                                                                            |
| <xref:System.Windows.Forms.Control.MouseEnter>       | 当鼠标指针进入控件的边框或工作区时（具体取决于控件的类型），会发生此事件。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。                                                                                                                                                     |
| <xref:System.Windows.Forms.Control.MouseHover>       | 此事件在鼠标指针停留在控件上时发生。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。                                                                                                                                                                                                      |
| <xref:System.Windows.Forms.Control.MouseLeave>       | 当鼠标指针离开控件的边框或工作区时（具体取决于控件的类型），会发生此事件。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。                                                                                                                                                 |
| <xref:System.Windows.Forms.Control.MouseMove>        | 当鼠标指针发生移动但仍位于控件上方时，会发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。                                                                                                                                                                                   |
| <xref:System.Windows.Forms.Control.MouseUp>          | 当鼠标指针位于控件上方，并且用户释放鼠标按钮时，会发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。                                                                                                                                                           |
| <xref:System.Windows.Forms.Control.MouseWheel>       | 当用户滚动鼠标滚轮并且控件有焦点时，会发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。 可以使用 <xref:System.Windows.Forms.MouseEventArgs> 的 <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> 属性来确定鼠标滚动的距离。 |

## <a name="mouse-information"></a>鼠标信息

<xref:System.Windows.Forms.MouseEventArgs> 将发送到与单击鼠标按钮和跟踪鼠标移动相关的鼠标事件处理程序。 <xref:System.Windows.Forms.MouseEventArgs> 提供有关当前鼠标状态的信息，包括鼠标指针在客户端坐标中的位置、按下的鼠标按钮是哪一个以及是否已经滚动鼠标滚轮。 几个鼠标事件（例如在鼠标指针进入或离开控件边界时引发的事件）会向事件处理程序发送 <xref:System.EventArgs>，但不提供详细信息。

如果想要知道鼠标按钮当前的状态或鼠标指针的位置，并且希望避免处理鼠标事件，还可以使用 <xref:System.Windows.Forms.Control> 类的 <xref:System.Windows.Forms.Control.MouseButtons%2A> 和 <xref:System.Windows.Forms.Control.MousePosition%2A> 属性。 <xref:System.Windows.Forms.Control.MouseButtons%2A> 返回有关当前按下哪些鼠标按钮的信息。 <xref:System.Windows.Forms.Control.MousePosition%2A> 返回鼠标指针的屏幕坐标，等同于由 <xref:System.Windows.Forms.Cursor.Position%2A> 返回的值。

## <a name="converting-between-screen-and-client-coordinates"></a>在屏幕坐标和客户端坐标之间转换

由于某些鼠标位置信息以客户端坐标提供，另一些以屏幕坐标提供，因此可能需要将某个点的位置信息从一个坐标系统转换到另一个坐标系统。 通过使用 <xref:System.Windows.Forms.Control> 类提供的 <xref:System.Windows.Forms.Control.PointToClient%2A> 和 <xref:System.Windows.Forms.Control.PointToScreen%2A> 方法可轻松完成此操作。

## <a name="standard-click-event-behavior"></a>标准 Click 事件行为

如果想要以正确的顺序处理鼠标单击事件，则需要了解在 Windows 窗体控件中引发的单击事件的顺序。 当按下任何受支持的鼠标按钮并释放时，所有 Windows 窗体控件都将以相同的顺序引发单击事件，下表中注明的个别控件除外。 下表显示单击鼠标按钮所引发事件的顺序：

01. <xref:System.Windows.Forms.Control.MouseDown> 事件。
01. <xref:System.Windows.Forms.Control.Click> 事件。
01. <xref:System.Windows.Forms.Control.MouseClick> 事件。
01. <xref:System.Windows.Forms.Control.MouseUp> 事件。

下面显示双击鼠标按钮所引发事件的顺序：

01. <xref:System.Windows.Forms.Control.MouseDown> 事件。
01. <xref:System.Windows.Forms.Control.Click> 事件。
01. <xref:System.Windows.Forms.Control.MouseClick> 事件。
01. <xref:System.Windows.Forms.Control.MouseUp> 事件。
01. <xref:System.Windows.Forms.Control.MouseDown> 事件。
01. <xref:System.Windows.Forms.Control.DoubleClick> 事件。

    此顺序可能不同，具体取决于相关控件的 <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> 样式位是否设置为 `true`。 有关如何设置 <xref:System.Windows.Forms.ControlStyles> 位的详细信息，请参阅 <xref:System.Windows.Forms.Control.SetStyle%2A> 方法。

01. <xref:System.Windows.Forms.Control.MouseDoubleClick> 事件。
01. <xref:System.Windows.Forms.Control.MouseUp> 事件。

### <a name="individual-controls"></a>个别控件

以下控件不符合标准鼠标单击事件行为：

- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.CheckBox>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.RadioButton>

  > [!NOTE]
  > 对于 <xref:System.Windows.Forms.ComboBox> 控件，如果用户单击编辑字段、按钮或列表中的某个项，将发生稍后详细说明的事件行为。

  - **左键单击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **右键单击**：不会引发任何单击事件
  - **左键双击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>；<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **右键双击**：不会引发任何单击事件

- <xref:System.Windows.Forms.TextBox>、<xref:System.Windows.Forms.RichTextBox>、<xref:System.Windows.Forms.ListBox>、<xref:System.Windows.Forms.MaskedTextBox> 和 <xref:System.Windows.Forms.CheckedListBox> 控件

  > [!NOTE]
  > 当用户单击这些控件内的任意位置时，将发生稍后详细说明的事件行为。

  - **左键单击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **右键单击**：不会引发任何单击事件
  - **左键双击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>、<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick>
  - **右键双击**：不会引发任何单击事件

- <xref:System.Windows.Forms.ListView> 控件

  > [!NOTE]
  > 仅当用户单击 <xref:System.Windows.Forms.ListView> 控件中的项时，才会发生稍后详细说明的事件行为。 单击该控件上其他任意位置不会引发任何事件。 除了稍后说明的事件外，还有 <xref:System.Windows.Forms.ListView.BeforeLabelEdit> 和 <xref:System.Windows.Forms.ListView.AfterLabelEdit> 事件，如果想要对 <xref:System.Windows.Forms.ListView> 控件进行验证，你可能会对这些事件感兴趣。

  - **左键单击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **右键单击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **左键双击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>；<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick>
  - **右键双击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>；<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick>

- <xref:System.Windows.Forms.TreeView> 控件

  > [!NOTE]
  > 仅当用户单击 <xref:System.Windows.Forms.TreeView> 控件中的项或项的右侧时，才会发生稍后详细说明的事件行为。 单击该控件上其他任意位置不会引发任何事件。 除了稍后说明的事件，还有 <xref:System.Windows.Forms.TreeView.BeforeCheck>、<xref:System.Windows.Forms.TreeView.BeforeSelect>、<xref:System.Windows.Forms.TreeView.BeforeLabelEdit>、<xref:System.Windows.Forms.TreeView.AfterSelect>、<xref:System.Windows.Forms.TreeView.AfterCheck> 和 <xref:System.Windows.Forms.TreeView.AfterLabelEdit> 事件，如果想要对 <xref:System.Windows.Forms.TreeView> 控件进行验证，你可能会对这些事件感兴趣。

  - **左键单击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **右键单击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **左键双击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>；<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick>
  - **右键双击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>；<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick>

## <a name="painting-behavior-of-toggle-controls"></a>切换控件的绘制行为

切换控件（如派生自 <xref:System.Windows.Forms.ButtonBase> 类的控件）具有独特的绘制行为和鼠标单击事件：

01. 用户按下鼠标按钮。
01. 控件以按下状态进行绘制。
01. 引发 <xref:System.Windows.Forms.Control.MouseDown> 事件。
01. 用户释放鼠标按钮。
01. 控件以引发状态进行绘制。
01. 引发 <xref:System.Windows.Forms.Control.Click> 事件。
01. 引发 <xref:System.Windows.Forms.Control.MouseClick> 事件。
01. 引发 <xref:System.Windows.Forms.Control.MouseUp> 事件。

    > [!NOTE]
    > 如果用户在鼠标按钮处于按下状态时将指针移出切换控件（例如在鼠标按下时将鼠标从 <xref:System.Windows.Forms.Button> 控件移出），那么切换控件将以引发状态进行绘制，并且只发生 <xref:System.Windows.Forms.Control.MouseUp> 事件。 在这种情况下，将不会发生 <xref:System.Windows.Forms.Control.Click> 或 <xref:System.Windows.Forms.Control.MouseClick> 事件。

## <a name="see-also"></a>另请参阅

- [使用鼠标的概述（Windows 窗体 .NET）](overview.md)
- [管理鼠标指针（Windows 窗体 .NET）](how-to-manage-cursor-pointer.md)
- [如何模拟鼠标事件（Windows 窗体 .NET）](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>
