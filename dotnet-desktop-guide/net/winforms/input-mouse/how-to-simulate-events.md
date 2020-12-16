---
title: 如何模拟鼠标事件
description: 了解如何模拟适用于 .NET 的 Windows 窗体中的鼠标事件。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
ms.openlocfilehash: 443611163d33a266b3c49d03df13131c994b0bd3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941971"
---
# <a name="how-to-simulate-mouse-events-windows-forms-net"></a><span data-ttu-id="fea02-103">如何模拟鼠标事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="fea02-103">How to simulate mouse events (Windows Forms .NET)</span></span>

<span data-ttu-id="fea02-104">在 Windows 窗体中模拟鼠标事件不像模拟键盘事件那样直接。</span><span class="sxs-lookup"><span data-stu-id="fea02-104">Simulating mouse events in Windows Forms isn't as straight forward as simulating keyboard events.</span></span> <span data-ttu-id="fea02-105">Windows 窗体不提供帮助程序类来移动鼠标和调用鼠标单击操作。</span><span class="sxs-lookup"><span data-stu-id="fea02-105">Windows Forms doesn't provide a helper class to move the mouse and invoke mouse-click actions.</span></span> <span data-ttu-id="fea02-106">控制鼠标的唯一方式是使用本机 Windows 方法。</span><span class="sxs-lookup"><span data-stu-id="fea02-106">The only option for controlling the mouse is to use native Windows methods.</span></span> <span data-ttu-id="fea02-107">如果你使用的是自定义控件或窗体，可模拟鼠标事件，但不能直接控制鼠标。</span><span class="sxs-lookup"><span data-stu-id="fea02-107">If you're working with a custom control or a form, you can simulate a mouse event, but you can't directly control the mouse.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="events"></a><span data-ttu-id="fea02-108">事件</span><span class="sxs-lookup"><span data-stu-id="fea02-108">Events</span></span>

<span data-ttu-id="fea02-109">大多数事件都具有调用这些事件的相应方法，以 `On` 后跟 `EventName` 的模式命名，如 `OnMouseMove`。</span><span class="sxs-lookup"><span data-stu-id="fea02-109">Most events have a corresponding method that invokes them, named in the pattern of `On` followed by `EventName`, such as `OnMouseMove`.</span></span> <span data-ttu-id="fea02-110">这种方式只适用于自定义控件或窗体内，因为这些方法受到保护且不能从控件或窗体的上下文外访问。</span><span class="sxs-lookup"><span data-stu-id="fea02-110">This option is only possible within custom controls or forms, because these methods are protected and can't be accessed from outside the context of the control or form.</span></span> <span data-ttu-id="fea02-111">使用方法（如 `OnMouseMove`）的缺点在于，它不会实际控制鼠标或与控件交互，而只是引发关联的事件。</span><span class="sxs-lookup"><span data-stu-id="fea02-111">The disadvantage to using a method such as `OnMouseMove` is that it doesn't actually control the mouse or interact with the control, it simply raises the associated event.</span></span> <span data-ttu-id="fea02-112">例如，如果你想模拟将鼠标悬停在 <xref:System.Windows.Forms.ListBox> 中的某一项上，则 `OnMouseMove` 和 `ListBox` 不会以光标下的突出显示的项的方式直观地作出反应。</span><span class="sxs-lookup"><span data-stu-id="fea02-112">For example, if you wanted to simulate hovering over an item in a <xref:System.Windows.Forms.ListBox>, `OnMouseMove` and the `ListBox` doesn't visually react with a highlighted item under the cursor.</span></span>

<span data-ttu-id="fea02-113">这些受保护的方法可用于模拟鼠标事件。</span><span class="sxs-lookup"><span data-stu-id="fea02-113">These protected methods are available to simulate mouse events.</span></span>

- `OnMouseDown`
- `OnMouseEnter`
- `OnMouseHover`
- `OnMouseLeave`
- `OnMouseMove`
- `OnMouseUp`
- `OnMouseWheel`
- `OnMouseClick`
- `OnMouseDoubleClick`

<span data-ttu-id="fea02-114">有关这些事件的详细信息，请参阅[使用鼠标事件（Windows 窗体 .NET）](events.md)</span><span class="sxs-lookup"><span data-stu-id="fea02-114">For more information about these events, see [Using mouse events (Windows Forms .NET)](events.md)</span></span>

## <a name="invoke-a-click"></a><span data-ttu-id="fea02-115">调用单击</span><span class="sxs-lookup"><span data-stu-id="fea02-115">Invoke a click</span></span>

