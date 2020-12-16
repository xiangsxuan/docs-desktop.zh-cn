---
title: 使用键盘事件
description: 使用键盘事件处理键盘输入的概述。 本文列出了与键盘相关的事件，并说明了何时使用它们。
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- KeyPress event [Windows Forms]
- keyboards [Windows Forms], keyboard events
- KeyUp event
- KeyDown event
- keyboard events
- events [Windows Forms], keyboard
ms.openlocfilehash: 3e7493c9841fa036aa9d18aa00a1322d9758cbb1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942022"
---
# <a name="using-keyboard-events-windows-forms-net"></a>使用键盘事件（Windows 窗体 .NET）

大多数 Windows 窗体程序通过处理键盘事件处理键盘输入。 本文提供对键盘事件的概述，包括有关何时使用每个事件和向每个事件提供的数据的详细信息。 有关一般事件的详细信息，请参阅[事件概述（Windows 窗体 .NET）](../forms/events.md)。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="keyboard-events"></a>键盘事件

Windows 窗体提供了两个在用户按下键盘键时发生的事件和一个在用户释放键盘键时发生的事件：

- <xref:System.Windows.Forms.Control.KeyDown> 事件发生一次。
- 用户按住相同的键时，<xref:System.Windows.Forms.Control.KeyPress> 事件可发生多次。
- 用户释放某个键时，<xref:System.Windows.Forms.Control.KeyUp> 事件发生一次。

用户按某个键时，Windows 窗体会根据键盘消息指定的是字符键还是物理键来确定引发哪个事件。 有关字符键和物理键的详细信息，请参阅[键盘概述、键盘事件](overview.md#keyboard-events)。

下表介绍了这三种键盘事件：

|键盘事件|描述|结果|
|--------------------|-----------------|-------------|
|<xref:System.Windows.Forms.Control.KeyDown>|用户按下物理键时，引发此事件。|<xref:System.Windows.Forms.Control.KeyDown> 的处理程序接收：<br /><br /> <ul><li>一个 <xref:System.Windows.Forms.KeyEventArgs> 参数，它提供 <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> 属性（该属性指定一个物理键盘按钮）。</li><li><xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> 属性（SHIFT、CTRL 或 ALT）。</li><li><xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> 属性（它结合了键代码和修饰符）。 <xref:System.Windows.Forms.KeyEventArgs> 参数还提供：<br /><br /> <ul><li><xref:System.Windows.Forms.KeyEventArgs.Handled%2A> 属性，可以设置该属性以防止基础控件接收键。</li><li><xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> 属性，可用于取消该击键的 <xref:System.Windows.Forms.Control.KeyPress> 和 <xref:System.Windows.Forms.Control.KeyUp> 事件。</li></ul></li></ul>|
|<xref:System.Windows.Forms.Control.KeyPress>|当所按的某个键或多个键生成一个字符时，则引发此事件。 例如，用户按 SHIFT 和小写的“a”键将会生成大写字母“A”字符。|<xref:System.Windows.Forms.Control.KeyPress> 在 <xref:System.Windows.Forms.Control.KeyDown> 后引发。<br /><br /> <ul><li><xref:System.Windows.Forms.Control.KeyPress> 的处理程序接收：</li><li>一个 <xref:System.Windows.Forms.KeyPressEventArgs> 参数，它包含所按的键的字符代码。 此字符代码对每个字符键和修改键组合都是唯一的。<br /><br />     例如，“A”键将生成：<br /><br /> <ul><li>字符代码 65（如果与 SHIFT 键一起按下）</li><li>或 CAPS LOCK 键 97（如果单独按下），</li><li>以及 1（如果与 CTRL 键一起按下）。</li></ul></li></ul>|
|<xref:System.Windows.Forms.Control.KeyUp>|用户释放物理键时，将引发此事件。|<xref:System.Windows.Forms.Control.KeyUp> 的处理程序接收：<br /><br /> <ul><li>一个 <xref:System.Windows.Forms.KeyEventArgs> 参数：<br /><br /> <ul><li>它提供 <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> 属性（该属性指定一个物理键盘按钮）。</li><li><xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> 属性（SHIFT、CTRL 或 ALT）。</li><li><xref:System.Globalization.SortKey.KeyData%2A> 属性（它结合了键代码和修饰符）。</li></ul></li></ul>|

## <a name="see-also"></a>另请参阅

- [使用键盘的概述（Windows 窗体 .NET）](overview.md)
- [如何修改键盘键事件（Windows 窗体 .NET）](how-to-change-key-press.md)
- [如何检查按下的修改键（Windows 窗体 .NET）](how-to-check-modifier-key.md)
- [如何模拟键盘事件（Windows 窗体 .NET）](how-to-simulate-events.md)
- [如何处理窗体中的键盘输入消息（Windows 窗体 .NET）](how-to-handle-forms.md)
