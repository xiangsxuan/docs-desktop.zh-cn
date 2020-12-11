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
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a>演练：在运行时更新状态栏信息

> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusStrip>和 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件替换和添加了 <xref:System.Windows.Forms.StatusBar> 和控件的功能 <xref:System.Windows.Forms.StatusBarPanel> ; 但是， <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> 如果你选择，和控件将保留以实现向后兼容性和将来使用。  
  
 通常情况下，程序会要求根据应用程序状态的更改或其他用户交互情况，在运行时动态更新状态栏面板的内容。 这是一种用于执行以下任务的常用方式：通知用户启用了 CAPS LOCK、NUM LOCK 或 SCROLL LOCK 之类的键，或者将日期或时钟作为方便的引用提供。  
  
 在下面的示例中，将使用类的实例 <xref:System.Windows.Forms.StatusBarPanel> 来承载时钟。  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a>准备更新状态栏  
  
1. 创建新的 Windows 窗体。  
  
2. 向窗体添加一个 <xref:System.Windows.Forms.StatusBar> 控件。 有关详细信息，请参阅[如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)。  
  
3. 将状态栏面板添加到 <xref:System.Windows.Forms.StatusBar> 控件。 有关详细信息，请参阅[如何：向 StatusBar 控件添加面板](how-to-add-panels-to-a-statusbar-control.md)。  
  
4. 对于 <xref:System.Windows.Forms.StatusBar> 已添加到窗体的控件，将 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 属性设置为 `true` 。  
  
5. 将 Windows 窗体 <xref:System.Windows.Forms.Timer> 组件添加到窗体。  
  
    > [!NOTE]
    > Windows 窗体 <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> 组件是为 Windows 窗体环境设计的。 如果需要适合服务器环境的计时器，请参阅[基于服务器的计时器介绍](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))。  
  
6. 将 <xref:System.Windows.Forms.Timer.Enabled%2A> 属性设置为 `true`。  
  
7. 将 <xref:System.Windows.Forms.Timer.Interval%2A> 的属性设置 <xref:System.Windows.Forms.Timer> 为30000。  
  
    > [!NOTE]
    > <xref:System.Windows.Forms.Timer.Interval%2A>组件的属性 <xref:System.Windows.Forms.Timer> 设置为30秒 (30000 毫秒) ，以确保在显示的时间内反映准确的时间。  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a>通过实现计时器更新状态栏  
  
1. 将以下代码插入组件的事件处理程序中 <xref:System.Windows.Forms.Timer> ，以更新控件的面板 <xref:System.Windows.Forms.StatusBar> 。  
  
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
  
     此时，就可以运行该应用程序并观察在状态栏面板中运行的时钟。  
  
### <a name="to-test-the-application"></a>测试应用程序  
  
1. 调试该应用程序，然后按 F5 运行。 有关调试的详细信息，请参阅[在 Visual Studio 中进行调试](/visualstudio/debugger/debugger-feature-tour)。  
  
    > [!NOTE]
    > 大约 30 秒之后，时钟才会出现在状态栏上。 这样可以获得最精确的时间。 相反，若要使时钟更快出现，可以减少 <xref:System.Windows.Forms.Timer.Interval%2A> 上一过程的步骤7中设置的属性值。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [如何：向 StatusBar 控件添加面板](how-to-add-panels-to-a-statusbar-control.md)
- [如何：确定 Windows 窗体 StatusBar 控件中被单击的面板](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [StatusBar 控件概述](statusbar-control-overview-windows-forms.md)
