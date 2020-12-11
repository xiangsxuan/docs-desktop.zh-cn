---
title: 控制 TextBox 控件中的插入点
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: fd4803820921f0c922a4ce885f809abee8fd4c6c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971882"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>如何：控制 Windows 窗体 TextBox 控件中的插入点
当 Windows 窗体 <xref:System.Windows.Forms.TextBox> 控件首次接收焦点时，文本框中的默认插入将位于任何现有文本的左侧。 用户可以通过键盘或鼠标移动插入点。 如果该文本框丢失，然后又重新获得焦点，则插入点将是用户最后放置它的位置。  
  
 在某些情况下，此行为可能会不安用户。 在字处理应用程序中，用户可能会希望新字符出现在任何现有文本之后。 在数据输入应用程序中，用户可能希望使用新字符来替换任何现有条目。 使用 <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 和 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 属性可以修改行为以满足你的目的。  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>控制 TextBox 控件中的插入点  
  
1. 将 <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 属性设置为适当的值。 如果为零，则将插入点放在第一个字符的左侧。  
  
2.  (可选) 将 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 属性设置为要选择的文本长度。  
  
     下面的代码始终将插入点返回到0。 `TextBox1_Enter`事件处理程序必须绑定到控件; 有关详细信息，请参阅[在 Windows 窗体中创建事件处理程序](../creating-event-handlers-in-windows-forms.md)。  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a>使插入点在默认情况下可见  
 <xref:System.Windows.Forms.TextBox>默认情况下，仅当 <xref:System.Windows.Forms.TextBox> 控件是 tab 键顺序中的第一个时，插入点才会显示在新窗体中。 否则，只有在您 <xref:System.Windows.Forms.TextBox> 通过键盘或鼠标为焦点时，才会显示插入点。  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>使文本框插入点在默认情况下在新窗体上可见  
  
- 将 <xref:System.Windows.Forms.TextBox> 控件的 <xref:System.Windows.Forms.Control.TabIndex%2A> 属性设置为 `0` 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.TextBox>
- [TextBox 控件概述](textbox-control-overview-windows-forms.md)
- [如何：使用 Windows 窗体 TextBox 控件创建密码文本框](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [如何：创建只读文本框](how-to-create-a-read-only-text-box-windows-forms.md)
- [如何：在字符串中添加引号](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [如何：在 Windows 窗体 TextBox 控件中选择文本](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [如何：在 Windows 窗体 TextBox 控件中查看多个行](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox 控件](textbox-control-windows-forms.md)
