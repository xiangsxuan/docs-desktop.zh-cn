---
title: 如何：设置状态栏面板的大小
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- StatusBar control [Windows Forms], panel size
- status bars [Windows Forms], setting panel size
- panels [Windows Forms], setting size in status bars
ms.assetid: a01bee43-d9eb-4954-84e6-45a93532d08d
ms.openlocfilehash: 4ba0f7f02b548a5d9ea1a99605a668f449b3e4a9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972562"
---
# <a name="how-to-set-the-size-of-status-bar-panels"></a><span data-ttu-id="7ee62-102">如何：设置状态栏面板的大小</span><span class="sxs-lookup"><span data-stu-id="7ee62-102">How to: Set the Size of Status-Bar Panels</span></span>
> [!NOTE]
> <span data-ttu-id="7ee62-103"><xref:System.Windows.Forms.ToolStripStatusLabel> 控件取代了 <xref:System.Windows.Forms.StatusBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.StatusBar> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="7ee62-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="7ee62-104">出现在 <xref:System.Windows.Forms.StatusBarPanel> [状态栏控件](statusbar-control-windows-forms.md) 控件中的类的每个实例都有多个动态属性，这些属性确定了其在运行时的宽度和大小调整行为。</span><span class="sxs-lookup"><span data-stu-id="7ee62-104">Each instance of the <xref:System.Windows.Forms.StatusBarPanel> class within a [StatusBar Control](statusbar-control-windows-forms.md) control has a number of dynamic properties that determine its width and resize behavior at run time.</span></span>  
  
### <a name="to-set-the-size-of-a-panel"></a><span data-ttu-id="7ee62-105">设置面板的大小</span><span class="sxs-lookup"><span data-stu-id="7ee62-105">To set the size of a panel</span></span>  
  
1. <span data-ttu-id="7ee62-106">在过程中，使用通过 <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A> 集合的属性传递的索引，设置、 <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A> 和 <xref:System.Windows.Forms.StatusBarPanel.Width%2A> 属性 (或状态栏面板) 的任何子集 <xref:System.Windows.Forms.StatusBar.Panels%2A> <xref:System.Windows.Forms.StatusBarPanel> 。</span><span class="sxs-lookup"><span data-stu-id="7ee62-106">In a procedure, set the <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, and <xref:System.Windows.Forms.StatusBarPanel.Width%2A> properties (or any subset therein) for the status-bar panels using their index passed through the <xref:System.Windows.Forms.StatusBar.Panels%2A> property of the <xref:System.Windows.Forms.StatusBarPanel> collection.</span></span>  
  
    ```vb  
    Public Sub SetStatusBarPanelSize()  
    ' Create panel and set text property.  
       StatusBar1.Panels.Add("One")  
    ' Set properties of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(0).Width = 200  
    ' Enable the StatusBar control to display panels.  
       StatusBar1.ShowPanels = True  
        End Sub  
    ```  
  
    ```csharp  
    public void SetStatusBarPanelSize()  
    {  
       // Create panel and set text property.  
       statusBar1.Panels.Add("One");  
       // Set properties of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[0].Width = 200;  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void SetStatusBarPanelSize()  
       {  
          // Create panel and set text property.  
          statusBar1->Panels->Add("One");  
          // Set properties of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[0]->Width = 200;  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7ee62-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ee62-107">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="7ee62-108">演练：在运行时更新状态栏信息</span><span class="sxs-lookup"><span data-stu-id="7ee62-108">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="7ee62-109">如何：确定 Windows 窗体 StatusBar 控件中被单击的面板</span><span class="sxs-lookup"><span data-stu-id="7ee62-109">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [<span data-ttu-id="7ee62-110">StatusBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="7ee62-110">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
