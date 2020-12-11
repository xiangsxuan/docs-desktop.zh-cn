---
title: 处理用户输入
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: a977061ab64dbecd5782645aa6929a77803b18c9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971298"
---
# <a name="handling-user-input"></a><span data-ttu-id="da61c-102">处理用户输入</span><span class="sxs-lookup"><span data-stu-id="da61c-102">Handling User Input</span></span>

<span data-ttu-id="da61c-103">本主题介绍提供的主键盘和鼠标事件 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="da61c-103">This topic describes the main keyboard and mouse events provided by <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="da61c-104">处理事件时，控件作者应重写受保护的 `On`*EventName* 方法，而不是向事件附加委托。</span><span class="sxs-lookup"><span data-stu-id="da61c-104">When handling an event, control authors should override the protected `On`*EventName* method rather than attaching a delegate to the event.</span></span> <span data-ttu-id="da61c-105">若要查看事件，请参阅[从组件引发事件](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="da61c-105">For a review of events, see [Raising Events from a Component](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da61c-106">如果没有与某个事件相关联的数据，则会将基类的一个实例 <xref:System.EventArgs> 作为参数传递到 `On` *事件名称* 方法。</span><span class="sxs-lookup"><span data-stu-id="da61c-106">If there is no data associated with an event, an instance of the base class <xref:System.EventArgs> is passed as an argument to the `On`*EventName* method.</span></span>  
  
## <a name="keyboard-events"></a><span data-ttu-id="da61c-107">键盘事件</span><span class="sxs-lookup"><span data-stu-id="da61c-107">Keyboard Events</span></span>  

 <span data-ttu-id="da61c-108">控件可以处理的常见键盘事件为 <xref:System.Windows.Forms.Control.KeyDown> 、 <xref:System.Windows.Forms.Control.KeyPress> 和 <xref:System.Windows.Forms.Control.KeyUp> 。</span><span class="sxs-lookup"><span data-stu-id="da61c-108">The common keyboard events that your control can handle are <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, and <xref:System.Windows.Forms.Control.KeyUp>.</span></span>  
  
|<span data-ttu-id="da61c-109">事件名称</span><span class="sxs-lookup"><span data-stu-id="da61c-109">Event Name</span></span>|<span data-ttu-id="da61c-110">要重写的方法</span><span class="sxs-lookup"><span data-stu-id="da61c-110">Method to Override</span></span>|<span data-ttu-id="da61c-111">事件说明</span><span class="sxs-lookup"><span data-stu-id="da61c-111">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|<span data-ttu-id="da61c-112">仅在最初按下键时引发。</span><span class="sxs-lookup"><span data-stu-id="da61c-112">Raised only when a key is initially pressed.</span></span>|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|<span data-ttu-id="da61c-113">每次按键时引发。</span><span class="sxs-lookup"><span data-stu-id="da61c-113">Raised every time a key is pressed.</span></span> <span data-ttu-id="da61c-114">如果某个键处于关闭状态，则 <xref:System.Windows.Forms.Control.KeyPress> 按操作系统定义的重复速率引发事件。</span><span class="sxs-lookup"><span data-stu-id="da61c-114">If a key is held down, a <xref:System.Windows.Forms.Control.KeyPress> event is raised at the repeat rate defined by the operating system.</span></span>|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|<span data-ttu-id="da61c-115">在松开某个键时引发。</span><span class="sxs-lookup"><span data-stu-id="da61c-115">Raised when a key is released.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="da61c-116">处理键盘输入比重写上表中的事件要复杂得多，这超出了本主题的讨论范围。</span><span class="sxs-lookup"><span data-stu-id="da61c-116">Handling keyboard input is considerably more complex than overriding the events in the preceding table and is beyond the scope of this topic.</span></span> <span data-ttu-id="da61c-117">有关详细信息，请参阅 [Windows 窗体中的用户输入](../user-input-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="da61c-117">For more information, see [User Input in Windows Forms](../user-input-in-windows-forms.md).</span></span>  
  
## <a name="mouse-events"></a><span data-ttu-id="da61c-118">鼠标事件</span><span class="sxs-lookup"><span data-stu-id="da61c-118">Mouse Events</span></span>  

 <span data-ttu-id="da61c-119">控件可以处理的鼠标事件包括、、、、 <xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseEnter> <xref:System.Windows.Forms.Control.MouseHover> <xref:System.Windows.Forms.Control.MouseLeave> <xref:System.Windows.Forms.Control.MouseMove> 和 <xref:System.Windows.Forms.Control.MouseUp> 。</span><span class="sxs-lookup"><span data-stu-id="da61c-119">The mouse events that your control can handle are <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, and <xref:System.Windows.Forms.Control.MouseUp>.</span></span>  
  
|<span data-ttu-id="da61c-120">事件名称</span><span class="sxs-lookup"><span data-stu-id="da61c-120">Event Name</span></span>|<span data-ttu-id="da61c-121">要重写的方法</span><span class="sxs-lookup"><span data-stu-id="da61c-121">Method to Override</span></span>|<span data-ttu-id="da61c-122">事件说明</span><span class="sxs-lookup"><span data-stu-id="da61c-122">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|<span data-ttu-id="da61c-123">指针位于控件上时，按下鼠标按钮会引发该事件。</span><span class="sxs-lookup"><span data-stu-id="da61c-123">Raised when the mouse button is pressed while the pointer is over the control.</span></span>|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|<span data-ttu-id="da61c-124">指针首次进入控件区域时引发。</span><span class="sxs-lookup"><span data-stu-id="da61c-124">Raised when the pointer first enters the region of the control.</span></span>|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|<span data-ttu-id="da61c-125">指针悬停在控件上时引发。</span><span class="sxs-lookup"><span data-stu-id="da61c-125">Raised when the pointer hovers over the control.</span></span>|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|<span data-ttu-id="da61c-126">指针离开控件区域时引发。</span><span class="sxs-lookup"><span data-stu-id="da61c-126">Raised when the pointer leaves the region of the control.</span></span>|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|<span data-ttu-id="da61c-127">指针在控件区域中移动时引发。</span><span class="sxs-lookup"><span data-stu-id="da61c-127">Raised when the pointer moves in the region of the control.</span></span>|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|<span data-ttu-id="da61c-128">指针位于控件上或指针离开控件区域时，松开鼠标按钮会引发该事件。</span><span class="sxs-lookup"><span data-stu-id="da61c-128">Raised when the mouse button is released while the pointer is over the control or the pointer leaves the region of the control.</span></span>|  
  
 <span data-ttu-id="da61c-129">下面的代码片段演示了一个重写事件的示例 <xref:System.Windows.Forms.Control.MouseDown> 。</span><span class="sxs-lookup"><span data-stu-id="da61c-129">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 <span data-ttu-id="da61c-130">下面的代码片段演示了一个重写事件的示例 <xref:System.Windows.Forms.Control.MouseMove> 。</span><span class="sxs-lookup"><span data-stu-id="da61c-130">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseMove> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 <span data-ttu-id="da61c-131">下面的代码片段演示了一个重写事件的示例 <xref:System.Windows.Forms.Control.MouseUp> 。</span><span class="sxs-lookup"><span data-stu-id="da61c-131">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 <span data-ttu-id="da61c-132">有关 `FlashTrackBar` 示例的完整源代码，请参阅[如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="da61c-132">For the complete source code for the `FlashTrackBar` sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da61c-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da61c-133">See also</span></span>

- [<span data-ttu-id="da61c-134">Windows 窗体控件中的事件</span><span class="sxs-lookup"><span data-stu-id="da61c-134">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="da61c-135">定义事件</span><span class="sxs-lookup"><span data-stu-id="da61c-135">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="da61c-136">事件</span><span class="sxs-lookup"><span data-stu-id="da61c-136">Events</span></span>](/dotnet/standard/events/index)
- [<span data-ttu-id="da61c-137">Windows 窗体中的用户输入</span><span class="sxs-lookup"><span data-stu-id="da61c-137">User Input in Windows Forms</span></span>](../user-input-in-windows-forms.md)
