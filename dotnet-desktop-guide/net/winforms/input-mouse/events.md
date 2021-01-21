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
# <a name="using-mouse-events-windows-forms-net"></a><span data-ttu-id="1dc60-105">使用鼠标事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="1dc60-105">Using mouse events (Windows Forms .NET)</span></span>

<span data-ttu-id="1dc60-106">大多数 Windows 窗体程序通过处理鼠标事件来处理鼠标输入。</span><span class="sxs-lookup"><span data-stu-id="1dc60-106">Most Windows Forms programs process mouse input by handling the mouse events.</span></span> <span data-ttu-id="1dc60-107">本文概述了鼠标事件，包括有关何时使用每个事件和为每个事件提供的数据的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1dc60-107">This article provides an overview of the mouse events, including details on when to use each event and the data that is supplied for each event.</span></span> <span data-ttu-id="1dc60-108">有关一般事件的详细信息，请参阅[事件概述（Windows 窗体 .NET）](../forms/events.md)。</span><span class="sxs-lookup"><span data-stu-id="1dc60-108">For more information about events in general, see [Events overview (Windows Forms .NET)](../forms/events.md).</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="mouse-events"></a><span data-ttu-id="1dc60-109">鼠标事件</span><span class="sxs-lookup"><span data-stu-id="1dc60-109">Mouse events</span></span>

<span data-ttu-id="1dc60-110">响应鼠标输入的主要方法是处理鼠标事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-110">The primary way to respond to mouse input is to handle mouse events.</span></span> <span data-ttu-id="1dc60-111">下表显示了鼠标事件并说明了这些事件的引发时间。</span><span class="sxs-lookup"><span data-stu-id="1dc60-111">The following table shows the mouse events and describes when they're raised.</span></span>

