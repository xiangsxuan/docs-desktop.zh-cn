---
title: 确定单击了状态栏控件中的哪个面板
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: eb3b10d515ba5b62236594e063ca7f060b34b73e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970084"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>如何：确定 Windows 窗体 StatusBar 控件中被单击的面板
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusStrip>和 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件替换和添加了 <xref:System.Windows.Forms.StatusBar> 和控件的功能 <xref:System.Windows.Forms.StatusBarPanel> ; 但是， <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> 如果你选择，和控件将保留以实现向后兼容性和将来使用。  
  
 若要对 " [状态栏" 控件](statusbar-control-windows-forms.md) 控件进行编程以响应用户单击，请在事件中使用 case 语句 <xref:System.Windows.Forms.StatusBar.PanelClick> 。 事件包含参数 (面板参数) ，其中包含对单击的的引用 <xref:System.Windows.Forms.StatusBarPanel> 。 使用此引用，可以确定所单击的面板的索引，并相应地进行编程。  
  
> [!NOTE]
> 确保 <xref:System.Windows.Forms.StatusBar> 将控件的 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 属性设置为 `true` 。  
  
### <a name="to-determine-which-panel-was-clicked"></a>确定单击了哪个面板  
  
1. 在 <xref:System.Windows.Forms.StatusBar.PanelClick> 事件处理程序中，使用 `Select Case` Visual Basic) 或 `switch case` (Visual c # 或 Visual C++) 语句中的 (，通过检查事件参数中单击的面板的索引来确定单击了哪个面板。  
  
     下面的代码示例需要 <xref:System.Windows.Forms.StatusBar> 控件、和 `StatusBar1` 两个对象的状态（ <xref:System.Windows.Forms.StatusBarPanel> `StatusBarPanel1` 和） `StatusBarPanel2` 。  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
      (Visual c # 中，Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.statusBar1.PanelClick += new
       System.Windows.Forms.StatusBarPanelClickEventHandler
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [如何：设置状态栏面板的大小](how-to-set-the-size-of-status-bar-panels.md)
- [演练：在运行时更新状态栏信息](walkthrough-updating-status-bar-information-at-run-time.md)
- [StatusBar 控件概述](statusbar-control-overview-windows-forms.md)
