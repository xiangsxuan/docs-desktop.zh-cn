---
title: 如何：确定活动的 MDI 子窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
ms.openlocfilehash: 57491faa10c182630d41565ba236d65e393929b3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970314"
---
# <a name="how-to-determine-the-active-mdi-child"></a>如何：确定活动的 MDI 子窗体
有时，您需要提供一个命令，该命令对在当前活动的子窗体上具有焦点的控件进行操作。 例如，假设您想要将选定的文本从子窗体的文本框复制到剪贴板。 您将创建一个过程，该过程使用 " <xref:System.Windows.Forms.Control.Click> 标准编辑" 菜单上的 "复制" 菜单项的事件将选定文本复制到剪贴板。  
  
 因为一个 MDI 应用程序可以有多个相同子窗体的实例，所以该过程需要知道要使用哪一个窗体。 若要指定正确的窗体，请使用 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 属性，该属性返回具有焦点或最近活动的子窗体。  
  
 当窗体上有多个控件时，还需要指定哪个控件处于活动状态。 与 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 属性一样， <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> 属性返回具有活动子窗体上焦点的控件。 下面的过程演示了可从子窗体菜单、MDI 窗体上的菜单或工具栏按钮调用的复制过程。  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>若要确定活动的 MDI 子 (以便将其文本复制到剪贴板)   
  
1. 在方法中，将活动子窗体的活动控件的文本复制到剪贴板。  
  
    > [!NOTE]
    > 此示例假设有一个 MDI 父窗体 (`Form1`) 包含一个或多个包含控件的 MDI 子窗口 <xref:System.Windows.Forms.RichTextBox> 。 有关详细信息，请参阅 [创建 MDI 父窗体](how-to-create-mdi-parent-forms.md)。  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a>另请参阅

- [多文档界面 (MDI) 应用程序](multiple-document-interface-mdi-applications.md)
- [如何：创建 MDI 父窗体](how-to-create-mdi-parent-forms.md)
- [如何：创建 MDI 子窗体](how-to-create-mdi-child-forms.md)
- [如何：将数据发送到活动的 MDI 子窗体](how-to-send-data-to-the-active-mdi-child.md)
- [如何：排列 MDI 子窗体](how-to-arrange-mdi-child-forms.md)
