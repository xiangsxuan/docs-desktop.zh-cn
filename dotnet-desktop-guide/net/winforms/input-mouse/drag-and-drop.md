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
# <a name="drag-and-drop-mouse-behavior-overview-windows-forms-net"></a><span data-ttu-id="ccd68-103">拖放鼠标行为概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="ccd68-103">Drag-and-drop mouse behavior overview (Windows Forms .NET)</span></span>

<span data-ttu-id="ccd68-104">Windows 窗体包含一组实现拖放行为的方法、事件和类。</span><span class="sxs-lookup"><span data-stu-id="ccd68-104">Windows Forms includes a set of methods, events, and classes that implement drag-and-drop behavior.</span></span> <span data-ttu-id="ccd68-105">本主题概述了 Windows 窗体对拖放功能的支持。</span><span class="sxs-lookup"><span data-stu-id="ccd68-105">This topic provides an overview of the drag-and-drop support in Windows Forms.</span></span><!-- TODO Also see [Drag-and-Drop Operations and Clipboard Support](./advanced/drag-and-drop-operations-and-clipboard-support.md).-->

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="drag-and-drop-events"></a><span data-ttu-id="ccd68-106">拖放事件</span><span class="sxs-lookup"><span data-stu-id="ccd68-106">Drag-and-drop events</span></span>

<span data-ttu-id="ccd68-107">拖放操作中有两类事件：一类是拖放操作的当前目标上发生的事件，一类是拖放操作的源上发生的事件。</span><span class="sxs-lookup"><span data-stu-id="ccd68-107">There are two categories of events in a drag and drop operation: events that occur on the current target of the drag-and-drop operation, and events that occur on the source of the drag and drop operation.</span></span> <span data-ttu-id="ccd68-108">若要执行拖放操作，必须处理这些事件。</span><span class="sxs-lookup"><span data-stu-id="ccd68-108">To perform drag-and-drop operations, you must handle these events.</span></span> <span data-ttu-id="ccd68-109">通过使用这些事件的事件参数中的可用信息，可以轻松地实现拖放操作。</span><span class="sxs-lookup"><span data-stu-id="ccd68-109">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>

## <a name="events-on-the-current-drop-target"></a><span data-ttu-id="ccd68-110">当前拖放目标上的事件</span><span class="sxs-lookup"><span data-stu-id="ccd68-110">Events on the current drop target</span></span>

<span data-ttu-id="ccd68-111">下表显示在拖放操作的当前目标上发生的事件。</span><span class="sxs-lookup"><span data-stu-id="ccd68-111">The following table shows the events that occur on the current target of a drag-and-drop operation.</span></span>

| <span data-ttu-id="ccd68-112">鼠标事件</span><span class="sxs-lookup"><span data-stu-id="ccd68-112">Mouse Event</span></span>                                   | <span data-ttu-id="ccd68-113">描述</span><span class="sxs-lookup"><span data-stu-id="ccd68-113">Description</span></span>                                                                                                                                                                                            |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <xref:System.Windows.Forms.Control.DragEnter> | <span data-ttu-id="ccd68-114">将对象拖入控件的边界时此事件发生。</span><span class="sxs-lookup"><span data-stu-id="ccd68-114">This event occurs when an object is dragged into the control's bounds.</span></span> <span data-ttu-id="ccd68-115">此事件的处理程序接收类型为 <xref:System.Windows.Forms.DragEventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="ccd68-115">The handler for this event receives an argument of type <xref:System.Windows.Forms.DragEventArgs>.</span></span>                              |
| <xref:System.Windows.Forms.Control.DragOver>  | <span data-ttu-id="ccd68-116">在鼠标指针位于控件的边界内时如果拖动对象则此事件发生。</span><span class="sxs-lookup"><span data-stu-id="ccd68-116">This event occurs when an object is dragged while the mouse pointer is within the control's bounds.</span></span> <span data-ttu-id="ccd68-117">此事件的处理程序接收类型为 <xref:System.Windows.Forms.DragEventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="ccd68-117">The handler for this event receives an argument of type <xref:System.Windows.Forms.DragEventArgs>.</span></span> |
| <xref:System.Windows.Forms.Control.DragDrop>  | <span data-ttu-id="ccd68-118">拖放操作完成时此事件发生。</span><span class="sxs-lookup"><span data-stu-id="ccd68-118">This event occurs when a drag-and-drop operation is completed.</span></span> <span data-ttu-id="ccd68-119">此事件的处理程序接收类型为 <xref:System.Windows.Forms.DragEventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="ccd68-119">The handler for this event receives an argument of type <xref:System.Windows.Forms.DragEventArgs>.</span></span>                                      |
| <xref:System.Windows.Forms.Control.DragLeave> | <span data-ttu-id="ccd68-120">将对象拖出控件的边界时此事件发生。</span><span class="sxs-lookup"><span data-stu-id="ccd68-120">This event occurs when an object is dragged out of the control's bounds.</span></span> <span data-ttu-id="ccd68-121">此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="ccd68-121">The handler for this event receives an argument of type <xref:System.EventArgs>.</span></span>                                              |

