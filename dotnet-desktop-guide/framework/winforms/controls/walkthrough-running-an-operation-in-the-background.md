---
title: 演练：在后台运行操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
ms.openlocfilehash: ad0955937965c89b52648e37cd151e0cd266e527
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972497"
---
# <a name="walkthrough-running-an-operation-in-the-background"></a><span data-ttu-id="eedd9-102">演练：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="eedd9-102">Walkthrough: Running an Operation in the Background</span></span>

<span data-ttu-id="eedd9-103">如果某项操作需要很长时间才能完成，而你不希望造成用户界面的延迟，则可以使用 <xref:System.ComponentModel.BackgroundWorker> 类在另一个线程上运行此操作。</span><span class="sxs-lookup"><span data-stu-id="eedd9-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>

<span data-ttu-id="eedd9-104">有关此示例中使用的代码的完整列表，请参阅 [如何：在后台运行操作](how-to-run-an-operation-in-the-background.md)。</span><span class="sxs-lookup"><span data-stu-id="eedd9-104">For a complete listing of the code used in this example, see [How to: Run an Operation in the Background](how-to-run-an-operation-in-the-background.md).</span></span>

## <a name="run-an-operation-in-the-background"></a><span data-ttu-id="eedd9-105">在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="eedd9-105">Run an operation in the background</span></span>

1. <span data-ttu-id="eedd9-106">在 Visual Studio 中的 Windows 窗体设计器中激活窗体后，将两个 <xref:System.Windows.Forms.Button> 控件从 **工具箱** 拖到窗体上，然后 `Name` <xref:System.Windows.Forms.Control.Text%2A> 根据下表设置这些按钮的和属性。</span><span class="sxs-lookup"><span data-stu-id="eedd9-106">With your form active in the Windows Forms Designer in Visual Studio, drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to the form, and then set the `Name` and <xref:System.Windows.Forms.Control.Text%2A> properties of the buttons according to the following table.</span></span>

    |<span data-ttu-id="eedd9-107">Button</span><span class="sxs-lookup"><span data-stu-id="eedd9-107">Button</span></span>|<span data-ttu-id="eedd9-108">名称</span><span class="sxs-lookup"><span data-stu-id="eedd9-108">Name</span></span>|<span data-ttu-id="eedd9-109">文本</span><span class="sxs-lookup"><span data-stu-id="eedd9-109">Text</span></span>|
    |------------|----------|----------|
    |`button1`|`startBtn`|<span data-ttu-id="eedd9-110">**启动**</span><span class="sxs-lookup"><span data-stu-id="eedd9-110">**Start**</span></span>|
    |`button2`|`cancelBtn`|<span data-ttu-id="eedd9-111">**取消**</span><span class="sxs-lookup"><span data-stu-id="eedd9-111">**Cancel**</span></span>|

2. <span data-ttu-id="eedd9-112">打开 " **工具箱**"，单击 " **组件** " 选项卡，然后将 <xref:System.ComponentModel.BackgroundWorker> 组件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="eedd9-112">Open the **Toolbox**, click the **Components** tab, and then drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span>

     <span data-ttu-id="eedd9-113">`backgroundWorker1`组件将出现在 **组件栏** 中。</span><span class="sxs-lookup"><span data-stu-id="eedd9-113">The `backgroundWorker1` component appears in the **Component Tray**.</span></span>

3. <span data-ttu-id="eedd9-114">在“属性”  窗口中，将 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="eedd9-114">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> property to `true`.</span></span>

4. <span data-ttu-id="eedd9-115">在 " **属性** " 窗口中，单击 " **事件** " 按钮，然后双击 <xref:System.ComponentModel.BackgroundWorker.DoWork> 和 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 事件创建事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="eedd9-115">In the **Properties** window, click on the **Events** button, and then double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span>

5. <span data-ttu-id="eedd9-116">将耗时的代码插入到 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="eedd9-116">Insert your time-consuming code into the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>

6. <span data-ttu-id="eedd9-117">从参数的属性中提取操作所需的所有参数 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> <xref:System.ComponentModel.DoWorkEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="eedd9-117">Extract any parameters required by the operation from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs> parameter.</span></span>

7. <span data-ttu-id="eedd9-118">将计算结果分配给 <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> 的属性 <xref:System.ComponentModel.DoWorkEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="eedd9-118">Assign the result of the computation to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span>

     <span data-ttu-id="eedd9-119">此事件处理程序将提供此功能 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 。</span><span class="sxs-lookup"><span data-stu-id="eedd9-119">This is will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]

8. <span data-ttu-id="eedd9-120">用于在事件处理程序中检索操作结果的插入代码 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 。</span><span class="sxs-lookup"><span data-stu-id="eedd9-120">Insert code for retrieving the result of your operation in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]

