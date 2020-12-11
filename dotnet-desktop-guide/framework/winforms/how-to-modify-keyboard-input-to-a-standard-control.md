---
title: 如何：修改标准控件中的键盘输入
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], modifying
- modifying keyboard input
- Windows Forms, modifying keyboard input
- keyboards [Windows Forms], keyboard input
ms.assetid: 626d3712-d866-4988-bcda-a2d5b36ec0ba
ms.openlocfilehash: 1aa22501eb3d15b30be4ea4918473cf5a48cfe94
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972734"
---
# <a name="how-to-modify-keyboard-input-to-a-standard-control"></a><span data-ttu-id="857e2-102">如何：修改标准控件中的键盘输入</span><span class="sxs-lookup"><span data-stu-id="857e2-102">How to: Modify Keyboard Input to a Standard Control</span></span>
<span data-ttu-id="857e2-103">Windows 窗体提供使用和修改键盘输入的功能。</span><span class="sxs-lookup"><span data-stu-id="857e2-103">Windows Forms provides the ability to consume and modify keyboard input.</span></span> <span data-ttu-id="857e2-104">使用键是指处理方法或事件处理程序内的键，以便消息队列更低处的其他方法和事件不会接收到键值。</span><span class="sxs-lookup"><span data-stu-id="857e2-104">Consuming a key refers to handling a key within a method or event handler so that other methods and events further down the message queue do not receive the key value.</span></span> <span data-ttu-id="857e2-105">修改键是指修改键的值，以便消息队列更低处的方法和事件处理程序接收不同的键值。</span><span class="sxs-lookup"><span data-stu-id="857e2-105">Modifying a key refers to modifying the value of a key so that methods and event handlers further down the message queue receive a different key value.</span></span> <span data-ttu-id="857e2-106">本主题演示如何完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="857e2-106">This topic shows how to accomplish these tasks.</span></span>  
  
### <a name="to-consume-a-key"></a><span data-ttu-id="857e2-107">若要使用键</span><span class="sxs-lookup"><span data-stu-id="857e2-107">To consume a key</span></span>  
  
- <span data-ttu-id="857e2-108">在 <xref:System.Windows.Forms.Control.KeyPress> 事件处理程序中，将 <xref:System.Windows.Forms.KeyPressEventArgs> 类的 <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="857e2-108">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to `true`.</span></span>  
  
     <span data-ttu-id="857e2-109">-或-</span><span class="sxs-lookup"><span data-stu-id="857e2-109">-or-</span></span>  
  
     <span data-ttu-id="857e2-110">在 <xref:System.Windows.Forms.Control.KeyDown> 事件处理程序中，将 <xref:System.Windows.Forms.KeyEventArgs> 类的 <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="857e2-110">In a <xref:System.Windows.Forms.Control.KeyDown> event handler, set the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> class to `true`.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="857e2-111">设置 <xref:System.Windows.Forms.Control.KeyDown> 事件处理程序中的 <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> 属性不会防止 <xref:System.Windows.Forms.Control.KeyPress> 和 <xref:System.Windows.Forms.Control.KeyUp> 事件因当前按键而引发。</span><span class="sxs-lookup"><span data-stu-id="857e2-111">Setting the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property in the <xref:System.Windows.Forms.Control.KeyDown> event handler does not prevent the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyUp> events from being raised for the current keystroke.</span></span> <span data-ttu-id="857e2-112">要实现此目的，请使用 <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="857e2-112">Use the <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> property for this purpose.</span></span>  
  
     <span data-ttu-id="857e2-113">以下示例是取自 `switch` 语句的摘要，可检查 <xref:System.Windows.Forms.Control.KeyPress> 事件处理程序接收的 <xref:System.Windows.Forms.KeyPressEventArgs> 的 <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="857e2-113">The following example is an excerpt from a `switch` statement that examines the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> received by a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span> <span data-ttu-id="857e2-114">此代码使用“A”和“a”字符键。</span><span class="sxs-lookup"><span data-stu-id="857e2-114">This code consumes the 'A' and 'a' character keys.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#6)]  
  
### <a name="to-modify-a-standard-character-key"></a><span data-ttu-id="857e2-115">若要修改标准字符键</span><span class="sxs-lookup"><span data-stu-id="857e2-115">To modify a standard character key</span></span>  
  
