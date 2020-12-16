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
# <a name="how-to-handle-keyboard-input-messages-in-the-form-windows-forms-net"></a><span data-ttu-id="fbb6a-103">如何处理窗体中的键盘输入消息（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="fbb6a-103">How to handle keyboard input messages in the form (Windows Forms .NET)</span></span>

<span data-ttu-id="fbb6a-104">Windows 窗体能够在消息到达控件之前处理窗体级别的键盘消息。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-104">Windows Forms provides the ability to handle keyboard messages at the form level, before the messages reach a control.</span></span> <span data-ttu-id="fbb6a-105">本文演示如何完成此任务。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-105">This article shows how to accomplish this task.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="handle-a-keyboard-message"></a><span data-ttu-id="fbb6a-106">处理键盘消息</span><span class="sxs-lookup"><span data-stu-id="fbb6a-106">Handle a keyboard message</span></span>

<span data-ttu-id="fbb6a-107">处理有效窗体的 <xref:System.Windows.Forms.Control.KeyPress> 或 <xref:System.Windows.Forms.Control.KeyDown> 事件，并将该窗体的 <xref:System.Windows.Forms.Form.KeyPreview%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-107">Handle the <xref:System.Windows.Forms.Control.KeyPress> or <xref:System.Windows.Forms.Control.KeyDown> event of the active form and set the <xref:System.Windows.Forms.Form.KeyPreview%2A> property of the form to `true`.</span></span> <span data-ttu-id="fbb6a-108">此属性会使键盘消息在到达窗体上的任何控件之前就被窗体接收。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-108">This property causes the keyboard to be received by the form before they reach any controls on the form.</span></span> <span data-ttu-id="fbb6a-109">以下代码示例通过检测所有数字键并使用 <kbd>1</kbd>、<kbd>4</kbd> 和 <kbd>7</kbd> 来处理 <xref:System.Windows.Forms.Control.KeyPress> 事件。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-109">The following code example handles the <xref:System.Windows.Forms.Control.KeyPress> event by detecting all of the number keys and consuming <kbd>1</kbd>, <kbd>4</kbd>, and <kbd>7</kbd>.</span></span>

:::code language="csharp" source="snippets/how-to-handle-forms/csharp/Form1.cs" id="HandleKey":::
:::code language="vb" source="snippets/how-to-handle-forms/vb/Form1.vb" id="HandleKey":::

## <a name="see-also"></a><span data-ttu-id="fbb6a-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbb6a-110">See also</span></span>

- [<span data-ttu-id="fbb6a-111">使用键盘的概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="fbb6a-111">Overview of using the keyboard (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="fbb6a-112">使用键盘事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="fbb6a-112">Using keyboard events (Windows Forms .NET)</span></span>](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
