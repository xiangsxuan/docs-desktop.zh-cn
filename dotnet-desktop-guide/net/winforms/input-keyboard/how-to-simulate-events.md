---
title: 模拟键盘事件
description: 了解如何模拟适用于 .NET 的 Windows 窗体中的键盘事件。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboards [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
ms.openlocfilehash: 5ac62ca4311461ba95a2c31876d038baffe678a2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941999"
---
# <a name="how-to-simulate-keyboard-events-windows-forms-net"></a><span data-ttu-id="1928d-103">如何模拟键盘事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="1928d-103">How to simulate keyboard events (Windows Forms .NET)</span></span>

<span data-ttu-id="1928d-104">Windows 窗体提供几个选项，用于以编程方式模拟键盘输入。</span><span class="sxs-lookup"><span data-stu-id="1928d-104">Windows Forms provides a few options for programmatically simulating keyboard input.</span></span> <span data-ttu-id="1928d-105">本文将简要阐述这些选项。</span><span class="sxs-lookup"><span data-stu-id="1928d-105">This article provides an overview of these options.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="use-sendkeys"></a><span data-ttu-id="1928d-106">使用 SendKeys</span><span class="sxs-lookup"><span data-stu-id="1928d-106">Use SendKeys</span></span>

<span data-ttu-id="1928d-107">Windows 窗体提供 <xref:System.Windows.Forms.SendKeys?displayProperty=fullName> 类，用于向活动应用程序发送击键。</span><span class="sxs-lookup"><span data-stu-id="1928d-107">Windows Forms provides the <xref:System.Windows.Forms.SendKeys?displayProperty=fullName> class for sending keystrokes to the active application.</span></span> <span data-ttu-id="1928d-108">可通过两种方法将击键发送到应用程序：<xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="1928d-108">There are two methods to send keystrokes to an application: <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1928d-109">这两种方法的区别在于，在发送击键时，`SendWait` 会阻止当前线程，等待响应，而 `Send` 不会。</span><span class="sxs-lookup"><span data-stu-id="1928d-109">The difference between the two methods is that `SendWait` blocks the current thread when the keystroke is sent, waiting for a response, while `Send` doesn't.</span></span> <span data-ttu-id="1928d-110">有关 `SendWait` 的详细信息，请参阅[将击键发送到其他应用程序](#to-send-a-keystroke-to-a-different-application)。</span><span class="sxs-lookup"><span data-stu-id="1928d-110">For more information about `SendWait`, see [To send a keystroke to a different application](#to-send-a-keystroke-to-a-different-application).</span></span>

> [!CAUTION]
> <span data-ttu-id="1928d-111">如果你的应用程序旨在用于全球各种键盘，使用 <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> 可能会产生不可预知的结果，应当避免。</span><span class="sxs-lookup"><span data-stu-id="1928d-111">If your application is intended for international use with a variety of keyboards, the use of <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> could yield unpredictable results and should be avoided.</span></span>

<span data-ttu-id="1928d-112">在后台，`SendKeys` 使用较旧的 Windows 实现来发送输入，这可能会在新式 Windows 上失败，因为在新式 Windows 上应用程序不使用管理权限运行。</span><span class="sxs-lookup"><span data-stu-id="1928d-112">Behind the scenes, `SendKeys` uses an older Windows implementation for sending input, which may fail on modern Windows where it's expected that the application isn't running with administrative rights.</span></span> <span data-ttu-id="1928d-113">如果较旧的实现失败，代码会自动尝试较新的 Windows 实现来发送输入。</span><span class="sxs-lookup"><span data-stu-id="1928d-113">If the older implementation fails, the code automatically tries the newer Windows implementation for sending input.</span></span> <span data-ttu-id="1928d-114">此外，如果 <xref:System.Windows.Forms.SendKeys> 类使用新的实现，在将击键发送到其他应用程序时，<xref:System.Windows.Forms.SendKeys.SendWait%2A> 方法不再阻止当前线程。</span><span class="sxs-lookup"><span data-stu-id="1928d-114">Additionally, when the <xref:System.Windows.Forms.SendKeys> class uses the new implementation, the <xref:System.Windows.Forms.SendKeys.SendWait%2A> method no longer blocks the current thread when sending keystrokes to another application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1928d-115">如果如论使用何种操作系统，你的应用程序均依赖于一致的行为，则可通过将以下应用程序设置添加至 app.config 文件强制执行 <xref:System.Windows.Forms.SendKeys> 类以使用新的实现。</span><span class="sxs-lookup"><span data-stu-id="1928d-115">If your application relies on consistent behavior regardless of the operating system, you can force the <xref:System.Windows.Forms.SendKeys> class to use the new implementation by adding the following application setting to your app.config file.</span></span>
>
> ```xml
> <appSettings>
>   <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> <span data-ttu-id="1928d-116">若要强制执行 <xref:System.Windows.Forms.SendKeys> 类以仅使用以前的实现，请改用 `"JournalHook"` 值。</span><span class="sxs-lookup"><span data-stu-id="1928d-116">To force the <xref:System.Windows.Forms.SendKeys> class to _only_ use the previous implementation, use the value `"JournalHook"` instead.</span></span>

### <a name="to-send-a-keystroke-to-the-same-application"></a><span data-ttu-id="1928d-117">若要将击键发送到相同的应用程序</span><span class="sxs-lookup"><span data-stu-id="1928d-117">To send a keystroke to the same application</span></span>

<span data-ttu-id="1928d-118">调用 <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> 类或 <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> 类的 <xref:System.Windows.Forms.SendKeys> 方法。</span><span class="sxs-lookup"><span data-stu-id="1928d-118">Call the <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method of the <xref:System.Windows.Forms.SendKeys> class.</span></span> <span data-ttu-id="1928d-119">指定的击键将由应用程序的活动控件接收。</span><span class="sxs-lookup"><span data-stu-id="1928d-119">The specified keystrokes will be received by the active control of the application.</span></span>

<span data-ttu-id="1928d-120">下面的代码示例使用 `Send` 来模拟同时按 <kbd>ALT</kbd> 和 <kbd>DOWN</kbd> 键。</span><span class="sxs-lookup"><span data-stu-id="1928d-120">The following code example uses `Send` to simulate pressing the <kbd>ALT</kbd> and <kbd>DOWN</kbd> keys together.</span></span> <span data-ttu-id="1928d-121">这些击键会导致 <xref:System.Windows.Forms.ComboBox> 控件显示其下拉列表。</span><span class="sxs-lookup"><span data-stu-id="1928d-121">These keystrokes cause the <xref:System.Windows.Forms.ComboBox> control to display its dropdown.</span></span> <span data-ttu-id="1928d-122">此示例假定 <xref:System.Windows.Forms.Form> 具有 <xref:System.Windows.Forms.Button> 和 <xref:System.Windows.Forms.ComboBox>。</span><span class="sxs-lookup"><span data-stu-id="1928d-122">This example assumes a <xref:System.Windows.Forms.Form> with a <xref:System.Windows.Forms.Button> and <xref:System.Windows.Forms.ComboBox>.</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="ShowDropDown":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="ShowDropDown":::

### <a name="to-send-a-keystroke-to-a-different-application"></a><span data-ttu-id="1928d-123">若要将击键发送到不同的应用程序</span><span class="sxs-lookup"><span data-stu-id="1928d-123">To send a keystroke to a different application</span></span>

<span data-ttu-id="1928d-124"><xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> 方法将击键发送到活动应用程序，该应用程序通常是你从其发送击键的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1928d-124">The <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> methods send keystrokes to the active application, which is usually the application you're sending keystrokes from.</span></span> <span data-ttu-id="1928d-125">若要将击键发送到其他应用程序，首先需要将其激活。</span><span class="sxs-lookup"><span data-stu-id="1928d-125">To send keystrokes to another application, you first need to activate it.</span></span> <span data-ttu-id="1928d-126">由于没有可激活其他应用程序的托管方法，所以必须使用本机 Windows 方法聚焦其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="1928d-126">Because there's no managed method to activate another application, you must use native Windows methods to focus the other application.</span></span> <span data-ttu-id="1928d-127">下面的代码示例使用平台调用来调用 `FindWindow` 和 `SetForegroundWindow` 方法以激活计算器应用程序窗口，然后调用 `Send` 向计算器应用程序发出一系列计算。</span><span class="sxs-lookup"><span data-stu-id="1928d-127">The following code example uses platform invoke to call the `FindWindow` and `SetForegroundWindow` methods to activate the Calculator application window, and then calls `Send` to issue a series of calculations to the Calculator application.</span></span>

<span data-ttu-id="1928d-128">下面的代码示例使用 `Send` 模拟按下键进入 Windows 10 计算器应用程序。</span><span class="sxs-lookup"><span data-stu-id="1928d-128">The following code example uses `Send` to simulate pressing keys into the Windows 10 Calculator application.</span></span> <span data-ttu-id="1928d-129">它首先搜索标题为 `Calculator` 的应用程序窗口，然后将其激活。</span><span class="sxs-lookup"><span data-stu-id="1928d-129">It first searches for an application window with title of `Calculator` and then activates it.</span></span> <span data-ttu-id="1928d-130">激活后，将发送击键以计算 10 加 10。</span><span class="sxs-lookup"><span data-stu-id="1928d-130">Once activated, the keystrokes are sent to calculate 10 plus 10.</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form2.cs" id="Calculator":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form2.vb" id="Calculator":::

## <a name="use-oneventname-methods"></a><span data-ttu-id="1928d-131">使用 OnEventName 方法</span><span class="sxs-lookup"><span data-stu-id="1928d-131">Use OnEventName methods</span></span>

<span data-ttu-id="1928d-132">模拟键盘事件的最简单方法是在引发事件的对象上调用方法。</span><span class="sxs-lookup"><span data-stu-id="1928d-132">The easiest way to simulate keyboard events is to call a method on the object that raises the event.</span></span> <span data-ttu-id="1928d-133">大多数事件都具有调用这些事件的相应方法，以 `On` 后跟 `EventName` 的模式命名，如 `OnKeyPress`。</span><span class="sxs-lookup"><span data-stu-id="1928d-133">Most events have a corresponding method that invokes them, named in the pattern of `On` followed by `EventName`, such as `OnKeyPress`.</span></span> <span data-ttu-id="1928d-134">这种方式只适用于自定义控件或窗体内，因为这些方法受到保护且不能从控件或窗体的上下文外访问。</span><span class="sxs-lookup"><span data-stu-id="1928d-134">This option is only possible within custom controls or forms, because these methods are protected and can't be accessed from outside the context of the control or form.</span></span>

<span data-ttu-id="1928d-135">这些受保护的方法可用于模拟键盘事件。</span><span class="sxs-lookup"><span data-stu-id="1928d-135">These protected methods are available to simulate keyboard events.</span></span>

- `OnKeyDown`
- `OnKeyPress`
- `OnKeyUp`

<span data-ttu-id="1928d-136">有关这些事件的详细信息，请参阅[使用键盘事件（Windows 窗体 .NET）](events.md)。</span><span class="sxs-lookup"><span data-stu-id="1928d-136">For more information about these events, see [Using keyboard events (Windows Forms .NET)](events.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1928d-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1928d-137">See also</span></span>

- [<span data-ttu-id="1928d-138">使用键盘的概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="1928d-138">Overview of using the keyboard (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="1928d-139">使用键盘事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="1928d-139">Using keyboard events (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="1928d-140">使用鼠标事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="1928d-140">Using mouse events (Windows Forms .NET)</span></span>](../input-mouse/events.md)
- <xref:System.Windows.Forms.SendKeys>
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