| <span data-ttu-id="1dc60-112">鼠标事件</span><span class="sxs-lookup"><span data-stu-id="1dc60-112">Mouse Event</span></span>                                          | <span data-ttu-id="1dc60-113">描述</span><span class="sxs-lookup"><span data-stu-id="1dc60-113">Description</span></span>                                             |
|------------------------------------------------------|---------------------------------------------------------|
| <xref:System.Windows.Forms.Control.Click>            | <span data-ttu-id="1dc60-114">此事件在释放鼠标按钮时发生，通常在 <xref:System.Windows.Forms.Control.MouseUp> 事件之前。</span><span class="sxs-lookup"><span data-stu-id="1dc60-114">This event occurs when the mouse button is released, typically before the <xref:System.Windows.Forms.Control.MouseUp> event.</span></span> <span data-ttu-id="1dc60-115">此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="1dc60-115">The handler for this event receives an argument of type <xref:System.EventArgs>.</span></span> <span data-ttu-id="1dc60-116">如果只需确定何时发生单击，处理此事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-116">Handle this event when you only need to determine when a click occurs.</span></span>                                                                             |
| <xref:System.Windows.Forms.Control.MouseClick>       | <span data-ttu-id="1dc60-117">此事件在用户使用鼠标单击控件时发生。</span><span class="sxs-lookup"><span data-stu-id="1dc60-117">This event occurs when the user clicks the control with the mouse.</span></span> <span data-ttu-id="1dc60-118">此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="1dc60-118">The handler for this event receives an argument of type <xref:System.Windows.Forms.MouseEventArgs>.</span></span> <span data-ttu-id="1dc60-119">如果需要在发生单击时获取有关鼠标的信息，处理此事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-119">Handle this event when you need to get information about the mouse when a click occurs.</span></span>                                                                                                   |
| <xref:System.Windows.Forms.Control.DoubleClick>      | <span data-ttu-id="1dc60-120">此事件在双击控件时发生。</span><span class="sxs-lookup"><span data-stu-id="1dc60-120">This event occurs when the control is double-clicked.</span></span> <span data-ttu-id="1dc60-121">此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="1dc60-121">The handler for this event receives an argument of type <xref:System.EventArgs>.</span></span> <span data-ttu-id="1dc60-122">如果只需确定何时发生双击，处理此事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-122">Handle this event when you only need to determine when a double-click occurs.</span></span>                                                                                                                                             |
| <xref:System.Windows.Forms.Control.MouseDoubleClick> | <span data-ttu-id="1dc60-123">此事件在用户使用鼠标双击控件时发生。</span><span class="sxs-lookup"><span data-stu-id="1dc60-123">This event occurs when the user double-clicks the control with the mouse.</span></span> <span data-ttu-id="1dc60-124">此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="1dc60-124">The handler for this event receives an argument of type <xref:System.Windows.Forms.MouseEventArgs>.</span></span> <span data-ttu-id="1dc60-125">如果需要在发生双击时获取有关鼠标的信息，处理此事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-125">Handle this event when you need to get information about the mouse when a double-click occurs.</span></span>                                                                                     |
| <xref:System.Windows.Forms.Control.MouseDown>        | <span data-ttu-id="1dc60-126">当鼠标指针位于控件上方并且用户按下鼠标按钮时，会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-126">This event occurs when the mouse pointer is over the control and the user presses a mouse button.</span></span> <span data-ttu-id="1dc60-127">此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="1dc60-127">The handler for this event receives an argument of type <xref:System.Windows.Forms.MouseEventArgs>.</span></span>                                                                                                                                                            |
| <xref:System.Windows.Forms.Control.MouseEnter>       | <span data-ttu-id="1dc60-128">当鼠标指针进入控件的边框或工作区时（具体取决于控件的类型），会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-128">This event occurs when the mouse pointer enters the border or client area of the control, depending on the type of control.</span></span> <span data-ttu-id="1dc60-129">此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="1dc60-129">The handler for this event receives an argument of type <xref:System.EventArgs>.</span></span>                                                                                                                                                     |
| <xref:System.Windows.Forms.Control.MouseHover>       | <span data-ttu-id="1dc60-130">此事件在鼠标指针停留在控件上时发生。</span><span class="sxs-lookup"><span data-stu-id="1dc60-130">This event occurs when the mouse pointer stops and rests over the control.</span></span> <span data-ttu-id="1dc60-131">此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="1dc60-131">The handler for this event receives an argument of type <xref:System.EventArgs>.</span></span>                                                                                                                                                                                                      |
| <xref:System.Windows.Forms.Control.MouseLeave>       | <span data-ttu-id="1dc60-132">当鼠标指针离开控件的边框或工作区时（具体取决于控件的类型），会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-132">This event occurs when the mouse pointer leaves the border or client area of the control, depending on the type of the control.</span></span> <span data-ttu-id="1dc60-133">此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="1dc60-133">The handler for this event receives an argument of type <xref:System.EventArgs>.</span></span>                                                                                                                                                 |
| <xref:System.Windows.Forms.Control.MouseMove>        | <span data-ttu-id="1dc60-134">当鼠标指针发生移动但仍位于控件上方时，会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-134">This event occurs when the mouse pointer moves while it is over a control.</span></span> <span data-ttu-id="1dc60-135">此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="1dc60-135">The handler for this event receives an argument of type <xref:System.Windows.Forms.MouseEventArgs>.</span></span>                                                                                                                                                                                   |
| <xref:System.Windows.Forms.Control.MouseUp>          | <span data-ttu-id="1dc60-136">当鼠标指针位于控件上方，并且用户释放鼠标按钮时，会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-136">This event occurs when the mouse pointer is over the control and the user releases a mouse button.</span></span> <span data-ttu-id="1dc60-137">此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="1dc60-137">The handler for this event receives an argument of type <xref:System.Windows.Forms.MouseEventArgs>.</span></span>                                                                                                                                                           |
| <xref:System.Windows.Forms.Control.MouseWheel>       | <span data-ttu-id="1dc60-138">当用户滚动鼠标滚轮并且控件有焦点时，会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-138">This event occurs when the user rotates the mouse wheel while the control has focus.</span></span> <span data-ttu-id="1dc60-139">此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。</span><span class="sxs-lookup"><span data-stu-id="1dc60-139">The handler for this event receives an argument of type <xref:System.Windows.Forms.MouseEventArgs>.</span></span> <span data-ttu-id="1dc60-140">可以使用 <xref:System.Windows.Forms.MouseEventArgs> 的 <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> 属性来确定鼠标滚动的距离。</span><span class="sxs-lookup"><span data-stu-id="1dc60-140">You can use the <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> property of <xref:System.Windows.Forms.MouseEventArgs> to determine how far the mouse has scrolled.</span></span> |

## <a name="mouse-information"></a><span data-ttu-id="1dc60-141">鼠标信息</span><span class="sxs-lookup"><span data-stu-id="1dc60-141">Mouse information</span></span>

