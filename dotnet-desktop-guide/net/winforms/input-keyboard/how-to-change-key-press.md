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
# <a name="how-to-modify-keyboard-key-events-windows-forms-net"></a><span data-ttu-id="33938-103">如何修改键盘键事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="33938-103">How to modify keyboard key events (Windows Forms .NET)</span></span>

<span data-ttu-id="33938-104">Windows 窗体提供使用和修改键盘输入的功能。</span><span class="sxs-lookup"><span data-stu-id="33938-104">Windows Forms provides the ability to consume and modify keyboard input.</span></span> <span data-ttu-id="33938-105">使用键是指处理方法或事件处理程序内的键，以便消息队列更低处的其他方法和事件不会收到键值。</span><span class="sxs-lookup"><span data-stu-id="33938-105">Consuming a key refers to handling a key within a method or event handler so that other methods and events further down the message queue don't receive the key value.</span></span> <span data-ttu-id="33938-106">修改键是指修改键的值，以便消息队列更低处的方法和事件处理程序接收不同的键值。</span><span class="sxs-lookup"><span data-stu-id="33938-106">And, modifying a key refers to modifying the value of a key so that methods and event handlers further down the message queue receive a different key value.</span></span> <span data-ttu-id="33938-107">本文演示如何完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="33938-107">This article shows how to accomplish these tasks.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="consume-a-key"></a><span data-ttu-id="33938-108">使用键</span><span class="sxs-lookup"><span data-stu-id="33938-108">Consume a key</span></span>

<span data-ttu-id="33938-109">在 <xref:System.Windows.Forms.Control.KeyPress> 事件处理程序中，将 <xref:System.Windows.Forms.KeyPressEventArgs> 类的 <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="33938-109">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to `true`.</span></span>

<span data-ttu-id="33938-110">-或-</span><span class="sxs-lookup"><span data-stu-id="33938-110">-or-</span></span>

<span data-ttu-id="33938-111">在 <xref:System.Windows.Forms.Control.KeyDown> 事件处理程序中，将 <xref:System.Windows.Forms.KeyEventArgs> 类的 <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="33938-111">In a <xref:System.Windows.Forms.Control.KeyDown> event handler, set the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> class to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="33938-112">设置 <xref:System.Windows.Forms.Control.KeyDown> 事件处理程序中的 <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> 属性不会防止 <xref:System.Windows.Forms.Control.KeyPress> 和 <xref:System.Windows.Forms.Control.KeyUp> 事件因当前按键而引发。</span><span class="sxs-lookup"><span data-stu-id="33938-112">Setting the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property in the <xref:System.Windows.Forms.Control.KeyDown> event handler does not prevent the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyUp> events from being raised for the current keystroke.</span></span> <span data-ttu-id="33938-113">要实现此目的，请使用 <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="33938-113">Use the <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> property for this purpose.</span></span>

<span data-ttu-id="33938-114">下面的示例处理 <xref:System.Windows.Forms.Control.KeyPress> 事件以使用 `A` 和 `a` 字符键。</span><span class="sxs-lookup"><span data-stu-id="33938-114">The following example handles the <xref:System.Windows.Forms.Control.KeyPress> event to consume the `A` and `a` character keys.</span></span> <span data-ttu-id="33938-115">不能在文本框中键入这些键：</span><span class="sxs-lookup"><span data-stu-id="33938-115">Those keys can't be typed into the text box:</span></span>

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/Form1.cs" id="ConsumeKey":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/Form1.vb" id="ConsumeKey":::

## <a name="modify-a-standard-character-key"></a><span data-ttu-id="33938-116">修改标准字符键</span><span class="sxs-lookup"><span data-stu-id="33938-116">Modify a standard character key</span></span>

<span data-ttu-id="33938-117">在 <xref:System.Windows.Forms.Control.KeyPress> 事件处理程序中，将 <xref:System.Windows.Forms.KeyPressEventArgs> 类的 <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> 属性设置为新字符键的值。</span><span class="sxs-lookup"><span data-stu-id="33938-117">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to the value of the new character key.</span></span>

<span data-ttu-id="33938-118">下面的示例处理 <xref:System.Windows.Forms.Control.KeyPress> 事件以将 `A` 和 `a` 字符键更改为 `!`：</span><span class="sxs-lookup"><span data-stu-id="33938-118">The following example handles the <xref:System.Windows.Forms.Control.KeyPress> event to change any `A` and `a` character keys to `!`:</span></span>

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/Form1.cs" id="ModifyKey":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/Form1.vb" id="ModifyKey":::

## <a name="modify-a-non-character-key"></a><span data-ttu-id="33938-119">修改非字符键</span><span class="sxs-lookup"><span data-stu-id="33938-119">Modify a non-character key</span></span>

<span data-ttu-id="33938-120">仅可通过从控件继承并重写 <xref:System.Windows.Forms.Control.PreProcessMessage%2A> 方法来修改非字符按键。</span><span class="sxs-lookup"><span data-stu-id="33938-120">You can only modify non-character key presses by inheriting from the control and overriding the <xref:System.Windows.Forms.Control.PreProcessMessage%2A> method.</span></span> <span data-ttu-id="33938-121">当输入 <xref:System.Windows.Forms.Message> 发送到控件时，将在控件引发事件之前对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="33938-121">As the   input <xref:System.Windows.Forms.Message> is sent to the control, it's processed before the control raising events.</span></span> <span data-ttu-id="33938-122">可以截获这些消息来修改或阻止它们。</span><span class="sxs-lookup"><span data-stu-id="33938-122">You can intercept these messages to modify or block them.</span></span>

<span data-ttu-id="33938-123">以下代码示例演示了如何使用 <xref:System.Windows.Forms.Message> 参数的 <xref:System.Windows.Forms.Message.WParam%2A> 属性来更改按下的键。</span><span class="sxs-lookup"><span data-stu-id="33938-123">The following code example demonstrates how to use the <xref:System.Windows.Forms.Message.WParam%2A> property of the <xref:System.Windows.Forms.Message> parameter to change the key pressed.</span></span> <span data-ttu-id="33938-124">此代码检测从 <kbd>F1</kbd> 到 <kbd>F10</kbd> 的键，并将该键转换为 <kbd>0</kbd> 到 <kbd>9</kbd> 之间的数字键（其中 <kbd>F10</kbd> 映射到 <kbd>0</kbd>）。</span><span class="sxs-lookup"><span data-stu-id="33938-124">This code detects a key from <kbd>F1</kbd> through <kbd>F10</kbd> and translates the key into a numeric key ranging from <kbd>0</kbd> through <kbd>9</kbd> (where <kbd>F10</kbd> maps to <kbd>0</kbd>).</span></span>

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/NewTextBox.cs" id="PreProcessMessage":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/NewTextBox.vb" id="PreProcessMessage":::

## <a name="see-also"></a><span data-ttu-id="33938-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33938-125">See also</span></span>

- [<span data-ttu-id="33938-126">使用键盘的概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="33938-126">Overview of using the keyboard (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="33938-127">使用键盘事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="33938-127">Using keyboard events (Windows Forms .NET)</span></span>](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