<span data-ttu-id="ccd68-122"><xref:System.Windows.Forms.DragEventArgs> 类提供鼠标指针的位置、鼠标按钮和键盘修改键的当前状态、正在拖动的数据以及 <xref:System.Windows.Forms.DragDropEffects> 值（指定拖动事件的源所允许的操作以及操作的目标放置效果）。</span><span class="sxs-lookup"><span data-stu-id="ccd68-122">The <xref:System.Windows.Forms.DragEventArgs> class provides the location of the mouse pointer, the current state of the mouse buttons and modifier keys of the keyboard, the data being dragged, and <xref:System.Windows.Forms.DragDropEffects> values that specify the operations allowed by the source of the drag event and the target drop effect for the operation.</span></span>

## <a name="events-on-the-drop-source"></a><span data-ttu-id="ccd68-123">放置源上的事件</span><span class="sxs-lookup"><span data-stu-id="ccd68-123">Events on the drop source</span></span>

<span data-ttu-id="ccd68-124">下表显示在拖放操作的源上发生的事件。</span><span class="sxs-lookup"><span data-stu-id="ccd68-124">The following table shows the events that occur on the source of the drag-and-drop operation.</span></span>

|<span data-ttu-id="ccd68-125">鼠标事件</span><span class="sxs-lookup"><span data-stu-id="ccd68-125">Mouse Event</span></span>|<span data-ttu-id="ccd68-126">描述</span><span class="sxs-lookup"><span data-stu-id="ccd68-126">Description</span></span>|
|-----------------|-----------------|
|<xref:System.Windows.Forms.Control.GiveFeedback>|<span data-ttu-id="ccd68-127">此事件在执行拖动操作期间发生。</span><span class="sxs-lookup"><span data-stu-id="ccd68-127">This event occurs during a drag operation.</span></span> <span data-ttu-id="ccd68-128">借助此事件，可向用户提供可视提示（例如更改鼠标指针），通知拖放操作正在发生。</span><span class="sxs-lookup"><span data-stu-id="ccd68-128">It provides an opportunity to give a visual cue to the user that the drag-and-drop operation is occurring, such as changing the mouse pointer.</span></span> <span data-ttu-id="ccd68-129">此事件的处理程序接收类型为 <xref:System.Windows.Forms.GiveFeedbackEventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="ccd68-129">The handler for this event receives an argument of type <xref:System.Windows.Forms.GiveFeedbackEventArgs>.</span></span>|
|<xref:System.Windows.Forms.Control.QueryContinueDrag>|<span data-ttu-id="ccd68-130">此事件在拖放操作期间引发，并使拖动源可以确定是否应取消拖放操作。</span><span class="sxs-lookup"><span data-stu-id="ccd68-130">This event is raised during a drag-and-drop operation and enables the drag source to determine whether the drag-and-drop operation should be canceled.</span></span> <span data-ttu-id="ccd68-131">此事件的处理程序接收类型为 <xref:System.Windows.Forms.QueryContinueDragEventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="ccd68-131">The handler for this event receives an argument of type <xref:System.Windows.Forms.QueryContinueDragEventArgs>.</span></span>|