- <span data-ttu-id="857e2-116">在 <xref:System.Windows.Forms.Control.KeyPress> 事件处理程序中，将 <xref:System.Windows.Forms.KeyPressEventArgs> 类的 <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> 属性设置为新字符键的值。</span><span class="sxs-lookup"><span data-stu-id="857e2-116">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to the value of the new character key.</span></span>  
  
     <span data-ttu-id="857e2-117">以下示例是取自 `switch` 语句的摘要，可将“A”修改为“B”，将“b”修改为“a”。</span><span class="sxs-lookup"><span data-stu-id="857e2-117">The following example is an excerpt from a `switch` statement that modifies 'B' to 'A' and 'b' to 'a'.</span></span> <span data-ttu-id="857e2-118">请注意，<xref:System.Windows.Forms.KeyPressEventArgs> 参数的 <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> 属性设置为 `false`，以便将新的键值传播至消息队列中的其他方法和事件。</span><span class="sxs-lookup"><span data-stu-id="857e2-118">Note that the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> parameter is set to `false`, so that the new key value is propagated to other methods and events in the message queue.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#7)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#7)]  
  
### <a name="to-modify-a-noncharacter-key"></a><span data-ttu-id="857e2-119">若要修改非字符键</span><span class="sxs-lookup"><span data-stu-id="857e2-119">To modify a noncharacter key</span></span>  
  
- <span data-ttu-id="857e2-120">重写 <xref:System.Windows.Forms.Control> 方法，此方法可处理 Windows 消息，检测 WM_KEYDOWN 或 WM_SYSKEYDOWN 消息，并将 <xref:System.Windows.Forms.Message> 参数的 <xref:System.Windows.Forms.Message.WParam%2A> 属性设置为 <xref:System.Windows.Forms.Keys> 值（表示新的非字符键）。</span><span class="sxs-lookup"><span data-stu-id="857e2-120">Override a <xref:System.Windows.Forms.Control> method that processes Windows messages, detect the WM_KEYDOWN or WM_SYSKEYDOWN message, and set the <xref:System.Windows.Forms.Message.WParam%2A> property of the <xref:System.Windows.Forms.Message> parameter to the <xref:System.Windows.Forms.Keys> value that represents the new noncharacter key.</span></span>  
  
     <span data-ttu-id="857e2-121">以下代码示例演示如何重写控件的 <xref:System.Windows.Forms.Control.PreProcessMessage%2A> 方法以检测 F1 至 F9 键并将任一 F3 按键修改为 F1。</span><span class="sxs-lookup"><span data-stu-id="857e2-121">The following code example demonstrates how to override the <xref:System.Windows.Forms.Control.PreProcessMessage%2A> method of a control to detect keys F1 through F9 and modify any F3 key press to F1.</span></span> <span data-ttu-id="857e2-122">有关 <xref:System.Windows.Forms.Control> 可以重写以截获键盘消息的方法的详细信息，请参阅 [Windows 窗体应用程序中的用户输入](user-input-in-a-windows-forms-application.md) 和 [键盘输入的工作方式](how-keyboard-input-works.md)。</span><span class="sxs-lookup"><span data-stu-id="857e2-122">For more information on <xref:System.Windows.Forms.Control> methods that you can override to intercept keyboard messages, see [User Input in a Windows Forms Application](user-input-in-a-windows-forms-application.md) and [How Keyboard Input Works](how-keyboard-input-works.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="857e2-123">示例</span><span class="sxs-lookup"><span data-stu-id="857e2-123">Example</span></span>  
 <span data-ttu-id="857e2-124">以下代码示例显示前几节中的代码示例的完整应用程序。</span><span class="sxs-lookup"><span data-stu-id="857e2-124">The following code example is the complete application for the code examples in the previous sections.</span></span> <span data-ttu-id="857e2-125">应用程序使用派生自 <xref:System.Windows.Forms.TextBox> 类的自定义控件来使用和修改键盘输入。</span><span class="sxs-lookup"><span data-stu-id="857e2-125">The application uses a custom control derived from the <xref:System.Windows.Forms.TextBox> class to consume and modify keyboard input.</span></span>  
  
 [!code-csharp[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="857e2-126">编译代码</span><span class="sxs-lookup"><span data-stu-id="857e2-126">Compiling the Code</span></span>  
 <span data-ttu-id="857e2-127">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="857e2-127">This example requires:</span></span>  
  
- <span data-ttu-id="857e2-128">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="857e2-128">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="857e2-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="857e2-129">See also</span></span>

- [<span data-ttu-id="857e2-130">Windows 窗体应用程序中的键盘输入</span><span class="sxs-lookup"><span data-stu-id="857e2-130">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="857e2-131">Windows 窗体应用程序中的用户输入</span><span class="sxs-lookup"><span data-stu-id="857e2-131">User Input in a Windows Forms Application</span></span>](user-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="857e2-132">键盘输入工作原理</span><span class="sxs-lookup"><span data-stu-id="857e2-132">How Keyboard Input Works</span></span>](how-keyboard-input-works.md)
