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
# <a name="how-to-simulate-keyboard-events-windows-forms-net"></a>如何模拟键盘事件（Windows 窗体 .NET）

Windows 窗体提供几个选项，用于以编程方式模拟键盘输入。 本文将简要阐述这些选项。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="use-sendkeys"></a>使用 SendKeys

Windows 窗体提供 <xref:System.Windows.Forms.SendKeys?displayProperty=fullName> 类，用于向活动应用程序发送击键。 可通过两种方法将击键发送到应用程序：<xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType>。 这两种方法的区别在于，在发送击键时，`SendWait` 会阻止当前线程，等待响应，而 `Send` 不会。 有关 `SendWait` 的详细信息，请参阅[将击键发送到其他应用程序](#to-send-a-keystroke-to-a-different-application)。

> [!CAUTION]
> 如果你的应用程序旨在用于全球各种键盘，使用 <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> 可能会产生不可预知的结果，应当避免。

在后台，`SendKeys` 使用较旧的 Windows 实现来发送输入，这可能会在新式 Windows 上失败，因为在新式 Windows 上应用程序不使用管理权限运行。 如果较旧的实现失败，代码会自动尝试较新的 Windows 实现来发送输入。 此外，如果 <xref:System.Windows.Forms.SendKeys> 类使用新的实现，在将击键发送到其他应用程序时，<xref:System.Windows.Forms.SendKeys.SendWait%2A> 方法不再阻止当前线程。

> [!IMPORTANT]
> 如果如论使用何种操作系统，你的应用程序均依赖于一致的行为，则可通过将以下应用程序设置添加至 app.config 文件强制执行 <xref:System.Windows.Forms.SendKeys> 类以使用新的实现。
>
> ```xml
> <appSettings>
>   <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> 若要强制执行 <xref:System.Windows.Forms.SendKeys> 类以仅使用以前的实现，请改用 `"JournalHook"` 值。

### <a name="to-send-a-keystroke-to-the-same-application"></a>若要将击键发送到相同的应用程序

调用 <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> 类或 <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> 类的 <xref:System.Windows.Forms.SendKeys> 方法。 指定的击键将由应用程序的活动控件接收。

下面的代码示例使用 `Send` 来模拟同时按 <kbd>ALT</kbd> 和 <kbd>DOWN</kbd> 键。 这些击键会导致 <xref:System.Windows.Forms.ComboBox> 控件显示其下拉列表。 此示例假定 <xref:System.Windows.Forms.Form> 具有 <xref:System.Windows.Forms.Button> 和 <xref:System.Windows.Forms.ComboBox>。

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="ShowDropDown":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="ShowDropDown":::

### <a name="to-send-a-keystroke-to-a-different-application"></a>若要将击键发送到不同的应用程序

<xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> 方法将击键发送到活动应用程序，该应用程序通常是你从其发送击键的应用程序。 若要将击键发送到其他应用程序，首先需要将其激活。 由于没有可激活其他应用程序的托管方法，所以必须使用本机 Windows 方法聚焦其他应用程序。 下面的代码示例使用平台调用来调用 `FindWindow` 和 `SetForegroundWindow` 方法以激活计算器应用程序窗口，然后调用 `Send` 向计算器应用程序发出一系列计算。

下面的代码示例使用 `Send` 模拟按下键进入 Windows 10 计算器应用程序。 它首先搜索标题为 `Calculator` 的应用程序窗口，然后将其激活。 激活后，将发送击键以计算 10 加 10。

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form2.cs" id="Calculator":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form2.vb" id="Calculator":::

## <a name="use-oneventname-methods"></a>使用 OnEventName 方法

模拟键盘事件的最简单方法是在引发事件的对象上调用方法。 大多数事件都具有调用这些事件的相应方法，以 `On` 后跟 `EventName` 的模式命名，如 `OnKeyPress`。 这种方式只适用于自定义控件或窗体内，因为这些方法受到保护且不能从控件或窗体的上下文外访问。

这些受保护的方法可用于模拟键盘事件。

- `OnKeyDown`
- `OnKeyPress`
- `OnKeyUp`

有关这些事件的详细信息，请参阅[使用键盘事件（Windows 窗体 .NET）](events.md)。

## <a name="see-also"></a>另请参阅

- [使用键盘的概述（Windows 窗体 .NET）](overview.md)
- [使用键盘事件（Windows 窗体 .NET）](events.md)
- [使用鼠标事件（Windows 窗体 .NET）](../input-mouse/events.md)
- <xref:System.Windows.Forms.SendKeys>
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
