---
title: 演练：在运行时更新状态栏信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
ms.openlocfilehash: a58f8698af95810e4f716aa2b105bb86be3f55e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972493"
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a><span data-ttu-id="4dc92-102">演练：在运行时更新状态栏信息</span><span class="sxs-lookup"><span data-stu-id="4dc92-102">Walkthrough: Updating Status Bar Information at Run Time</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4dc92-103"><xref:System.Windows.Forms.StatusStrip>和 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件替换和添加了 <xref:System.Windows.Forms.StatusBar> 和控件的功能 <xref:System.Windows.Forms.StatusBarPanel> ; 但是， <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> 如果你选择，和控件将保留以实现向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="4dc92-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="4dc92-104">通常情况下，程序会要求根据应用程序状态的更改或其他用户交互情况，在运行时动态更新状态栏面板的内容。</span><span class="sxs-lookup"><span data-stu-id="4dc92-104">Often, a program will call for you to update the contents of status bar panels dynamically at run time, based on changes to application state or other user interaction.</span></span> <span data-ttu-id="4dc92-105">这是一种用于执行以下任务的常用方式：通知用户启用了 CAPS LOCK、NUM LOCK 或 SCROLL LOCK 之类的键，或者将日期或时钟作为方便的引用提供。</span><span class="sxs-lookup"><span data-stu-id="4dc92-105">This is a common way to signal users that keys such as the CAPS LOCK, NUM LOCK, or SCROLL LOCK are enabled, or to provide the date or a clock as a convenient reference.</span></span>  
  
 <span data-ttu-id="4dc92-106">在下面的示例中，将使用类的实例 <xref:System.Windows.Forms.StatusBarPanel> 来承载时钟。</span><span class="sxs-lookup"><span data-stu-id="4dc92-106">In the following example, you will use an instance of the <xref:System.Windows.Forms.StatusBarPanel> class to host a clock.</span></span>  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a><span data-ttu-id="4dc92-107">准备更新状态栏</span><span class="sxs-lookup"><span data-stu-id="4dc92-107">To get the status bar ready for updating</span></span>  
  
1. <span data-ttu-id="4dc92-108">创建新的 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="4dc92-108">Create a new Windows form.</span></span>  
  
