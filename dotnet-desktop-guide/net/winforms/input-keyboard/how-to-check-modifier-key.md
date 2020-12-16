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
# <a name="how-to-check-for-modifier-key-presses-windows-forms-net"></a><span data-ttu-id="7f95b-103">如何检查按下的修改键（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="7f95b-103">How to check for modifier key presses (Windows Forms .NET)</span></span>

<span data-ttu-id="7f95b-104">当用户在应用程序中键入键时，可监视按下的修改键，如 <kbd>SHIFT</kbd>、<kbd>ALT</kbd> 和 <kbd>CTRL</kbd>。</span><span class="sxs-lookup"><span data-stu-id="7f95b-104">As the user types keys into your application, you can monitor for pressed modifier keys such as the <kbd>SHIFT</kbd>, <kbd>ALT</kbd>, and <kbd>CTRL</kbd>.</span></span> <span data-ttu-id="7f95b-105">当修改键与其他键甚至是鼠标单击一起按下时，应用程序可以相应地做出响应。</span><span class="sxs-lookup"><span data-stu-id="7f95b-105">When a modifier key is pressed in combination with other keys or even a mouse click, your application can respond appropriately.</span></span> <span data-ttu-id="7f95b-106">例如，按 <kbd>S</kbd> 键可能会在屏幕上显示一个“s”。</span><span class="sxs-lookup"><span data-stu-id="7f95b-106">For example, pressing the <kbd>S</kbd> key may cause an "s" to appear on the screen.</span></span> <span data-ttu-id="7f95b-107">如果按下键 <kbd>CTRL+S</kbd>，可能会保存当前文档。</span><span class="sxs-lookup"><span data-stu-id="7f95b-107">If the keys <kbd>CTRL+S</kbd> are pressed, instead, the current document may be saved.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="7f95b-108">如果处理 <xref:System.Windows.Forms.Control.KeyDown> 事件，事件处理程序收到的 <xref:System.Windows.Forms.KeyEventArgs.Modifiers?displayProperty=nameWithType> 属性将指定按下的修改键。</span><span class="sxs-lookup"><span data-stu-id="7f95b-108">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers?displayProperty=nameWithType> property received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="7f95b-109">此外，<xref:System.Windows.Forms.KeyEventArgs.KeyData?displayProperty=nameWithType> 属性指定与按位 OR 组合的所有修改键一起按下的字符。</span><span class="sxs-lookup"><span data-stu-id="7f95b-109">Also, the <xref:System.Windows.Forms.KeyEventArgs.KeyData?displayProperty=nameWithType> property specifies the character that was pressed along with any modifier keys combined with a bitwise OR.</span></span>

<span data-ttu-id="7f95b-110">如果要处理 <xref:System.Windows.Forms.Control.KeyPress> 事件或鼠标事件，事件处理程序不会收到此信息。</span><span class="sxs-lookup"><span data-stu-id="7f95b-110">If you're handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler doesn't receive this information.</span></span> <span data-ttu-id="7f95b-111">使用 <xref:System.Windows.Forms.Control> 类的 <xref:System.Windows.Forms.Control.ModifierKeys%2A> 属性来检测修改键。</span><span class="sxs-lookup"><span data-stu-id="7f95b-111">Use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class to detect a key modifier.</span></span> <span data-ttu-id="7f95b-112">在任一情况下，都必须对相应的 <xref:System.Windows.Forms.Keys> 值和要测试的值执行按位 AND。</span><span class="sxs-lookup"><span data-stu-id="7f95b-112">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you're testing.</span></span> <span data-ttu-id="7f95b-113"><xref:System.Windows.Forms.Keys> 枚举提供每个修改键的变体，因此，请务必使用正确的值执行按位 AND 检查。</span><span class="sxs-lookup"><span data-stu-id="7f95b-113">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it's important that you do the bitwise AND check with the correct value.</span></span>

<span data-ttu-id="7f95b-114">例如，<kbd>SHIFT</kbd> 键由以下键值表示：</span><span class="sxs-lookup"><span data-stu-id="7f95b-114">For example, the <kbd>SHIFT</kbd> key is represented by the following key values:</span></span>

- <xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.ShiftKey?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.RShiftKey?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.LShiftKey?displayProperty=nameWithType>

<span data-ttu-id="7f95b-115">将 <kbd>SHIFT</kbd> 作为修改键进行测试的正确值是 <xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="7f95b-115">The correct value to test <kbd>SHIFT</kbd> as a modifier key is <xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7f95b-116">同样，若要将 <kbd>CTRL</kbd> 和 <kbd>ALT</kbd> 作为修改键进行测试，应分别使用 <xref:System.Windows.Forms.Keys.Control?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.Keys.Alt?displayProperty=nameWithType> 值。</span><span class="sxs-lookup"><span data-stu-id="7f95b-116">Similarly, to test for <kbd>CTRL</kbd> and <kbd>ALT</kbd> as modifiers you should use the <xref:System.Windows.Forms.Keys.Control?displayProperty=nameWithType> and <xref:System.Windows.Forms.Keys.Alt?displayProperty=nameWithType> values, respectively.</span></span>

## <a name="detect-modifier-key"></a><span data-ttu-id="7f95b-117">检测修改键</span><span class="sxs-lookup"><span data-stu-id="7f95b-117">Detect modifier key</span></span>

<span data-ttu-id="7f95b-118">通过将 <xref:System.Windows.Forms.Control.ModifierKeys%2A> 属性和 <xref:System.Windows.Forms.Keys> 枚举值与按位 AND 运算符进行比较，检测是否已按下修改键。</span><span class="sxs-lookup"><span data-stu-id="7f95b-118">Detect if a modifier key is pressed by comparing the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and the <xref:System.Windows.Forms.Keys> enumeration value with a bitwise AND operator.</span></span>

<span data-ttu-id="7f95b-119">下面的代码示例演示如何确定在 <xref:System.Windows.Forms.Control.KeyPress> 和 <xref:System.Windows.Forms.Control.KeyDown> 事件处理程序中是否按下了 <kbd>SHIFT</kbd> 键。</span><span class="sxs-lookup"><span data-stu-id="7f95b-119">The following code example shows how to determine whether the <kbd>SHIFT</kbd> key is pressed within the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyDown> event handlers.</span></span>

:::code language="csharp" source="snippets/how-to-check-modifier-key/csharp/Form1.cs" id="DetectModifier":::
:::code language="vb" source="snippets/how-to-check-modifier-key/vb/Form1.vb" id="DetectModifier":::

## <a name="see-also"></a><span data-ttu-id="7f95b-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f95b-120">See also</span></span>

- [<span data-ttu-id="7f95b-121">使用键盘的概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="7f95b-121">Overview of using the keyboard (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="7f95b-122">使用键盘事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="7f95b-122">Using keyboard events (Windows Forms .NET)</span></span>](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