9. <span data-ttu-id="eedd9-121">实现 `TimeConsumingOperation` 方法。</span><span class="sxs-lookup"><span data-stu-id="eedd9-121">Implement the `TimeConsumingOperation` method.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]

10. <span data-ttu-id="eedd9-122">在 Windows 窗体设计器中，双击 `startButton` 创建 <xref:System.Windows.Forms.Control.Click> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="eedd9-122">In the Windows Forms Designer, double-click `startButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>

11. <span data-ttu-id="eedd9-123"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>在的 <xref:System.Windows.Forms.Control.Click> 事件处理程序中调用方法 `startButton` 。</span><span class="sxs-lookup"><span data-stu-id="eedd9-123">Call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `startButton`.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]

12. <span data-ttu-id="eedd9-124">在 Windows 窗体设计器中，双击 `cancelButton` 创建 <xref:System.Windows.Forms.Control.Click> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="eedd9-124">In the Windows Forms Designer, double-click `cancelButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>

13. <span data-ttu-id="eedd9-125"><xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>在的 <xref:System.Windows.Forms.Control.Click> 事件处理程序中调用方法 `cancelButton` 。</span><span class="sxs-lookup"><span data-stu-id="eedd9-125">Call the <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `cancelButton`.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]

14. <span data-ttu-id="eedd9-126">在该文件的顶部，导入 System.componentmodel 和 System.object 命名空间。</span><span class="sxs-lookup"><span data-stu-id="eedd9-126">At the top of the file, import the System.ComponentModel and System.Threading namespaces.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]

15. <span data-ttu-id="eedd9-127">按 **F6** 生成解决方案，然后按 **Ctrl** + **F5** 在调试器外部运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="eedd9-127">Press **F6** to build the solution, and then press **Ctrl**+**F5** to run the application outside the debugger.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eedd9-128">如果按 **F5** 在调试器下运行该应用程序， `TimeConsumingOperation` 调试器将捕获并显示该方法中引发的异常。</span><span class="sxs-lookup"><span data-stu-id="eedd9-128">If you press **F5** to run the application under the debugger, the exception raised in the `TimeConsumingOperation` method is caught and displayed by the debugger.</span></span> <span data-ttu-id="eedd9-129">当你在调试器外部运行应用程序时， <xref:System.ComponentModel.BackgroundWorker> 会处理异常并将其缓存在 <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> 的属性中 <xref:System.ComponentModel.RunWorkerCompletedEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="eedd9-129">When you run the application outside the debugger, the <xref:System.ComponentModel.BackgroundWorker> handles the exception and caches it in the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> property of the <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span></span>

16. <span data-ttu-id="eedd9-130">单击 " **启动** " 按钮运行异步操作，然后单击 " **取消** " 按钮停止正在运行的异步操作。</span><span class="sxs-lookup"><span data-stu-id="eedd9-130">Click the **Start** button to run an asynchronous operation, and then click the **Cancel** button to stop a running asynchronous operation.</span></span>

     <span data-ttu-id="eedd9-131">每个操作的结果显示在 <xref:System.Windows.Forms.MessageBox> 中。</span><span class="sxs-lookup"><span data-stu-id="eedd9-131">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="eedd9-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="eedd9-132">Next steps</span></span>

- <span data-ttu-id="eedd9-133">实现一个窗体，该窗体在异步操作继续时报告进度。</span><span class="sxs-lookup"><span data-stu-id="eedd9-133">Implement a form that reports progress as an asynchronous operation proceeds.</span></span> <span data-ttu-id="eedd9-134">有关详细信息，请参阅 [如何：实现使用后台操作的窗体](how-to-implement-a-form-that-uses-a-background-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="eedd9-134">For more information, see [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>

- <span data-ttu-id="eedd9-135">实现支持组件的异步模式的类。</span><span class="sxs-lookup"><span data-stu-id="eedd9-135">Implement a class that supports the Asynchronous Pattern for Components.</span></span> <span data-ttu-id="eedd9-136">有关详细信息，请参阅 [实现基于事件的异步模式](/dotnet/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern)。</span><span class="sxs-lookup"><span data-stu-id="eedd9-136">For more information, see [Implementing the Event-based Asynchronous Pattern](/dotnet/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern).</span></span>

## <a name="see-also"></a><span data-ttu-id="eedd9-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eedd9-137">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="eedd9-138">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="eedd9-138">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="eedd9-139">如何：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="eedd9-139">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="eedd9-140">BackgroundWorker 组件</span><span class="sxs-lookup"><span data-stu-id="eedd9-140">BackgroundWorker Component</span></span>](backgroundworker-component.md)