<span data-ttu-id="fea02-116">考虑到大多数控件在单击时会执行某些操作（如调用用户代码的按钮或更改其选中状态的复选框），Windows 窗体提供一种简单的方法来触发单击操作。</span><span class="sxs-lookup"><span data-stu-id="fea02-116">Considering most controls do something when clicked, like a button calling user code, or checkbox change its checked state, Windows Forms provides an easy way to trigger the click.</span></span> <span data-ttu-id="fea02-117">某些控件（如组合框）在单击时不会执行任何特殊操作，并且模拟单击不会对控件产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="fea02-117">Some controls, such as a combobox, don't do anything special when clicked and simulating a click has no effect on the control.</span></span>

### <a name="performclick"></a><span data-ttu-id="fea02-118">PerformClick</span><span class="sxs-lookup"><span data-stu-id="fea02-118">PerformClick</span></span>

<span data-ttu-id="fea02-119"><xref:System.Windows.Forms.IButtonControl?displayProperty=nameWithType> 接口提供模拟单击控件的 <xref:System.Windows.Forms.IButtonControl.PerformClick%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="fea02-119">The <xref:System.Windows.Forms.IButtonControl?displayProperty=nameWithType> interface provides the <xref:System.Windows.Forms.IButtonControl.PerformClick%2A> method which simulates a click on the control.</span></span> <span data-ttu-id="fea02-120"><xref:System.Windows.Forms.Button?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.LinkLabel?displayProperty=nameWithType> 控件都实现此接口。</span><span class="sxs-lookup"><span data-stu-id="fea02-120">Both the <xref:System.Windows.Forms.Button?displayProperty=nameWithType> and <xref:System.Windows.Forms.LinkLabel?displayProperty=nameWithType> controls implement this interface.</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="PerformClick":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="PerformClick":::

### <a name="invokeclick"></a><span data-ttu-id="fea02-121">InvokeClick</span><span class="sxs-lookup"><span data-stu-id="fea02-121">InvokeClick</span></span>

<span data-ttu-id="fea02-122">对于窗体的自定义控件，使用 <xref:System.Windows.Forms.Control.InvokeOnClick%2A> 方法模拟鼠标单击。</span><span class="sxs-lookup"><span data-stu-id="fea02-122">With a form a custom control, use the <xref:System.Windows.Forms.Control.InvokeOnClick%2A> method to simulate a mouse click.</span></span> <span data-ttu-id="fea02-123">这是一个受保护的方法，只能从窗体或派生的自定义控件中调用。</span><span class="sxs-lookup"><span data-stu-id="fea02-123">This is a protected method that can only be called from within the form or a derived custom control.</span></span>

<span data-ttu-id="fea02-124">例如，以下代码从 `button1` 单击复选框。</span><span class="sxs-lookup"><span data-stu-id="fea02-124">For example, the following code clicks a checkbox from `button1`.</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="ClickCheckbox":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="ClickCheckbox":::

## <a name="use-native-windows-methods"></a><span data-ttu-id="fea02-125">使用本机 Windows 方法</span><span class="sxs-lookup"><span data-stu-id="fea02-125">Use native Windows methods</span></span>

<span data-ttu-id="fea02-126">Windows 提供了一些方法，你可调用这些方法来模拟鼠标移动和单击，如 [`User32.dll SendInput`](/windows/win32/api/winuser/nf-winuser-sendinput) 和 [`User32.dll SetCursorPos`](/windows/win32/api/winuser/nf-winuser-setcursorpos)。</span><span class="sxs-lookup"><span data-stu-id="fea02-126">Windows provides methods you can call to simulate mouse movements and clicks such as [`User32.dll SendInput`](/windows/win32/api/winuser/nf-winuser-sendinput) and [`User32.dll SetCursorPos`](/windows/win32/api/winuser/nf-winuser-setcursorpos).</span></span> <span data-ttu-id="fea02-127">下面的示例将鼠标光标移动到控件的中心：</span><span class="sxs-lookup"><span data-stu-id="fea02-127">The following example moves the mouse cursor to the center of a control:</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form2.cs" id="MoveCursor":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form2.vb" id="MoveCursor":::

## <a name="see-also"></a><span data-ttu-id="fea02-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fea02-128">See also</span></span>

- [<span data-ttu-id="fea02-129">使用鼠标的概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="fea02-129">Overview of using the mouse (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="fea02-130">使用鼠标事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="fea02-130">Using mouse events (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="fea02-131">如何区分单击和双击（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="fea02-131">How to distinguish between clicks and double-clicks (Windows Forms .NET)</span></span>](how-to-distinguish-between-clicks-and-double-clicks.md)
- [<span data-ttu-id="fea02-132">管理鼠标指针（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="fea02-132">Manage mouse pointers (Windows Forms .NET)</span></span>](how-to-manage-cursor-pointer.md)
