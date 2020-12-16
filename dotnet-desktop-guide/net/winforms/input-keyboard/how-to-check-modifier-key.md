---
title: 检查按下的修改键
description: 了解如何检测何时在适用于 .NET 的 Windows 窗体中按下了 SHIFT、ALT 或 CTRL 键。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.openlocfilehash: 7feda0f604e1cb40b34f7bf42aa122d817a5a95e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941954"
---
# <a name="how-to-check-for-modifier-key-presses-windows-forms-net"></a>如何检查按下的修改键（Windows 窗体 .NET）

当用户在应用程序中键入键时，可监视按下的修改键，如 <kbd>SHIFT</kbd>、<kbd>ALT</kbd> 和 <kbd>CTRL</kbd>。 当修改键与其他键甚至是鼠标单击一起按下时，应用程序可以相应地做出响应。 例如，按 <kbd>S</kbd> 键可能会在屏幕上显示一个“s”。 如果按下键 <kbd>CTRL+S</kbd>，可能会保存当前文档。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

如果处理 <xref:System.Windows.Forms.Control.KeyDown> 事件，事件处理程序收到的 <xref:System.Windows.Forms.KeyEventArgs.Modifiers?displayProperty=nameWithType> 属性将指定按下的修改键。 此外，<xref:System.Windows.Forms.KeyEventArgs.KeyData?displayProperty=nameWithType> 属性指定与按位 OR 组合的所有修改键一起按下的字符。

如果要处理 <xref:System.Windows.Forms.Control.KeyPress> 事件或鼠标事件，事件处理程序不会收到此信息。 使用 <xref:System.Windows.Forms.Control> 类的 <xref:System.Windows.Forms.Control.ModifierKeys%2A> 属性来检测修改键。 在任一情况下，都必须对相应的 <xref:System.Windows.Forms.Keys> 值和要测试的值执行按位 AND。 <xref:System.Windows.Forms.Keys> 枚举提供每个修改键的变体，因此，请务必使用正确的值执行按位 AND 检查。

例如，<kbd>SHIFT</kbd> 键由以下键值表示：

- <xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.ShiftKey?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.RShiftKey?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.LShiftKey?displayProperty=nameWithType>

将 <kbd>SHIFT</kbd> 作为修改键进行测试的正确值是 <xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType>。 同样，若要将 <kbd>CTRL</kbd> 和 <kbd>ALT</kbd> 作为修改键进行测试，应分别使用 <xref:System.Windows.Forms.Keys.Control?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.Keys.Alt?displayProperty=nameWithType> 值。

## <a name="detect-modifier-key"></a>检测修改键

通过将 <xref:System.Windows.Forms.Control.ModifierKeys%2A> 属性和 <xref:System.Windows.Forms.Keys> 枚举值与按位 AND 运算符进行比较，检测是否已按下修改键。

下面的代码示例演示如何确定在 <xref:System.Windows.Forms.Control.KeyPress> 和 <xref:System.Windows.Forms.Control.KeyDown> 事件处理程序中是否按下了 <kbd>SHIFT</kbd> 键。

:::code language="csharp" source="snippets/how-to-check-modifier-key/csharp/Form1.cs" id="DetectModifier":::
:::code language="vb" source="snippets/how-to-check-modifier-key/vb/Form1.vb" id="DetectModifier":::

## <a name="see-also"></a>另请参阅

- [使用键盘的概述（Windows 窗体 .NET）](overview.md)
- [使用键盘事件（Windows 窗体 .NET）](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