<span data-ttu-id="ccd68-132"><xref:System.Windows.Forms.QueryContinueDragEventArgs> 类提供鼠标按钮和键盘修改键的当前状态、指定是否按 ESC 键的值以及 <xref:System.Windows.Forms.DragAction> 值（可设置为指定是否应继续拖放操作）。</span><span class="sxs-lookup"><span data-stu-id="ccd68-132">The <xref:System.Windows.Forms.QueryContinueDragEventArgs> class provides the current state of the mouse buttons and modifier keys of the keyboard, a value specifying whether the ESC key was pressed, and a <xref:System.Windows.Forms.DragAction> value that can be set to specify whether the drag-and-drop operation should continue.</span></span>

## <a name="performing-drag-and-drop"></a><span data-ttu-id="ccd68-133">执行拖放操作</span><span class="sxs-lookup"><span data-stu-id="ccd68-133">Performing drag-and-drop</span></span>

<span data-ttu-id="ccd68-134">拖放操作始终涉及两个组件 - 放置源和拖放目标 。</span><span class="sxs-lookup"><span data-stu-id="ccd68-134">Drag-and-drop operations always involve two components, the **drag source** and the **drop target**.</span></span> <span data-ttu-id="ccd68-135">若要启动拖放操作，请指定一个控件作为源，并处理 <xref:System.Windows.Forms.Control.MouseDown> 事件。</span><span class="sxs-lookup"><span data-stu-id="ccd68-135">To start a drag-and-drop operation, designate a control as the source and handle the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span> <span data-ttu-id="ccd68-136">在事件处理程序中，调用 <xref:System.Windows.DragDrop.DoDragDrop%2A> 方法，该方法提供与放置关联的数据和 <xref:System.Windows.DragDropEffects> 值。</span><span class="sxs-lookup"><span data-stu-id="ccd68-136">In the event handler, call the <xref:System.Windows.DragDrop.DoDragDrop%2A> method providing the data associated with the drop and the a <xref:System.Windows.DragDropEffects> value.</span></span>

<span data-ttu-id="ccd68-137">将目标控件的 <xref:System.Windows.Forms.Control.AllowDrop> 属性设置为 `true`，以允许该控件接受拖放操作。</span><span class="sxs-lookup"><span data-stu-id="ccd68-137">Set the target control's <xref:System.Windows.Forms.Control.AllowDrop> property set to `true` to allow that control to accept a drag-and-drop operation.</span></span> <span data-ttu-id="ccd68-138">目标处理两个事件，第一个是响应控件上的拖动的事件，如 <xref:System.Windows.Forms.Control.DragOver>。</span><span class="sxs-lookup"><span data-stu-id="ccd68-138">The target handles two events, first an event in response to the drag being over the control, such as <xref:System.Windows.Forms.Control.DragOver>.</span></span> <span data-ttu-id="ccd68-139">第二个事件是放置操作本身 - <xref:System.Windows.Forms.Control.DragDrop>。</span><span class="sxs-lookup"><span data-stu-id="ccd68-139">And a second event which is the drop action itself, <xref:System.Windows.Forms.Control.DragDrop>.</span></span>

<span data-ttu-id="ccd68-140">下面的示例演示一个从 <xref:System.Windows.Forms.Label> 控件到 <xref:System.Windows.Forms.TextBox> 的拖动操作。</span><span class="sxs-lookup"><span data-stu-id="ccd68-140">The following example demonstrates a drag from a <xref:System.Windows.Forms.Label> control to a <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="ccd68-141">拖动操作完成后，`TextBox` 通过将标签的文本分配给其自身来做出响应。</span><span class="sxs-lookup"><span data-stu-id="ccd68-141">When the drag is completed, the `TextBox` responds by assigning the label's text to itself.</span></span>

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

<span data-ttu-id="ccd68-142">有关拖动效果的详细信息，请参阅<xref:System.Windows.Forms.DragEventArgs.Data%2A> 和 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>。</span><span class="sxs-lookup"><span data-stu-id="ccd68-142">For more information about the drag effects, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccd68-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ccd68-143">See also</span></span>

- [<span data-ttu-id="ccd68-144">使用鼠标的概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="ccd68-144">Overview of using the mouse (Windows Forms .NET)</span></span>](overview.md)
- <xref:System.Windows.Forms.Control.DragDrop?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragEnter?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragLeave?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragOver?displayProperty=nameWithType>