2. <span data-ttu-id="4dc92-109">向窗体添加一个 <xref:System.Windows.Forms.StatusBar> 控件。</span><span class="sxs-lookup"><span data-stu-id="4dc92-109">Add a <xref:System.Windows.Forms.StatusBar> control to your form.</span></span> <span data-ttu-id="4dc92-110">有关详细信息，请参阅[如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="4dc92-110">For details, see [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
3. <span data-ttu-id="4dc92-111">将状态栏面板添加到 <xref:System.Windows.Forms.StatusBar> 控件。</span><span class="sxs-lookup"><span data-stu-id="4dc92-111">Add a status bar panel to your <xref:System.Windows.Forms.StatusBar> control.</span></span> <span data-ttu-id="4dc92-112">有关详细信息，请参阅[如何：向 StatusBar 控件添加面板](how-to-add-panels-to-a-statusbar-control.md)。</span><span class="sxs-lookup"><span data-stu-id="4dc92-112">For details, see [How to: Add Panels to a StatusBar Control](how-to-add-panels-to-a-statusbar-control.md).</span></span>  
  
4. <span data-ttu-id="4dc92-113">对于 <xref:System.Windows.Forms.StatusBar> 已添加到窗体的控件，将 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="4dc92-113">For the <xref:System.Windows.Forms.StatusBar> control you added to your form, set the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true`.</span></span>  
  
5. <span data-ttu-id="4dc92-114">将 Windows 窗体 <xref:System.Windows.Forms.Timer> 组件添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="4dc92-114">Add a Windows Forms <xref:System.Windows.Forms.Timer> component to the form.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4dc92-115">Windows 窗体 <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> 组件是为 Windows 窗体环境设计的。</span><span class="sxs-lookup"><span data-stu-id="4dc92-115">The Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="4dc92-116">如果需要适合服务器环境的计时器，请参阅[基于服务器的计时器介绍](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="4dc92-116">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
6. <span data-ttu-id="4dc92-117">将 <xref:System.Windows.Forms.Timer.Enabled%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="4dc92-117">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>  
  
7. <span data-ttu-id="4dc92-118">将 <xref:System.Windows.Forms.Timer.Interval%2A> 的属性设置 <xref:System.Windows.Forms.Timer> 为30000。</span><span class="sxs-lookup"><span data-stu-id="4dc92-118">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> to 30000.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4dc92-119"><xref:System.Windows.Forms.Timer.Interval%2A>组件的属性 <xref:System.Windows.Forms.Timer> 设置为30秒 (30000 毫秒) ，以确保在显示的时间内反映准确的时间。</span><span class="sxs-lookup"><span data-stu-id="4dc92-119">The <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> component is set to 30 seconds (30,000 milliseconds) to ensure that an accurate time is reflected in the time displayed.</span></span>  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a><span data-ttu-id="4dc92-120">通过实现计时器更新状态栏</span><span class="sxs-lookup"><span data-stu-id="4dc92-120">To implement the timer to update the status bar</span></span>  
  
1. <span data-ttu-id="4dc92-121">将以下代码插入组件的事件处理程序中 <xref:System.Windows.Forms.Timer> ，以更新控件的面板 <xref:System.Windows.Forms.StatusBar> 。</span><span class="sxs-lookup"><span data-stu-id="4dc92-121">Insert the following code into the event handler of the <xref:System.Windows.Forms.Timer> component to update the panel of the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     <span data-ttu-id="4dc92-122">此时，就可以运行该应用程序并观察在状态栏面板中运行的时钟。</span><span class="sxs-lookup"><span data-stu-id="4dc92-122">At this point, you are ready to run the application and observe the clock running in the status bar panel.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="4dc92-123">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="4dc92-123">To test the application</span></span>  
  
1. <span data-ttu-id="4dc92-124">调试该应用程序，然后按 F5 运行。</span><span class="sxs-lookup"><span data-stu-id="4dc92-124">Debug the application and press F5 to run it.</span></span> <span data-ttu-id="4dc92-125">有关调试的详细信息，请参阅[在 Visual Studio 中进行调试](/visualstudio/debugger/debugger-feature-tour)。</span><span class="sxs-lookup"><span data-stu-id="4dc92-125">For details about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugger-feature-tour).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4dc92-126">大约 30 秒之后，时钟才会出现在状态栏上。</span><span class="sxs-lookup"><span data-stu-id="4dc92-126">It will take approximately 30 seconds for the clock to appear in the status bar.</span></span> <span data-ttu-id="4dc92-127">这样可以获得最精确的时间。</span><span class="sxs-lookup"><span data-stu-id="4dc92-127">This is to get the most accurate time possible.</span></span> <span data-ttu-id="4dc92-128">相反，若要使时钟更快出现，可以减少 <xref:System.Windows.Forms.Timer.Interval%2A> 上一过程的步骤7中设置的属性值。</span><span class="sxs-lookup"><span data-stu-id="4dc92-128">Conversely, to make the clock appear sooner, you can reduce the value of the <xref:System.Windows.Forms.Timer.Interval%2A> property you set in step 7 in the previous procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc92-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4dc92-129">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="4dc92-130">如何：向 StatusBar 控件添加面板</span><span class="sxs-lookup"><span data-stu-id="4dc92-130">How to: Add Panels to a StatusBar Control</span></span>](how-to-add-panels-to-a-statusbar-control.md)
- [<span data-ttu-id="4dc92-131">如何：确定 Windows 窗体 StatusBar 控件中被单击的面板</span><span class="sxs-lookup"><span data-stu-id="4dc92-131">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [<span data-ttu-id="4dc92-132">StatusBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="4dc92-132">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
