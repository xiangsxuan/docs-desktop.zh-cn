---
title: 在窗体级别处理键盘输入
description: 了解如何在消息到达控件之前在窗体级别处理 Windows 窗体的键盘输入。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.openlocfilehash: 51433eeb32f73385fd74d8a236a273526c1b72ed
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941936"
---
# <a name="how-to-handle-keyboard-input-messages-in-the-form-windows-forms-net"></a>如何处理窗体中的键盘输入消息（Windows 窗体 .NET）

Windows 窗体能够在消息到达控件之前处理窗体级别的键盘消息。 本文演示如何完成此任务。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="handle-a-keyboard-message"></a>处理键盘消息

处理有效窗体的 <xref:System.Windows.Forms.Control.KeyPress> 或 <xref:System.Windows.Forms.Control.KeyDown> 事件，并将该窗体的 <xref:System.Windows.Forms.Form.KeyPreview%2A> 属性设置为 `true`。 此属性会使键盘消息在到达窗体上的任何控件之前就被窗体接收。 以下代码示例通过检测所有数字键并使用 <kbd>1</kbd>、<kbd>4</kbd> 和 <kbd>7</kbd> 来处理 <xref:System.Windows.Forms.Control.KeyPress> 事件。

:::code language="csharp" source="snippets/how-to-handle-forms/csharp/Form1.cs" id="HandleKey":::
:::code language="vb" source="snippets/how-to-handle-forms/vb/Form1.vb" id="HandleKey":::

## <a name="see-also"></a>另请参阅

- [使用键盘的概述（Windows 窗体 .NET）](overview.md)
- [使用键盘事件（Windows 窗体 .NET）](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
