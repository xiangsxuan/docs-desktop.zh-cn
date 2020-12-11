---
title: 确定 RichTextBox 控件中格式属性的更改时间
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
ms.openlocfilehash: a190c3479b58464763e0eefdd32d14e88a1f05e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970085"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>如何：确定 Windows 窗体 RichTextBox 控件中的格式设置特性何时更改
Windows 窗体控件的常见用法 <xref:System.Windows.Forms.RichTextBox> 是使用字体选项或段落样式之类的属性设置文本格式。 您的应用程序可能需要跟踪文本格式设置的任何更改，以便显示工具栏，这与在许多字处理应用程序中一样。  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>响应格式设置特性的更改  
  
1. 在 <xref:System.Windows.Forms.RichTextBox.SelectionChanged> 事件处理程序中编写代码，以根据属性的值执行适当的操作。 下面的示例根据属性的值更改工具栏按钮的外观 <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 。 只有在插入点移动到控件中时，工具栏按钮才会更新。  
  
     下面的示例假设窗体具有一个 <xref:System.Windows.Forms.RichTextBox> 控件和一个 <xref:System.Windows.Forms.ToolBar> 包含工具栏按钮的控件。 有关工具栏和工具栏按钮的详细信息，请参阅 [如何：将按钮添加到工具栏控件](how-to-add-buttons-to-a-toolbar-control.md)。  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 控件](richtextbox-control-windows-forms.md)
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
