---
title: 演练：实现使用后台操作的窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- threading [Windows Forms], walkthroughs
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
ms.openlocfilehash: bdd82b0f32f93fbcdd5713bfb9ba9081f653298b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972504"
---
# <a name="walkthrough-implementing-a-form-that-uses-a-background-operation"></a><span data-ttu-id="73a71-102">演练：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="73a71-102">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>

<span data-ttu-id="73a71-103">如果你有一个需要很长时间才能完成的操作，并且不希望你的用户界面 (UI) 停止响应或阻止，则可以使用 <xref:System.ComponentModel.BackgroundWorker> 类在另一个线程上执行该操作。</span><span class="sxs-lookup"><span data-stu-id="73a71-103">If you have an operation that will take a long time to complete, and you do not want your user interface (UI) to stop responding or to block, you can use the <xref:System.ComponentModel.BackgroundWorker> class to execute the operation on another thread.</span></span>

<span data-ttu-id="73a71-104">本演练演示了如何使用 <xref:System.ComponentModel.BackgroundWorker> 类来 "在后台" 执行耗时计算，同时用户界面保持响应状态。</span><span class="sxs-lookup"><span data-stu-id="73a71-104">This walkthrough illustrates how to use the <xref:System.ComponentModel.BackgroundWorker> class to perform time-consuming computations "in the background," while the user interface remains responsive.</span></span>  <span data-ttu-id="73a71-105">演练时，将有一个异步计算 Fibonacci 数列的应用程序。</span><span class="sxs-lookup"><span data-stu-id="73a71-105">When you are through, you will have an application that computes Fibonacci numbers asynchronously.</span></span> <span data-ttu-id="73a71-106">即使计算大型 Fibonacci 数列需要花费大量时间，但主 UI 线程不会被这种延时中断，并且在计算期间窗体仍会响应。</span><span class="sxs-lookup"><span data-stu-id="73a71-106">Even though computing a large Fibonacci number can take a noticeable amount of time, the main UI thread will not be interrupted by this delay, and the form will be responsive during the calculation.</span></span>

<span data-ttu-id="73a71-107">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="73a71-107">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="73a71-108">创建基于 Windows 的应用程序</span><span class="sxs-lookup"><span data-stu-id="73a71-108">Creating a Windows-based Application</span></span>

- <span data-ttu-id="73a71-109"><xref:System.ComponentModel.BackgroundWorker>在窗体中创建</span><span class="sxs-lookup"><span data-stu-id="73a71-109">Creating a <xref:System.ComponentModel.BackgroundWorker> in Your Form</span></span>

- <span data-ttu-id="73a71-110">添加异步事件处理程序</span><span class="sxs-lookup"><span data-stu-id="73a71-110">Adding Asynchronous Event Handlers</span></span>

- <span data-ttu-id="73a71-111">添加进度报告和取消支持</span><span class="sxs-lookup"><span data-stu-id="73a71-111">Adding Progress Reporting and Support for Cancellation</span></span>

