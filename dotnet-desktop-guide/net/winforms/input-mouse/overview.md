---
title: 鼠标输入概述
description: 了解适用于 .NET 的 Windows 窗体中鼠标输入的工作原理。 鼠标事件由窗体和控件引发，表示鼠标的位置和按钮状态。
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.openlocfilehash: 3e85305796d724d9acdbcd2e7cb86e748c30b783
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941940"
---
# <a name="overview-of-using-the-mouse-windows-forms-net"></a>使用鼠标的概述（Windows 窗体 .NET）

接收和处理鼠标输入是每个 Windows 应用程序的重要组成部分。 你可以处理鼠标事件以在应用程序中执行操作，或使用鼠标位置信息执行命中测试或其他操作。 此外，你还可更改应用程序中的控件处理鼠标输入的方式。 本文将详细介绍这些鼠标事件，以及如何获取和更改鼠标的系统设置。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

在 Windows 窗体中，用户输入以 [Windows 消息](/windows/win32/winmsg/about-messages-and-message-queues)的形式发送到应用程序。 一系列可重写的方法在应用程序、窗体和控件级别处理这些消息。 当这些方法接收鼠标消息时，它们会引发可处理的事件以获取有关鼠标输入的信息。 在许多情况下，Windows 窗体应用程序只需通过处理这些事件即可处理所有用户输入。 在其他情况下，应用程序可能会重写处理消息的方法之一，以便在应用程序、窗体或控件接收特定消息之前截获该消息。

## <a name="mouse-events"></a>鼠标事件

所有 Windows 窗体控件都将继承与鼠标和键盘输入相关的一组事件。 例如，控件可以处理 <xref:System.Windows.Forms.Control.MouseClick> 事件以确定鼠标单击的位置。 有关鼠标事件的详细信息，请参阅[使用鼠标事件](events.md)。

## <a name="mouse-location-and-hit-testing"></a>鼠标位置和命中测试

当用户移动鼠标时，操作系统将移动鼠标指针。 鼠标指针包含一个称为“热点”的像素，操作系统会跟踪该像素并将其识别为指针的位置。 当用户移动鼠标或按下鼠标按钮时，包含 <xref:System.Windows.Forms.Cursor.HotSpot%2A> 的 <xref:System.Windows.Forms.Control> 将引发相应的鼠标事件。

可以在处理鼠标事件时使用 <xref:System.Windows.Forms.MouseEventArgs> 的 <xref:System.Windows.Forms.MouseEventArgs.Location%2A> 属性获取当前鼠标位置，也可使用 <xref:System.Windows.Forms.Cursor> 类的 <xref:System.Windows.Forms.Cursor.Position%2A> 属性获取当前鼠标位置。 然后可使用鼠标位置信息来执行命中测试，然后根据鼠标的位置执行操作。 命中测试功能内置于 Windows 窗体中的若干控件，如 <xref:System.Windows.Forms.ListView>、<xref:System.Windows.Forms.TreeView>、<xref:System.Windows.Forms.MonthCalendar> 和 <xref:System.Windows.Forms.DataGridView> 控件。

与相应的鼠标事件（例如 <xref:System.Windows.Forms.Control.MouseHover>）一起使用时，命中测试在确定应用程序应何时执行特定操作时非常有用。

## <a name="changing-mouse-input-settings"></a>更改鼠标输入设置

可通过从控件派生并使用 <xref:System.Windows.Forms.Control.GetStyle%2A> 和 <xref:System.Windows.Forms.Control.SetStyle%2A> 方法，检测并更改控件处理鼠标输入的方式。 <xref:System.Windows.Forms.Control.SetStyle%2A> 方法使用 <xref:System.Windows.Forms.ControlStyles> 值的按位组合来确定控件是否将具有标准单击、双击行为，或控件是否将处理自己的鼠标处理。 此外，<xref:System.Windows.Forms.SystemInformation> 类还包括描述鼠标功能以及指定鼠标与操作系统交互方式的属性。 下表对这些属性进行了总结。

| 属性                                                               | 描述                                                                                                                                                            |
|------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>       | 获取如下区域的尺寸（以像素为单位）：用户必须在此区域内单击两次，操作系统才将这两次单击视为一次双击。                     |
| <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>       | 获取要将鼠标操作视为双击的第一次单击与第二次单击之间可以经过的最大毫秒数。 |
| <xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>          | 获取鼠标上的按钮数。                                                                                                                               |
| <xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>   | 获取一个值，该值指示是否已交换鼠标左右按钮的功能。                                                                   |
| <xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>        | 获取特定矩形的尺寸（以像素为单位），鼠标指针必须在该矩形范围内停留达到鼠标悬停时间后，才会生成鼠标悬停消息。        |
| <xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>        | 获取一个以毫秒为单位的时间，鼠标指针必须在悬停矩形中停留该时间后，才会生成鼠标悬停消息。                                   |
| <xref:System.Windows.Forms.SystemInformation.MousePresent%2A>          | 获取一个值，该值指示鼠标是否已安装。                                                                                                                  |
| <xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>            | 获取一个值，该值指示当前鼠标速度，范围为 1 至 20。                                                                                                         |
| <xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>     | 获取一个值，该值指示是否安装了带有鼠标轮的鼠标。                                                                                               |
| <xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A> | 获取单次鼠标轮旋转增量的增量值。                                                                                  |
| <xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A> | 获取滚动鼠标轮时所滚动过的行数。                                                                                                    |

## <a name="methods-that-process-user-input-messages"></a>处理用户输入消息的方法

窗体和控件可以访问 <xref:System.Windows.Forms.IMessageFilter> 接口和一组可重写的方法，这些方法可在消息队列中的不同位置处理 Windows 消息。 这些方法都有 <xref:System.Windows.Forms.Message> 参数，该参数用于封装 Windows 消息的低级别详细信息。 可以实现或重写这些方法来检查消息，然后使用此消息或将其传递给消息队列中的下一个使用者。 下表显示用于处理 Windows 窗体中所有 Windows 消息的方法。

| 方法     | 说明 |
|------------|-----------|
| <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A> | 此方法在应用程序级别截获排队的（也称为已发布的）Windows 消息。|
| <xref:System.Windows.Forms.Control.PreProcessMessage%2A>       | 此方法在 Windows 消息经过处理之前，在窗体和控件级别截获这些消息。|
| <xref:System.Windows.Forms.Control.WndProc%2A>                 | 此方法在窗体和控件级别处理 Windows 消息。|
| <xref:System.Windows.Forms.Control.DefWndProc%2A>              | 此方法在窗体和控件级别执行 Windows 消息的默认处理。 这提供了窗口的最小功能。|
| <xref:System.Windows.Forms.Control.OnNotifyMessage%2A>         | 此方法在消息经过处理之后，在窗体和控件级别截获这些消息。 必须设置 <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> 样式位才能调用此方法。|

## <a name="see-also"></a>另请参阅

- [使用鼠标事件（Windows 窗体 .NET）](events.md)
- [拖放鼠标行为概述（Windows 窗体 .NET）](drag-and-drop.md)
- [管理鼠标指针（Windows 窗体 .NET）](how-to-manage-cursor-pointer.md)
