---
title: 如何：使用 FontDialog 组件显示字体列表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
ms.openlocfilehash: 05e9b5e1280d0318354b0d47f4d78f7ec1c5f4e7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972650"
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a>如何：使用 FontDialog 组件显示字体列表
使用 [FontDialog](fontdialog-component-windows-forms.md) 组件，用户可以选择字体，还可以更改其显示的方位，如粗细和大小。  
  
 对话框中选择的字体将在属性中返回 <xref:System.Windows.Forms.FontDialog.Font%2A> 。 因此，利用用户选择的字体与读取属性一样简单。  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a>使用 FontDialog 组件选择字体属性  
  
1. 使用方法显示对话框 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 。  
  
2. 使用 <xref:System.Windows.Forms.DialogResult> 属性可确定对话框的关闭方式。  
  
3. 使用 " <xref:System.Windows.Forms.FontDialog.Font%2A> 属性" 设置所需的字体。  
  
     在下面的示例中， <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Click> 事件处理程序将打开一个 <xref:System.Windows.Forms.FontDialog> 组件。 如果选择字体，并且用户单击 **"确定"**， <xref:System.Windows.Forms.FontDialog.Font%2A> <xref:System.Windows.Forms.TextBox> 则窗体上的控件的属性将设置为所选字体。 该示例假设窗体具有一个 <xref:System.Windows.Forms.Button> 控件、一个  <xref:System.Windows.Forms.TextBox> 控件和一个 <xref:System.Windows.Forms.FontDialog> 组件。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
      (Visual c # 和 Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.FontDialog>
- [FontDialog 组件](fontdialog-component-windows-forms.md)
