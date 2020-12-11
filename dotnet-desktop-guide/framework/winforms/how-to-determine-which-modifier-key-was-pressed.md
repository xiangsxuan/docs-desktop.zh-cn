---
title: 如何：确定按下了哪个修改键
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
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
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: 9140834b4849ecb143ac57a6f6ae20e2d870859b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970253"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="d0338-102">如何：确定按下了哪个修改键</span><span class="sxs-lookup"><span data-stu-id="d0338-102">How to: Determine Which Modifier Key Was Pressed</span></span>

<span data-ttu-id="d0338-103">当创建接受用户击键的应用程序时，可能还需要监视修改键，如 SHIFT、ALT 和 CTRL 键。</span><span class="sxs-lookup"><span data-stu-id="d0338-103">When you create an application that accepts the user's keystrokes, you may also want to monitor for modifier keys such as the SHIFT, ALT, and CTRL keys.</span></span> <span data-ttu-id="d0338-104">当修改键与其他键结合使用时，或通过鼠标单击时，应用程序可以相应地做出响应。</span><span class="sxs-lookup"><span data-stu-id="d0338-104">When a modifier key is pressed in combination with other keys, or with mouse clicks, your application can respond appropriately.</span></span> <span data-ttu-id="d0338-105">例如，如果按下字母，这可能只是导致屏幕上出现 "S"，但如果按下键 CTRL + S，则可能会保存当前文档。</span><span class="sxs-lookup"><span data-stu-id="d0338-105">For example, if the letter S is pressed, this may simply cause an "s" to appear on the screen, but if the keys CTRL+S are pressed, the current document may be saved.</span></span> <span data-ttu-id="d0338-106">如果处理 <xref:System.Windows.Forms.Control.KeyDown> 事件， <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> <xref:System.Windows.Forms.KeyEventArgs> 事件处理程序接收的的属性将指定按下的修改键。</span><span class="sxs-lookup"><span data-stu-id="d0338-106">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="d0338-107">或者，的 <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> 属性 <xref:System.Windows.Forms.KeyEventArgs> 指定按下的字符以及与按位 "或" 组合的所有修改键。</span><span class="sxs-lookup"><span data-stu-id="d0338-107">Alternatively, the <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property of <xref:System.Windows.Forms.KeyEventArgs> specifies the character that was pressed as well as any modifier keys combined with a bitwise OR.</span></span> <span data-ttu-id="d0338-108">但是，如果要处理 <xref:System.Windows.Forms.Control.KeyPress> 事件或鼠标事件，事件处理程序不会收到此信息。</span><span class="sxs-lookup"><span data-stu-id="d0338-108">However, if you are handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler does not receive this information.</span></span> <span data-ttu-id="d0338-109">在这种情况下，必须使用 <xref:System.Windows.Forms.Control.ModifierKeys%2A> 类的属性 <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="d0338-109">In this case, you must use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="d0338-110">在任一情况下，都必须对适当的 <xref:System.Windows.Forms.Keys> 值和要测试的值执行按位 "与" 运算。</span><span class="sxs-lookup"><span data-stu-id="d0338-110">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you are testing.</span></span> <span data-ttu-id="d0338-111"><xref:System.Windows.Forms.Keys>枚举提供每个修改键的变体，因此，请务必按正确的值执行按位 "与"。</span><span class="sxs-lookup"><span data-stu-id="d0338-111">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it is important that you perform the bitwise AND with the correct value.</span></span> <span data-ttu-id="d0338-112">例如，shift 键由、和表示， <xref:System.Windows.Forms.Keys.Shift> <xref:System.Windows.Forms.Keys.ShiftKey> <xref:System.Windows.Forms.Keys.RShiftKey> <xref:System.Windows.Forms.Keys.LShiftKey> 用于测试移位作为修改键的正确值为 <xref:System.Windows.Forms.Keys.Shift> 。</span><span class="sxs-lookup"><span data-stu-id="d0338-112">For example, the SHIFT key is represented by <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> and <xref:System.Windows.Forms.Keys.LShiftKey> The correct value to test SHIFT as a modifier key is <xref:System.Windows.Forms.Keys.Shift>.</span></span> <span data-ttu-id="d0338-113">同样，若要测试 CTRL 和 ALT 作为修饰符，应分别使用 <xref:System.Windows.Forms.Keys.Control> 和 <xref:System.Windows.Forms.Keys.Alt> 值。</span><span class="sxs-lookup"><span data-stu-id="d0338-113">Similarly, to test for CTRL and ALT as modifiers you should use the <xref:System.Windows.Forms.Keys.Control> and <xref:System.Windows.Forms.Keys.Alt> values, respectively.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0338-114">Visual Basic 程序员还可以通过属性访问密钥信息 <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A></span><span class="sxs-lookup"><span data-stu-id="d0338-114">Visual Basic programmers can also access key information through the <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> property</span></span>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="d0338-115">确定按下了哪个修改键</span><span class="sxs-lookup"><span data-stu-id="d0338-115">To determine which modifier key was pressed</span></span>  
  
- <span data-ttu-id="d0338-116">对属性使用位 `AND` 运算符 <xref:System.Windows.Forms.Control.ModifierKeys%2A> ，并使用枚举的值 <xref:System.Windows.Forms.Keys> 来确定是否按下某个特定的修改键。</span><span class="sxs-lookup"><span data-stu-id="d0338-116">Use the bitwise `AND` operator with the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and a value of the <xref:System.Windows.Forms.Keys> enumeration to determine whether a particular modifier key is pressed.</span></span> <span data-ttu-id="d0338-117">下面的代码示例演示如何确定事件处理程序中是否按下了 SHIFT 键 <xref:System.Windows.Forms.Control.KeyPress> 。</span><span class="sxs-lookup"><span data-stu-id="d0338-117">The following code example shows how to determine whether the SHIFT key is pressed within a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="d0338-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0338-118">See also</span></span>

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [<span data-ttu-id="d0338-119">Windows 窗体应用程序中的键盘输入</span><span class="sxs-lookup"><span data-stu-id="d0338-119">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
- <span data-ttu-id="d0338-120">[如何：确定 CapsLock 是否在 Visual Basic](/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d0338-120">[How to: Determine If CapsLock is On in Visual Basic](/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))</span></span>
