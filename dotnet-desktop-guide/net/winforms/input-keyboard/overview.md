---
title: 键盘输入概述
description: 了解 .NET 的 Windows 窗体中键盘输入的工作原理。 键盘事件由窗体和控件引发，并表示向下、已按下或向上的键。
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, keyboard input
- keyboard [Windows Forms], input
ms.openlocfilehash: dbebc89b4ec9e5824f7a1b44a75fe313c4ab683b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941912"
---
# <a name="overview-of-using-the-keyboard-windows-forms-net"></a>使用键盘的概述（Windows 窗体 .NET）

在 Windows 窗体中，用户输入以 [Windows 消息](/windows/win32/winmsg/about-messages-and-message-queues)的形式发送到应用程序。 一系列可重写的方法在应用程序、窗体和控件级别处理这些消息。 当这些方法收到键盘消息时，它们会引发可处理的事件以获取有关键盘输入的信息。 在许多情况下，Windows 窗体应用程序只需通过处理这些事件即可处理所有用户输入。 在其他情况下，应用程序可能需要重写处理消息的方法之一，以便在应用程序、窗体或控件接收特定消息之前截获该消息。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="keyboard-events"></a>键盘事件

所有 Windows 窗体控件都将继承与鼠标和键盘输入相关的一组事件。 例如，控件可以处理 <xref:System.Windows.Forms.Control.KeyPress> 事件以确定所按下的键的字符代码。 有关详细信息，请参阅[使用键盘事件](events.md)。

## <a name="methods-that-process-user-input-messages"></a>处理用户输入消息的方法

窗体和控件可以访问 <xref:System.Windows.Forms.IMessageFilter> 接口和一组可重写的方法，这些方法可在消息队列中的不同位置处理 Windows 消息。 这些方法都有 <xref:System.Windows.Forms.Message> 参数，该参数用于封装 Windows 消息的低级别详细信息。 可以实现或重写这些方法来检查消息，然后使用此消息或将其传递给消息队列中的下一个使用者。 下表显示用于处理 Windows 窗体中所有 Windows 消息的方法。

| 方法     | 说明 |
|------------|-----------|
| <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A> | 此方法在应用程序级别截获排队的（也称为已发布的）Windows 消息。|
| <xref:System.Windows.Forms.Control.PreProcessMessage%2A>       | 此方法在 Windows 消息经过处理之前，在窗体和控件级别截获这些消息。|
| <xref:System.Windows.Forms.Control.WndProc%2A>                 | 此方法在窗体和控件级别处理 Windows 消息。|
| <xref:System.Windows.Forms.Control.DefWndProc%2A>              | 此方法在窗体和控件级别执行 Windows 消息的默认处理。 这提供了窗口的最小功能。|
| <xref:System.Windows.Forms.Control.OnNotifyMessage%2A>         | 此方法在消息经过处理之后，在窗体和控件级别截获这些消息。 必须设置 <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> 样式位才能调用此方法。|