<span data-ttu-id="1dc60-142"><xref:System.Windows.Forms.MouseEventArgs> 将发送到与单击鼠标按钮和跟踪鼠标移动相关的鼠标事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="1dc60-142">A <xref:System.Windows.Forms.MouseEventArgs> is sent to the handlers of mouse events related to clicking a mouse button and tracking mouse movements.</span></span> <span data-ttu-id="1dc60-143"><xref:System.Windows.Forms.MouseEventArgs> 提供有关当前鼠标状态的信息，包括鼠标指针在客户端坐标中的位置、按下的鼠标按钮是哪一个以及是否已经滚动鼠标滚轮。</span><span class="sxs-lookup"><span data-stu-id="1dc60-143"><xref:System.Windows.Forms.MouseEventArgs> provides information about the current state of the mouse, including the location of the mouse pointer in client coordinates, which mouse buttons are pressed, and whether the mouse wheel has scrolled.</span></span> <span data-ttu-id="1dc60-144">几个鼠标事件（例如在鼠标指针进入或离开控件边界时引发的事件）会向事件处理程序发送 <xref:System.EventArgs>，但不提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="1dc60-144">Several mouse events, such as those that are raised when the mouse pointer has entered or left the bounds of a control, send an <xref:System.EventArgs> to the event handler with no further information.</span></span>

<span data-ttu-id="1dc60-145">如果想要知道鼠标按钮当前的状态或鼠标指针的位置，并且希望避免处理鼠标事件，还可以使用 <xref:System.Windows.Forms.Control> 类的 <xref:System.Windows.Forms.Control.MouseButtons%2A> 和 <xref:System.Windows.Forms.Control.MousePosition%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="1dc60-145">If you want to know the current state of the mouse buttons or the location of the mouse pointer, and you want to avoid handling a mouse event, you can also use the <xref:System.Windows.Forms.Control.MouseButtons%2A> and <xref:System.Windows.Forms.Control.MousePosition%2A> properties of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="1dc60-146"><xref:System.Windows.Forms.Control.MouseButtons%2A> 返回有关当前按下哪些鼠标按钮的信息。</span><span class="sxs-lookup"><span data-stu-id="1dc60-146"><xref:System.Windows.Forms.Control.MouseButtons%2A> returns information about which mouse buttons are currently pressed.</span></span> <span data-ttu-id="1dc60-147"><xref:System.Windows.Forms.Control.MousePosition%2A> 返回鼠标指针的屏幕坐标，等同于由 <xref:System.Windows.Forms.Cursor.Position%2A> 返回的值。</span><span class="sxs-lookup"><span data-stu-id="1dc60-147">The <xref:System.Windows.Forms.Control.MousePosition%2A> returns the screen coordinates of the mouse pointer and is equivalent to the value returned by <xref:System.Windows.Forms.Cursor.Position%2A>.</span></span>

## <a name="converting-between-screen-and-client-coordinates"></a><span data-ttu-id="1dc60-148">在屏幕坐标和客户端坐标之间转换</span><span class="sxs-lookup"><span data-stu-id="1dc60-148">Converting Between Screen and Client Coordinates</span></span>

<span data-ttu-id="1dc60-149">由于某些鼠标位置信息以客户端坐标提供，另一些以屏幕坐标提供，因此可能需要将某个点的位置信息从一个坐标系统转换到另一个坐标系统。</span><span class="sxs-lookup"><span data-stu-id="1dc60-149">Because some mouse location information is in client coordinates and some is in screen coordinates, you may need to convert a point from one coordinate system to the other.</span></span> <span data-ttu-id="1dc60-150">通过使用 <xref:System.Windows.Forms.Control> 类提供的 <xref:System.Windows.Forms.Control.PointToClient%2A> 和 <xref:System.Windows.Forms.Control.PointToScreen%2A> 方法可轻松完成此操作。</span><span class="sxs-lookup"><span data-stu-id="1dc60-150">You can do this easily by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available on the <xref:System.Windows.Forms.Control> class.</span></span>

## <a name="standard-click-event-behavior"></a><span data-ttu-id="1dc60-151">标准 Click 事件行为</span><span class="sxs-lookup"><span data-stu-id="1dc60-151">Standard Click event behavior</span></span>