<span data-ttu-id="73a71-112">若要了解此示例中使用的代码的完整列表，请参阅[如何：实现使用后台操作的窗体](how-to-implement-a-form-that-uses-a-background-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="73a71-112">For a complete listing of the code used in this example, see [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>

## <a name="create-a-form-that-uses-a-background-operation"></a><span data-ttu-id="73a71-113">创建使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="73a71-113">Create a form that uses a background operation</span></span>

1. <span data-ttu-id="73a71-114">在 visual Studio 中，创建一个名为 " `BackgroundWorkerExample` (**文件**" "  >  **新建**  >  **项目**" "  >  **Visual c #** " 或 **Visual Basic**  >  **经典桌面**  >  **Windows 窗体应用程序**) 的基于 Windows 的应用程序项目</span><span class="sxs-lookup"><span data-stu-id="73a71-114">In Visual Studio, create a Windows-based application project called `BackgroundWorkerExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="73a71-115">在“解决方案资源管理器”中，右键单击“Form1”，然后从快捷菜单中选择“重命名”。</span><span class="sxs-lookup"><span data-stu-id="73a71-115">In **Solution Explorer**, right-click **Form1** and select **Rename** from the shortcut menu.</span></span> <span data-ttu-id="73a71-116">将文件名更改为 `FibonacciCalculator`。</span><span class="sxs-lookup"><span data-stu-id="73a71-116">Change the file name to `FibonacciCalculator`.</span></span> <span data-ttu-id="73a71-117">询问是否希望重命名对代码元素“**”的所有引用时，单击“是”**`Form1`按钮。</span><span class="sxs-lookup"><span data-stu-id="73a71-117">Click the **Yes** button when you are asked if you want to rename all references to the code element '`Form1`'.</span></span>

3. <span data-ttu-id="73a71-118">将 <xref:System.Windows.Forms.NumericUpDown> 控件从 " **工具箱** " 拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="73a71-118">Drag a <xref:System.Windows.Forms.NumericUpDown> control from the **Toolbox** onto the form.</span></span> <span data-ttu-id="73a71-119">将 <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> 属性设置为 `1` ，并将 <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> 属性设置为 `91` 。</span><span class="sxs-lookup"><span data-stu-id="73a71-119">Set the <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> property to `1` and the <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> property to `91`.</span></span>

4. <span data-ttu-id="73a71-120">向窗体添加两个 <xref:System.Windows.Forms.Button> 控件。</span><span class="sxs-lookup"><span data-stu-id="73a71-120">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span>

5. <span data-ttu-id="73a71-121">重命名第一个 <xref:System.Windows.Forms.Button> 控件 `startAsyncButton` 并将 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为 `Start Async` 。</span><span class="sxs-lookup"><span data-stu-id="73a71-121">Rename the first <xref:System.Windows.Forms.Button> control `startAsyncButton` and set the <xref:System.Windows.Forms.Control.Text%2A> property to `Start Async`.</span></span> <span data-ttu-id="73a71-122">重命名第二个 <xref:System.Windows.Forms.Button> 控件 `cancelAsyncButton` ，并将 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为 `Cancel Async` 。</span><span class="sxs-lookup"><span data-stu-id="73a71-122">Rename the second <xref:System.Windows.Forms.Button> control `cancelAsyncButton`, and set the <xref:System.Windows.Forms.Control.Text%2A> property to `Cancel Async`.</span></span> <span data-ttu-id="73a71-123">将其 <xref:System.Windows.Forms.Control.Enabled%2A> 属性设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="73a71-123">Set its <xref:System.Windows.Forms.Control.Enabled%2A> property to `false`.</span></span>

6. <span data-ttu-id="73a71-124">为两个控件的事件创建一个事件处理程序 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click> 。</span><span class="sxs-lookup"><span data-stu-id="73a71-124">Create an event handler for both of the <xref:System.Windows.Forms.Button> controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="73a71-125">有关详细信息，请参阅[如何：使用设计器创建事件处理程序](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="73a71-125">For details, see [How to: Create Event Handlers Using the Designer](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

7. <span data-ttu-id="73a71-126">将 <xref:System.Windows.Forms.Label> 控件从 " **工具箱** " 拖到窗体上并将其重命名 `resultLabel` 。</span><span class="sxs-lookup"><span data-stu-id="73a71-126">Drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the form and rename it `resultLabel`.</span></span>

8. <span data-ttu-id="73a71-127">将 <xref:System.Windows.Forms.ProgressBar> 控件从 " **工具箱** " 拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="73a71-127">Drag a <xref:System.Windows.Forms.ProgressBar> control from the **Toolbox** onto the form.</span></span>

## <a name="create-a-backgroundworker-with-the-designer"></a><span data-ttu-id="73a71-128">使用设计器创建 BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="73a71-128">Create a BackgroundWorker with the Designer</span></span>

<span data-ttu-id="73a71-129">可以 <xref:System.ComponentModel.BackgroundWorker> 使用 **Windows** **窗体设计器** 创建异步操作的。</span><span class="sxs-lookup"><span data-stu-id="73a71-129">You can create the <xref:System.ComponentModel.BackgroundWorker> for your asynchronous operation using the **Windows** **Forms Designer**.</span></span>

<span data-ttu-id="73a71-130">从 "**工具箱**" 的 "**组件**" 选项卡中，将拖 <xref:System.ComponentModel.BackgroundWorker> 到窗体上。</span><span class="sxs-lookup"><span data-stu-id="73a71-130">From the **Components** tab of the **Toolbox**, drag a <xref:System.ComponentModel.BackgroundWorker> onto the form.</span></span>

## <a name="add-asynchronous-event-handlers"></a><span data-ttu-id="73a71-131">添加异步事件处理程序</span><span class="sxs-lookup"><span data-stu-id="73a71-131">Add asynchronous event handlers</span></span>

<span data-ttu-id="73a71-132">你现在可以为 <xref:System.ComponentModel.BackgroundWorker> 组件的异步事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="73a71-132">You are now ready to add event handlers for the <xref:System.ComponentModel.BackgroundWorker> component's asynchronous events.</span></span> <span data-ttu-id="73a71-133">这些事件处理程序将调用在后台运行的计算 Fibonacci 数列的耗时操作。</span><span class="sxs-lookup"><span data-stu-id="73a71-133">The time-consuming operation that will run in the background, which computes Fibonacci numbers, is called by one of these event handlers.</span></span>

1. <span data-ttu-id="73a71-134">在 " **属性** " 窗口中，如果 <xref:System.ComponentModel.BackgroundWorker> 组件仍处于选中状态，请单击 " **事件** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="73a71-134">In the **Properties** window, with the <xref:System.ComponentModel.BackgroundWorker> component still selected, click the **Events** button.</span></span> <span data-ttu-id="73a71-135">双击 <xref:System.ComponentModel.BackgroundWorker.DoWork> 和 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 事件创建事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="73a71-135">Double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span> <span data-ttu-id="73a71-136">若要深入了解如何使用事件处理程序，请参阅[如何：使用设计器创建事件处理程序](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="73a71-136">For more information about how to use event handlers, see [How to: Create Event Handlers Using the Designer](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

2. <span data-ttu-id="73a71-137">在窗体中新建一个名为 `ComputeFibonacci` 的新方法。</span><span class="sxs-lookup"><span data-stu-id="73a71-137">Create a new method, called `ComputeFibonacci`, in your form.</span></span> <span data-ttu-id="73a71-138">此方法完成实际的工作，并在后台运行。</span><span class="sxs-lookup"><span data-stu-id="73a71-138">This method does the actual work, and it will run in the background.</span></span> <span data-ttu-id="73a71-139">这些代码演示了 Fibonacci 算法的递归实现，这种算法的效率非常低，对于较大的数值花费的时间按指数增长。</span><span class="sxs-lookup"><span data-stu-id="73a71-139">This code demonstrates the recursive implementation of the Fibonacci algorithm, which is notably inefficient, taking exponentially longer time to complete for larger numbers.</span></span> <span data-ttu-id="73a71-140">在这里使用是出于演示的目的，为了说明在应用程序中某项操作可能带来长时间的延迟。</span><span class="sxs-lookup"><span data-stu-id="73a71-140">It is used here for illustrative purposes, to show an operation that can introduce long delays in your application.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]

3. <span data-ttu-id="73a71-141">在 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序中，添加对方法的调用 `ComputeFibonacci` 。</span><span class="sxs-lookup"><span data-stu-id="73a71-141">In the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler, add a call to the `ComputeFibonacci` method.</span></span> <span data-ttu-id="73a71-142">`ComputeFibonacci`从的属性中获取的第一个参数 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> <xref:System.ComponentModel.DoWorkEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="73a71-142">Take the first parameter for `ComputeFibonacci` from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span> <span data-ttu-id="73a71-143"><xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.DoWorkEventArgs> 稍后会使用和参数进行进度报告和取消支持。</span><span class="sxs-lookup"><span data-stu-id="73a71-143">The <xref:System.ComponentModel.BackgroundWorker> and <xref:System.ComponentModel.DoWorkEventArgs> parameters will be used later for progress reporting and cancellation support.</span></span> <span data-ttu-id="73a71-144">将的返回值分配 `ComputeFibonacci` 给 <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> 的属性 <xref:System.ComponentModel.DoWorkEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="73a71-144">Assign the return value from `ComputeFibonacci` to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span> <span data-ttu-id="73a71-145">此结果将可用于 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="73a71-145">This result will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

    > [!NOTE]
    > <span data-ttu-id="73a71-146"><xref:System.ComponentModel.BackgroundWorker.DoWork>事件处理程序不会直接引用 `backgroundWorker1` 实例变量，因为这会将此事件处理程序用于特定的实例 <xref:System.ComponentModel.BackgroundWorker> 。</span><span class="sxs-lookup"><span data-stu-id="73a71-146">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler does not reference the `backgroundWorker1` instance variable directly, as this would couple this event handler to a specific instance of <xref:System.ComponentModel.BackgroundWorker>.</span></span> <span data-ttu-id="73a71-147">而是 <xref:System.ComponentModel.BackgroundWorker> 从参数恢复对引发此事件的的引用 `sender` 。</span><span class="sxs-lookup"><span data-stu-id="73a71-147">Instead, a reference to the <xref:System.ComponentModel.BackgroundWorker> that raised this event is recovered from the `sender` parameter.</span></span> <span data-ttu-id="73a71-148">当窗体承载多个时，这一点非常重要 <xref:System.ComponentModel.BackgroundWorker> 。</span><span class="sxs-lookup"><span data-stu-id="73a71-148">This is important when the form hosts more than one <xref:System.ComponentModel.BackgroundWorker>.</span></span> <span data-ttu-id="73a71-149">这一点也很重要，不是在事件处理程序中操作任何用户界面对象 <xref:System.ComponentModel.BackgroundWorker.DoWork> 。</span><span class="sxs-lookup"><span data-stu-id="73a71-149">It is also important not to manipulate any user-interface objects in your <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="73a71-150">而是通过事件与用户界面通信 <xref:System.ComponentModel.BackgroundWorker> 。</span><span class="sxs-lookup"><span data-stu-id="73a71-150">Instead, communicate to the user interface through the <xref:System.ComponentModel.BackgroundWorker> events.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]

4. <span data-ttu-id="73a71-151">在 `startAsyncButton` 控件的 <xref:System.Windows.Forms.Control.Click> 事件处理程序中，添加用于启动异步操作的代码。</span><span class="sxs-lookup"><span data-stu-id="73a71-151">In the `startAsyncButton` control's <xref:System.Windows.Forms.Control.Click> event handler, add the code that starts the asynchronous operation.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]

5. <span data-ttu-id="73a71-152">在 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 事件处理程序中，将计算结果分配给 `resultLabel` 控件。</span><span class="sxs-lookup"><span data-stu-id="73a71-152">In the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler, assign the result of the calculation to the `resultLabel` control.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]

## <a name="adding-progress-reporting-and-support-for-cancellation"></a><span data-ttu-id="73a71-153">添加进度报告和取消支持</span><span class="sxs-lookup"><span data-stu-id="73a71-153">Adding Progress Reporting and Support for Cancellation</span></span>

<span data-ttu-id="73a71-154">由于异步操作将会花费很长的时间，因此通常希望向用户报告进度并允许用户取消操作。</span><span class="sxs-lookup"><span data-stu-id="73a71-154">For asynchronous operations that will take a long time, it is often desirable to report progress to the user and to allow the user to cancel the operation.</span></span> <span data-ttu-id="73a71-155"><xref:System.ComponentModel.BackgroundWorker>类提供一个事件，使您可以在后台操作继续时发布进度。</span><span class="sxs-lookup"><span data-stu-id="73a71-155">The <xref:System.ComponentModel.BackgroundWorker> class provides an event that allows you to post progress as your background operation proceeds.</span></span> <span data-ttu-id="73a71-156">它还提供了一个标志，该标志允许辅助代码检测 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 和中断自身。</span><span class="sxs-lookup"><span data-stu-id="73a71-156">It also provides a flag that allows your worker code to detect a call to <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> and interrupt itself.</span></span>

### <a name="implement-progress-reporting"></a><span data-ttu-id="73a71-157">实现进度报告</span><span class="sxs-lookup"><span data-stu-id="73a71-157">Implement progress reporting</span></span>

1. <span data-ttu-id="73a71-158">在“属性”窗口中，选择 `backgroundWorker1`。</span><span class="sxs-lookup"><span data-stu-id="73a71-158">In the **Properties**, window, select `backgroundWorker1`.</span></span> <span data-ttu-id="73a71-159">将 <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> 和 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="73a71-159">Set the <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span>

2. <span data-ttu-id="73a71-160">在 `FibonacciCalculator` 窗体中声明两个变量。</span><span class="sxs-lookup"><span data-stu-id="73a71-160">Declare two variables in the `FibonacciCalculator` form.</span></span> <span data-ttu-id="73a71-161">这将用于跟踪进度。</span><span class="sxs-lookup"><span data-stu-id="73a71-161">These will be used to track progress.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]

3. <span data-ttu-id="73a71-162">为 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="73a71-162">Add an event handler for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span> <span data-ttu-id="73a71-163">在 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 事件处理程序中， <xref:System.Windows.Forms.ProgressBar> 用参数的 <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> 属性更新 <xref:System.ComponentModel.ProgressChangedEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="73a71-163">In the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler, update the <xref:System.Windows.Forms.ProgressBar> with the <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> property of the <xref:System.ComponentModel.ProgressChangedEventArgs> parameter.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]

### <a name="implement-support-for-cancellation"></a><span data-ttu-id="73a71-164">实现对取消的支持</span><span class="sxs-lookup"><span data-stu-id="73a71-164">Implement support for cancellation</span></span>

1. <span data-ttu-id="73a71-165">在 `cancelAsyncButton` 控件的 <xref:System.Windows.Forms.Control.Click> 事件处理程序中，添加取消异步操作的代码。</span><span class="sxs-lookup"><span data-stu-id="73a71-165">In the `cancelAsyncButton` control's <xref:System.Windows.Forms.Control.Click> event handler, add the code that cancels the asynchronous operation.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]

2. <span data-ttu-id="73a71-166">下面的 `ComputeFibonacci` 方法中的代码片段可报告进程并支持取消。</span><span class="sxs-lookup"><span data-stu-id="73a71-166">The following code fragments in the `ComputeFibonacci` method report progress and support cancellation.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]

## <a name="checkpoint"></a><span data-ttu-id="73a71-167">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="73a71-167">Checkpoint</span></span>

<span data-ttu-id="73a71-168">此时，可以编译并运行 Fibonacci 计算器应用程序。</span><span class="sxs-lookup"><span data-stu-id="73a71-168">At this point, you can compile and run the Fibonacci Calculator application.</span></span>

<span data-ttu-id="73a71-169">按 **F5** 编译并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="73a71-169">Press **F5** to compile and run the application.</span></span>

<span data-ttu-id="73a71-170">当计算在后台运行时，您将看到 <xref:System.Windows.Forms.ProgressBar> 显示完成计算的进度。</span><span class="sxs-lookup"><span data-stu-id="73a71-170">While the calculation is running in the background, you will see the <xref:System.Windows.Forms.ProgressBar> displaying the progress of the calculation toward completion.</span></span> <span data-ttu-id="73a71-171">也可以取消挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="73a71-171">You can also cancel the pending operation.</span></span>

<span data-ttu-id="73a71-172">对于较小数值，计算应非常快，但对于较大数值，将看到明显的延时。</span><span class="sxs-lookup"><span data-stu-id="73a71-172">For small numbers, the calculation should be very fast, but for larger numbers, you should see a noticeable delay.</span></span> <span data-ttu-id="73a71-173">如果输入 30 或更大的值，应看到有几秒钟的延时，这取决于计算机的速度。</span><span class="sxs-lookup"><span data-stu-id="73a71-173">If you enter a value of 30 or greater, you should see a delay of several seconds, depending on the speed of your computer.</span></span> <span data-ttu-id="73a71-174">对于大于 40 的值，完成计算可能要花费数分钟或数小时。</span><span class="sxs-lookup"><span data-stu-id="73a71-174">For values greater than 40, it may take minutes or hours to finish the calculation.</span></span> <span data-ttu-id="73a71-175">在计算器计算较大的 Fibonacci 数列时，注意可以自由地移动窗体、最小化、最大化甚至关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="73a71-175">While the calculator is busy computing a large Fibonacci number, notice that you can freely move the form around, minimize, maximize, and even dismiss it.</span></span> <span data-ttu-id="73a71-176">这是因为主 UI 线程不会等待计算完成。</span><span class="sxs-lookup"><span data-stu-id="73a71-176">This is because the main UI thread is not waiting for the calculation to finish.</span></span>

## <a name="next-steps"></a><span data-ttu-id="73a71-177">后续步骤</span><span class="sxs-lookup"><span data-stu-id="73a71-177">Next steps</span></span>

<span data-ttu-id="73a71-178">现在您已实现了一个窗体，该窗体使用 <xref:System.ComponentModel.BackgroundWorker> 组件在后台执行计算，接下来可以了解异步操作的其他可能性：</span><span class="sxs-lookup"><span data-stu-id="73a71-178">Now that you have implemented a form that uses a <xref:System.ComponentModel.BackgroundWorker> component to execute a computation in the background, you can explore other possibilities for asynchronous operations:</span></span>

- <span data-ttu-id="73a71-179">为多个并发操作使用多个 <xref:System.ComponentModel.BackgroundWorker> 对象。</span><span class="sxs-lookup"><span data-stu-id="73a71-179">Use multiple <xref:System.ComponentModel.BackgroundWorker> objects for several simultaneous operations.</span></span>

- <span data-ttu-id="73a71-180">若要调试多线程应用程序，请参阅[如何：使用“线程”窗口](/visualstudio/debugger/how-to-use-the-threads-window)。</span><span class="sxs-lookup"><span data-stu-id="73a71-180">To debug your multithreaded application, see [How to: Use the Threads Window](/visualstudio/debugger/how-to-use-the-threads-window).</span></span>

- <span data-ttu-id="73a71-181">实现自己的支持异步编程模式的组件。</span><span class="sxs-lookup"><span data-stu-id="73a71-181">Implement your own component that supports the asynchronous programming model.</span></span> <span data-ttu-id="73a71-182">有关详细信息，请参阅[基于事件的异步模式概述](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)。</span><span class="sxs-lookup"><span data-stu-id="73a71-182">For more information, see [Event-based Asynchronous Pattern Overview](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview).</span></span>

    > [!CAUTION]
    > <span data-ttu-id="73a71-183">使用任何一种多线程都可能引起极为严重和复杂的 Bug。</span><span class="sxs-lookup"><span data-stu-id="73a71-183">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="73a71-184">在实现任何使用多线程处理的解决方案之前，请参阅[托管线程处理最佳做法](/dotnet/standard/threading/managed-threading-best-practices)。</span><span class="sxs-lookup"><span data-stu-id="73a71-184">Consult the [Managed Threading Best Practices](/dotnet/standard/threading/managed-threading-best-practices) before implementing any solution that uses multithreading.</span></span>

## <a name="see-also"></a><span data-ttu-id="73a71-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73a71-185">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- [<span data-ttu-id="73a71-186">托管线程</span><span class="sxs-lookup"><span data-stu-id="73a71-186">Managed Threading</span></span>](/dotnet/standard/threading/index)
- [<span data-ttu-id="73a71-187">托管线程处理的最佳做法</span><span class="sxs-lookup"><span data-stu-id="73a71-187">Managed Threading Best Practices</span></span>](/dotnet/standard/threading/managed-threading-best-practices)
- [<span data-ttu-id="73a71-188">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="73a71-188">Event-based Asynchronous Pattern Overview</span></span>](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)
- [<span data-ttu-id="73a71-189">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="73a71-189">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="73a71-190">演练：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="73a71-190">Walkthrough: Running an Operation in the Background</span></span>](walkthrough-running-an-operation-in-the-background.md)
- [<span data-ttu-id="73a71-191">BackgroundWorker 组件</span><span class="sxs-lookup"><span data-stu-id="73a71-191">BackgroundWorker Component</span></span>](backgroundworker-component.md)
