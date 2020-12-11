---
title: 使用 RichTextBox 控件启用拖放操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- drag and drop [Windows Forms], richTextBox control
- text boxes [Windows Forms], drag-and-drop operations
- RichTextBox control [Windows Forms], drag-and-drop operations
ms.assetid: ca167d1c-2014-4cf0-96a0-20598470be3b
ms.openlocfilehash: 27e5c18598552c465ef17f5e58069bc10e401c09
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971318"
---
# <a name="how-to-enable-drag-and-drop-operations-with-the-windows-forms-richtextbox-control"></a>如何：使用 Windows 窗体 RichTextBox 控件启用拖放操作
通过处理 <xref:System.Windows.Forms.RichTextBox> 和 <xref:System.Windows.Forms.RichTextBox.DragEnter> 事件，在 Windows 窗体 <xref:System.Windows.Forms.RichTextBox.DragDrop> 控件中进行拖放操作。 因此，在 <xref:System.Windows.Forms.RichTextBox> 控件中进行拖放操作是非常简单的。  
  
### <a name="to-enable-drag-operations-in-a-richtextbox-control"></a>在 RichTextBox 控件中实现拖动操作  
  
1. 将 <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> 控件的 <xref:System.Windows.Forms.RichTextBox> 属性设置为 `true`。  
  
2. 在 <xref:System.Windows.Forms.RichTextBox.DragEnter> 事件的事件处理程序中编写代码。 使用 `if` 语句来确保要拖动的数据为可接受的类型（本例为文本）。 <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> 属性可以设置为 <xref:System.Windows.Forms.DragDropEffects> 枚举的任何值。  
  
    ```vb  
    Private Sub RichTextBox1_DragEnter(ByVal sender As Object, _
       ByVal e As System.Windows.Forms.DragEventArgs) _
       Handles RichTextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
          e.Effect = DragDropEffects.Copy  
       Else  
          e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragEnter(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    ```cpp  
    private:  
       void richTextBox1_DragEnter(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          if (e->Data->GetDataPresent(DataFormats::Text))  
             e->Effect = DragDropEffects::Copy;  
          else  
             e->Effect = DragDropEffects::None;  
       }  
    ```  
  
      (Visual c # 和 Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.richTextBox1.DragEnter += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragEnter);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragEnter += gcnew  
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragEnter);  
    ```  
  
3. 编写代码以处理 <xref:System.Windows.Forms.RichTextBox.DragDrop> 事件。 使用 <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> 方法来检索要拖动的数据。  
  
     在下面的示例中，代码会将 <xref:System.Windows.Forms.RichTextBox.Text%2A> 控件的 <xref:System.Windows.Forms.RichTextBox> 属性设置为等于要拖动的数据。 如果 <xref:System.Windows.Forms.RichTextBox> 控件中已有文本，拖动的文本将插入到插入点。  
  
    ```vb  
    Private Sub RichTextBox1_DragDrop(ByVal sender As Object, _
       ByVal e As System.Windows.Forms.DragEventArgs) _
       Handles RichTextBox1.DragDrop  
       Dim i As Int16
       Dim s As String  
  
       ' Get start position to drop the text.  
       i = RichTextBox1.SelectionStart  
       s = RichTextBox1.Text.Substring(i)  
       RichTextBox1.Text = RichTextBox1.Text.Substring(0, i)  
  
       ' Drop the text on to the RichTextBox.  
       RichTextBox1.Text = RichTextBox1.Text + _  
          e.Data.GetData(DataFormats.Text).ToString()  
       RichTextBox1.Text = RichTextBox1.Text + s  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragDrop(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       int i;  
       String s;  
  
       // Get start position to drop the text.  
       i = richTextBox1.SelectionStart;  
       s = richTextBox1.Text.Substring(i);  
       richTextBox1.Text = richTextBox1.Text.Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       richTextBox1.Text = richTextBox1.Text +
          e.Data.GetData(DataFormats.Text).ToString();  
       richTextBox1.Text = richTextBox1.Text + s;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void richTextBox1_DragDrop(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          int i;  
          String ^s;  
  
       // Get start position to drop the text.  
       i = richTextBox1->SelectionStart;  
       s = richTextBox1->Text->Substring(i);  
       richTextBox1->Text = richTextBox1->Text->Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       String ^str = String::Concat(richTextBox1->Text, e->Data  
       ->GetData(DataFormats->Text)->ToString());
       richTextBox1->Text = String::Concat(str, s);  
       }  
    ```  
  
      (Visual c # 和 Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.richTextBox1.DragDrop += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragDrop);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragDrop += gcnew
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragDrop);  
    ```  
  
### <a name="to-test-the-drag-and-drop-functionality-in-your-application"></a>测试应用程序中的拖放功能  
  
1. 保存并生成应用程序。 在运行期间，运行写字板。  
  
     写字板是由 Windows 安装的允许拖放操作的文本编辑器。 可以通过单击“开始”  按钮，选择“运行” ，在“运行” `WordPad`**对话框的文本框中键入** ，然后单击“确定” 来访问它。  
  
2. 打开写字板后，在其中键入文本字符串。 使用鼠标选择该文本，然后将所选的文本拖到 Windows 应用程序中的 <xref:System.Windows.Forms.RichTextBox> 控件之上。  
  
     注意，将鼠标移到 <xref:System.Windows.Forms.RichTextBox> 控件上（并因此引发 <xref:System.Windows.Forms.RichTextBox.DragEnter> 事件）时，鼠标指针会改变，可以将所选的文本放入 <xref:System.Windows.Forms.RichTextBox> 控件。  
  
     释放鼠标按钮，所选文本将放开（也就是引发 <xref:System.Windows.Forms.RichTextBox.DragDrop> 事件）并插入到 <xref:System.Windows.Forms.RichTextBox> 控件中。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.RichTextBox>
- [如何：在应用程序之间执行拖放操作](../advanced/how-to-perform-drag-and-drop-operations-between-applications.md)
- [RichTextBox 控件](richtextbox-control-windows-forms.md)
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