<span data-ttu-id="1dc60-152">如果想要以正确的顺序处理鼠标单击事件，则需要了解在 Windows 窗体控件中引发的单击事件的顺序。</span><span class="sxs-lookup"><span data-stu-id="1dc60-152">If you want to handle mouse click events in the proper order, you need to know the order in which click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="1dc60-153">当按下任何受支持的鼠标按钮并释放时，所有 Windows 窗体控件都将以相同的顺序引发单击事件，下表中注明的个别控件除外。</span><span class="sxs-lookup"><span data-stu-id="1dc60-153">All Windows Forms controls raise click events in the same order when any supported mouse button is pressed and released, except where noted in the following list for individual controls.</span></span> <span data-ttu-id="1dc60-154">下表显示单击鼠标按钮所引发事件的顺序：</span><span class="sxs-lookup"><span data-stu-id="1dc60-154">The following list shows the order of events raised for a single mouse-button click:</span></span>

01. <span data-ttu-id="1dc60-155"><xref:System.Windows.Forms.Control.MouseDown> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-155"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>
01. <span data-ttu-id="1dc60-156"><xref:System.Windows.Forms.Control.Click> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-156"><xref:System.Windows.Forms.Control.Click> event.</span></span>
01. <span data-ttu-id="1dc60-157"><xref:System.Windows.Forms.Control.MouseClick> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-157"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>
01. <span data-ttu-id="1dc60-158"><xref:System.Windows.Forms.Control.MouseUp> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-158"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

<span data-ttu-id="1dc60-159">下面显示双击鼠标按钮所引发事件的顺序：</span><span class="sxs-lookup"><span data-stu-id="1dc60-159">The following is the order of events raised for a double mouse-button click:</span></span>

01. <span data-ttu-id="1dc60-160"><xref:System.Windows.Forms.Control.MouseDown> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-160"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>
01. <span data-ttu-id="1dc60-161"><xref:System.Windows.Forms.Control.Click> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-161"><xref:System.Windows.Forms.Control.Click> event.</span></span>
01. <span data-ttu-id="1dc60-162"><xref:System.Windows.Forms.Control.MouseClick> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-162"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>
01. <span data-ttu-id="1dc60-163"><xref:System.Windows.Forms.Control.MouseUp> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-163"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>
01. <span data-ttu-id="1dc60-164"><xref:System.Windows.Forms.Control.MouseDown> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-164"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>
01. <span data-ttu-id="1dc60-165"><xref:System.Windows.Forms.Control.DoubleClick> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-165"><xref:System.Windows.Forms.Control.DoubleClick> event.</span></span>

    <span data-ttu-id="1dc60-166">此顺序可能不同，具体取决于相关控件的 <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> 样式位是否设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="1dc60-166">This can vary, depending on whether the control in question has the <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> style bit set to `true`.</span></span> <span data-ttu-id="1dc60-167">有关如何设置 <xref:System.Windows.Forms.ControlStyles> 位的详细信息，请参阅 <xref:System.Windows.Forms.Control.SetStyle%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1dc60-167">For more information about how to set a <xref:System.Windows.Forms.ControlStyles> bit, see the <xref:System.Windows.Forms.Control.SetStyle%2A> method.</span></span>

01. <span data-ttu-id="1dc60-168"><xref:System.Windows.Forms.Control.MouseDoubleClick> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-168"><xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span>
01. <span data-ttu-id="1dc60-169"><xref:System.Windows.Forms.Control.MouseUp> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-169"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

### <a name="individual-controls"></a><span data-ttu-id="1dc60-170">个别控件</span><span class="sxs-lookup"><span data-stu-id="1dc60-170">Individual controls</span></span>

<span data-ttu-id="1dc60-171">以下控件不符合标准鼠标单击事件行为：</span><span class="sxs-lookup"><span data-stu-id="1dc60-171">The following controls don't conform to the standard mouse click event behavior:</span></span>

- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.CheckBox>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.RadioButton>

  > [!NOTE]
  > <span data-ttu-id="1dc60-172">对于 <xref:System.Windows.Forms.ComboBox> 控件，如果用户单击编辑字段、按钮或列表中的某个项，将发生稍后详细说明的事件行为。</span><span class="sxs-lookup"><span data-stu-id="1dc60-172">For the <xref:System.Windows.Forms.ComboBox> control, the event behavior detailed later occurs if the user clicks on the edit field, the button, or on an item within the list.</span></span>

  - <span data-ttu-id="1dc60-173">**左键单击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="1dc60-173">**Left click**: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>
  - <span data-ttu-id="1dc60-174">**右键单击**：不会引发任何单击事件</span><span class="sxs-lookup"><span data-stu-id="1dc60-174">**Right click**: No click events raised</span></span>
  - <span data-ttu-id="1dc60-175">**左键双击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>；<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="1dc60-175">**Left double-click**: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>
  - <span data-ttu-id="1dc60-176">**右键双击**：不会引发任何单击事件</span><span class="sxs-lookup"><span data-stu-id="1dc60-176">**Right double-click**: No click events raised</span></span>