键盘和鼠标消息也由其他一组特定于这些类型消息的可重写方法进行处理。 有关详细信息，请参阅[键的预处理](#preprocessing-keys)部分。 <!-- TODO mouse link -->.

## <a name="types-of-keys"></a>密钥类型

Windows 窗体将键盘输入标识为由按位 <xref:System.Windows.Forms.Keys> 枚举表示的虚拟键代码。 使用 <xref:System.Windows.Forms.Keys> 枚举，可以组合一系列按键以生成单个值。 这些值与 WM_KEYDOWN 和 WM_SYSKEYDOWN Windows 消息所附带的值相对应 。 可以通过处理 <xref:System.Windows.Forms.Control.KeyDown> 或 <xref:System.Windows.Forms.Control.KeyUp> 事件来检测大多数物理按键。 字符键是 <xref:System.Windows.Forms.Keys> 枚举的子集，它们与 WM_CHAR 和 WM_SYSCHAR Windows 消息所附带的值相对应 。 如果通过组合按键得到一个字符，则可以通过处理 <xref:System.Windows.Forms.Control.KeyPress> 事件来检测该字符。 <!-- TODO is this still valid with .NET Core/5 ?? Alternatively, you can use <xref:Microsoft.VisualBasic.Devices.Keyboard>, exposed by Visual Basic programming interface, to discover which keys were pressed and send keys. For more information, see [Accessing the Keyboard](../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md).-->

## <a name="order-of-keyboard-events"></a>键盘事件的顺序

正如上面列出的那样，在一个控件上可能出现三个与键盘相关的事件。 以下顺序是发生这些事件的常规顺序：

01. 用户按“a”键，该键将被预处理和调度，并且会发生 <xref:System.Windows.Forms.Control.KeyDown> 事件。
01. 用户按住“a”键，该键将被预处理和调度，并且会发生 <xref:System.Windows.Forms.Control.KeyPress> 事件。
    当用户按住某个键时，此事件会发生多次。
01. 用户松开“a”键，该键将被预处理和调度，并且会发生 <xref:System.Windows.Forms.Control.KeyUp> 事件。

## <a name="preprocessing-keys"></a>键的预处理

与其他消息一样，键盘消息也是在窗体或控件的 <xref:System.Windows.Forms.Control.WndProc%2A> 方法中处理的。 但是，在处理键盘消息之前，<xref:System.Windows.Forms.Control.PreProcessMessage%2A> 方法会调用一个或多个方法，这些方法可被重写以处理特殊的字符键和物理按键。 可以重写这些方法，以便在控件处理消息之前检测并筛选某些按键。 下表按照方法出现的顺序列出了正在执行的操作以及所出现的相关方法。

### <a name="preprocessing-for-a-keydown-event"></a>KeyDown 事件的预处理

|操作|相关方法|说明|
|------------|--------------------|-----------|
|检查命令键（如快捷键或菜单快捷键）。|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|此方法处理命令键，命令键的优先级高于常规键。 如果此方法返回 `true`，则不调度键消息，而且不发生键事件。 如果它返回 `false`，则调用 <xref:System.Windows.Forms.Control.IsInputKey%2A>。|
|检查该键是否为需要预处理的特殊键，或者是否为应引发 <xref:System.Windows.Forms.Control.KeyDown> 事件并且被调度到某个控件的普通字符键。|<xref:System.Windows.Forms.Control.IsInputKey%2A>|如果此方法返回 `true`，则表示该控件为常规字符，并且会引发 <xref:System.Windows.Forms.Control.KeyDown> 事件。 如果返回 `false`，则调用 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>。 **注意：** 若要确保控件获取某个键或组合键，可以处理 <xref:System.Windows.Forms.Control.PreviewKeyDown> 事件，并针对所需的键或组合键将 <xref:System.Windows.Forms.PreviewKeyDownEventArgs> 的 <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> 设置为 `true`。|
|检查该键是否为导航键（Esc、Tab、回车键或箭头键）。|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|此方法处理在控件内实现特殊功能（如在控件与其父级之间切换焦点）的物理按键。 如果中间控件不处理该键，则会调用父控件的 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>，直至层次结构中的最顶端控件。 如果此方法返回 `true`，则完成预处理，而且不生成按键事件。 如果它返回 `false`，则会发生 <xref:System.Windows.Forms.Control.KeyDown> 事件。|

### <a name="preprocessing-for-a-keypress-event"></a>KeyPress 事件的预处理

|操作|相关方法|说明|
|------------|--------------------|-----------|
|检查该键是否为控件应当处理的普通字符|<xref:System.Windows.Forms.Control.IsInputChar%2A>|如果该字符是普通字符，则此方法返回 `true`，并且引发 <xref:System.Windows.Forms.Control.KeyPress> 事件，而且不再进行预处理。 否则，将调用 <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>。|
|检查该字符是否为助记键（如按钮上的“确定(&O)”）|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|与 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> 类似，将调用此方法，直至控件层次结构的顶端。 如果控件是容器控件，此方法会通过调用控件及其子控件的 <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> 来检查助记键。 如果 <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> 返回 `true`，则不会发生 <xref:System.Windows.Forms.Control.KeyPress> 事件。|

## <a name="processing-keyboard-messages"></a>处理键盘消息

键盘消息在到达窗体或控件的 <xref:System.Windows.Forms.Control.WndProc%2A> 方法之后，它们会由一组可重写的方法来处理。 其中的每种方法都返回一个 <xref:System.Boolean> 值，该值指定控件是否已处理和使用了键盘消息。 如果其中的某种方法返回 `true`，则键盘消息被视为已处理，而且它不传递到控件的基控件或父控件进行进一步处理。 否则，消息停留在消息队列中，而且可能会在控件的基控件或父控件的其他方法中进行处理。 下表显示用来处理键盘消息的方法。

|方法|说明|
|------------|-----------|
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|此方法处理由控件的 <xref:System.Windows.Forms.Control.WndProc%2A> 方法接收的所有键盘消息。|
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|此方法将键盘消息发送到控件的父控件。 如果 <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A> 返回 `true`，则不生成键事件，否则将调用 <xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>。|
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|此方法会根据需要引发 <xref:System.Windows.Forms.Control.KeyDown>、<xref:System.Windows.Forms.Control.KeyPress> 和 <xref:System.Windows.Forms.Control.KeyUp> 事件。|

## <a name="overriding-keyboard-methods"></a>重写键盘方法

在预处理和处理键盘消息时，可以使用许多方法进行重写；但是，这些方法有好有坏。 下表显示可能需要完成的任务以及重写键盘方法的最佳方式。 有关重写方法的详细信息，请参阅[继承（C# 编程指南）](/dotnet/csharp/programming-guide/classes-and-structs/inheritance.md#abstract-and-virtual-methods)或[继承 (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md#overriding-properties-and-methods-in-derived-classes)

|任务|方法|
|----------|------------|
|截获导航键并引发 <xref:System.Windows.Forms.Control.KeyDown> 事件。 例如，希望在文本框中处理 Tab 键和回车键。|替代 <xref:System.Windows.Forms.Control.IsInputKey%2A>。 **注意：** 还可以处理 <xref:System.Windows.Forms.Control.PreviewKeyDown> 事件，并针对所需的键或组合键将 <xref:System.Windows.Forms.PreviewKeyDownEventArgs> 的 <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> 设置为 `true`。|
|在控件上执行特殊的输入或导航处理。 例如，你可能希望在列表控件中使用箭头键更改选定项。|重写 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|
|截获导航键并引发 <xref:System.Windows.Forms.Control.KeyPress> 事件。 例如，你希望在数字调整框控件中，多次按箭头键来加快项的调整进度。|替代 <xref:System.Windows.Forms.Control.IsInputChar%2A>。|
|在 <xref:System.Windows.Forms.Control.KeyPress> 事件期间执行特殊的输入或导航处理。 例如，在列表控件中，按住“r”键将跳到以字母 r 开头的项并在这些项间切换。|重写 <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|
|执行自定义的助记键处理；例如，你希望处理所有者描述的、包含在工具栏中的按钮上的助记键。|替代 <xref:System.Windows.Forms.Control.ProcessMnemonic%2A>。|

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.WndProc%2A>
- <xref:System.Windows.Forms.Control.PreProcessMessage%2A>
- [使用键盘事件（Windows 窗体 .NET）](events.md)
- [如何修改键盘键事件（Windows 窗体 .NET）](how-to-change-key-press.md)
- [如何检查按下的修改键（Windows 窗体 .NET）](how-to-check-modifier-key.md)
- [如何模拟键盘事件（Windows 窗体 .NET）](how-to-simulate-events.md)
- [如何处理窗体中的键盘输入消息（Windows 窗体 .NET）](how-to-handle-forms.md)
- [添加控件（Windows 窗体 .NET）](../controls/how-to-add-to-a-form.md)
