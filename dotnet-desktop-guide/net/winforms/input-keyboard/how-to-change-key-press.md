---
title: 修改键盘键事件
description: 了解如何截获按键并修改在 Windows 窗体 .NET 应用程序上按下的键。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], modifying
- modifying keyboard input
- Windows Forms, modifying keyboard input
- keyboards [Windows Forms], keyboard input
ms.openlocfilehash: 94a003a8eb5fbffd9dbaf817a3ce95ca93a7d370
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941914"
---
# <a name="how-to-modify-keyboard-key-events-windows-forms-net"></a>如何修改键盘键事件（Windows 窗体 .NET）

Windows 窗体提供使用和修改键盘输入的功能。 使用键是指处理方法或事件处理程序内的键，以便消息队列更低处的其他方法和事件不会收到键值。 修改键是指修改键的值，以便消息队列更低处的方法和事件处理程序接收不同的键值。 本文演示如何完成这些任务。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="consume-a-key"></a>使用键

在 <xref:System.Windows.Forms.Control.KeyPress> 事件处理程序中，将 <xref:System.Windows.Forms.KeyPressEventArgs> 类的 <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> 属性设置为 `true`。

-或-

在 <xref:System.Windows.Forms.Control.KeyDown> 事件处理程序中，将 <xref:System.Windows.Forms.KeyEventArgs> 类的 <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> 属性设置为 `true`。

> [!NOTE]
> 设置 <xref:System.Windows.Forms.Control.KeyDown> 事件处理程序中的 <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> 属性不会防止 <xref:System.Windows.Forms.Control.KeyPress> 和 <xref:System.Windows.Forms.Control.KeyUp> 事件因当前按键而引发。 要实现此目的，请使用 <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> 属性。

下面的示例处理 <xref:System.Windows.Forms.Control.KeyPress> 事件以使用 `A` 和 `a` 字符键。 不能在文本框中键入这些键：

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/Form1.cs" id="ConsumeKey":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/Form1.vb" id="ConsumeKey":::

## <a name="modify-a-standard-character-key"></a>修改标准字符键

在 <xref:System.Windows.Forms.Control.KeyPress> 事件处理程序中，将 <xref:System.Windows.Forms.KeyPressEventArgs> 类的 <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> 属性设置为新字符键的值。

下面的示例处理 <xref:System.Windows.Forms.Control.KeyPress> 事件以将 `A` 和 `a` 字符键更改为 `!`：

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/Form1.cs" id="ModifyKey":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/Form1.vb" id="ModifyKey":::

## <a name="modify-a-non-character-key"></a>修改非字符键

仅可通过从控件继承并重写 <xref:System.Windows.Forms.Control.PreProcessMessage%2A> 方法来修改非字符按键。 当输入 <xref:System.Windows.Forms.Message> 发送到控件时，将在控件引发事件之前对其进行处理。 可以截获这些消息来修改或阻止它们。

以下代码示例演示了如何使用 <xref:System.Windows.Forms.Message> 参数的 <xref:System.Windows.Forms.Message.WParam%2A> 属性来更改按下的键。 此代码检测从 <kbd>F1</kbd> 到 <kbd>F10</kbd> 的键，并将该键转换为 <kbd>0</kbd> 到 <kbd>9</kbd> 之间的数字键（其中 <kbd>F10</kbd> 映射到 <kbd>0</kbd>）。

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/NewTextBox.cs" id="PreProcessMessage":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/NewTextBox.vb" id="PreProcessMessage":::

## <a name="see-also"></a>另请参阅

- [使用键盘的概述（Windows 窗体 .NET）](overview.md)
- [使用键盘事件（Windows 窗体 .NET）](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