- <span data-ttu-id="1dc60-177"><xref:System.Windows.Forms.TextBox>、<xref:System.Windows.Forms.RichTextBox>、<xref:System.Windows.Forms.ListBox>、<xref:System.Windows.Forms.MaskedTextBox> 和 <xref:System.Windows.Forms.CheckedListBox> 控件</span><span class="sxs-lookup"><span data-stu-id="1dc60-177"><xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>, and <xref:System.Windows.Forms.CheckedListBox> controls</span></span>

  > [!NOTE]
  > <span data-ttu-id="1dc60-178">当用户单击这些控件内的任意位置时，将发生稍后详细说明的事件行为。</span><span class="sxs-lookup"><span data-stu-id="1dc60-178">The event behavior detailed later occurs when the user clicks anywhere within these controls.</span></span>

  - <span data-ttu-id="1dc60-179">**左键单击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="1dc60-179">**Left click**: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>
  - <span data-ttu-id="1dc60-180">**右键单击**：不会引发任何单击事件</span><span class="sxs-lookup"><span data-stu-id="1dc60-180">**Right click**: No click events raised</span></span>
  - <span data-ttu-id="1dc60-181">**左键双击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>、<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="1dc60-181">**Left double-click**: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>
  - <span data-ttu-id="1dc60-182">**右键双击**：不会引发任何单击事件</span><span class="sxs-lookup"><span data-stu-id="1dc60-182">**Right double-click**: No click events raised</span></span>

- <span data-ttu-id="1dc60-183"><xref:System.Windows.Forms.ListView> 控件</span><span class="sxs-lookup"><span data-stu-id="1dc60-183"><xref:System.Windows.Forms.ListView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="1dc60-184">仅当用户单击 <xref:System.Windows.Forms.ListView> 控件中的项时，才会发生稍后详细说明的事件行为。</span><span class="sxs-lookup"><span data-stu-id="1dc60-184">The event behavior detailed later occurs only when the user clicks on the items in the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="1dc60-185">单击该控件上其他任意位置不会引发任何事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-185">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="1dc60-186">除了稍后说明的事件外，还有 <xref:System.Windows.Forms.ListView.BeforeLabelEdit> 和 <xref:System.Windows.Forms.ListView.AfterLabelEdit> 事件，如果想要对 <xref:System.Windows.Forms.ListView> 控件进行验证，你可能会对这些事件感兴趣。</span><span class="sxs-lookup"><span data-stu-id="1dc60-186">In addition to the events described later, there are the <xref:System.Windows.Forms.ListView.BeforeLabelEdit> and <xref:System.Windows.Forms.ListView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.ListView> control.</span></span>

  - <span data-ttu-id="1dc60-187">**左键单击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="1dc60-187">**Left click**: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>
  - <span data-ttu-id="1dc60-188">**右键单击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="1dc60-188">**Right click**: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>
  - <span data-ttu-id="1dc60-189">**左键双击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>；<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="1dc60-189">**Left double-click**: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>
  - <span data-ttu-id="1dc60-190">**右键双击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>；<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="1dc60-190">**Right double-click**: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

- <span data-ttu-id="1dc60-191"><xref:System.Windows.Forms.TreeView> 控件</span><span class="sxs-lookup"><span data-stu-id="1dc60-191"><xref:System.Windows.Forms.TreeView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="1dc60-192">仅当用户单击 <xref:System.Windows.Forms.TreeView> 控件中的项或项的右侧时，才会发生稍后详细说明的事件行为。</span><span class="sxs-lookup"><span data-stu-id="1dc60-192">The event behavior detailed later occurs only when the user clicks on the items themselves or to the right of the items in the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="1dc60-193">单击该控件上其他任意位置不会引发任何事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-193">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="1dc60-194">除了稍后说明的事件，还有 <xref:System.Windows.Forms.TreeView.BeforeCheck>、<xref:System.Windows.Forms.TreeView.BeforeSelect>、<xref:System.Windows.Forms.TreeView.BeforeLabelEdit>、<xref:System.Windows.Forms.TreeView.AfterSelect>、<xref:System.Windows.Forms.TreeView.AfterCheck> 和 <xref:System.Windows.Forms.TreeView.AfterLabelEdit> 事件，如果想要对 <xref:System.Windows.Forms.TreeView> 控件进行验证，你可能会对这些事件感兴趣。</span><span class="sxs-lookup"><span data-stu-id="1dc60-194">In addition to those described later, there are the <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck>, and <xref:System.Windows.Forms.TreeView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.TreeView> control.</span></span>

  - <span data-ttu-id="1dc60-195">**左键单击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="1dc60-195">**Left click**: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>
  - <span data-ttu-id="1dc60-196">**右键单击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="1dc60-196">**Right click**: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>
  - <span data-ttu-id="1dc60-197">**左键双击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>；<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="1dc60-197">**Left double-click**: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>
  - <span data-ttu-id="1dc60-198">**右键双击**：<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>；<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="1dc60-198">**Right double-click**: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

## <a name="painting-behavior-of-toggle-controls"></a><span data-ttu-id="1dc60-199">切换控件的绘制行为</span><span class="sxs-lookup"><span data-stu-id="1dc60-199">Painting behavior of toggle controls</span></span>

<span data-ttu-id="1dc60-200">切换控件（如派生自 <xref:System.Windows.Forms.ButtonBase> 类的控件）具有独特的绘制行为和鼠标单击事件：</span><span class="sxs-lookup"><span data-stu-id="1dc60-200">Toggle controls, such as the controls deriving from the <xref:System.Windows.Forms.ButtonBase> class, have the following distinctive painting behavior in combination with mouse click events:</span></span>

01. <span data-ttu-id="1dc60-201">用户按下鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="1dc60-201">The user presses the mouse button.</span></span>
01. <span data-ttu-id="1dc60-202">控件以按下状态进行绘制。</span><span class="sxs-lookup"><span data-stu-id="1dc60-202">The control paints in the pressed state.</span></span>
01. <span data-ttu-id="1dc60-203">引发 <xref:System.Windows.Forms.Control.MouseDown> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-203">The <xref:System.Windows.Forms.Control.MouseDown> event is raised.</span></span>
01. <span data-ttu-id="1dc60-204">用户释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="1dc60-204">The user releases the mouse button.</span></span>
01. <span data-ttu-id="1dc60-205">控件以引发状态进行绘制。</span><span class="sxs-lookup"><span data-stu-id="1dc60-205">The control paints in the raised state.</span></span>
01. <span data-ttu-id="1dc60-206">引发 <xref:System.Windows.Forms.Control.Click> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-206">The <xref:System.Windows.Forms.Control.Click> event is raised.</span></span>
01. <span data-ttu-id="1dc60-207">引发 <xref:System.Windows.Forms.Control.MouseClick> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-207">The <xref:System.Windows.Forms.Control.MouseClick> event is raised.</span></span>
01. <span data-ttu-id="1dc60-208">引发 <xref:System.Windows.Forms.Control.MouseUp> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-208">The <xref:System.Windows.Forms.Control.MouseUp> event is raised.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1dc60-209">如果用户在鼠标按钮处于按下状态时将指针移出切换控件（例如在鼠标按下时将鼠标从 <xref:System.Windows.Forms.Button> 控件移出），那么切换控件将以引发状态进行绘制，并且只发生 <xref:System.Windows.Forms.Control.MouseUp> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-209">If the user moves the pointer out of the toggle control while the mouse button is down (such as moving the mouse off the <xref:System.Windows.Forms.Button> control while it is pressed), the toggle control will paint in the raised state and only the <xref:System.Windows.Forms.Control.MouseUp> event occurs.</span></span> <span data-ttu-id="1dc60-210">在这种情况下，将不会发生 <xref:System.Windows.Forms.Control.Click> 或 <xref:System.Windows.Forms.Control.MouseClick> 事件。</span><span class="sxs-lookup"><span data-stu-id="1dc60-210">The <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> events will not occur in this situation.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dc60-211">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1dc60-211">See also</span></span>

- [<span data-ttu-id="1dc60-212">使用鼠标的概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="1dc60-212">Overview of using the mouse (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="1dc60-213">管理鼠标指针（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="1dc60-213">Manage mouse pointers (Windows Forms .NET)</span></span>](how-to-manage-cursor-pointer.md)
- [<span data-ttu-id="1dc60-214">如何模拟鼠标事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="1dc60-214">How to simulate mouse events (Windows Forms .NET)</span></span>](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>