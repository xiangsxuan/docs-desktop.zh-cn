---
title: 如何：选择连接到用户计算机的打印机
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
ms.openlocfilehash: 2afbccd02ef42a78d5eac1a01841516fca27c92e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970335"
---
# <a name="how-to-choose-the-printers-attached-to-a-users-computer-in-windows-forms"></a>如何：在 Windows 窗体中选择附加到用户计算机的打印机
用户通常希望选择默认打印机之外的打印机进行打印。 可以使用 <xref:System.Windows.Forms.PrintDialog> 组件使用户能够从当前安装的打印机中选择打印机。 通过 <xref:System.Windows.Forms.PrintDialog> 组件，会捕获 <xref:System.Windows.Forms.DialogResult> 组件的 <xref:System.Windows.Forms.PrintDialog> 并用于选择打印机。  
  
 在下面的过程中，选择一个文本文件以打印到默认打印机。 <xref:System.Windows.Forms.PrintDialog> 类随后进行实例化。  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a>选择打印机，然后打印文件  
  
1. 选择要使用组件的打印机 <xref:System.Windows.Forms.PrintDialog> 。  
  
     在下面的代码示例中，要处理两个事件。 在第一种情况下， <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Click> 事件是 <xref:System.Windows.Forms.PrintDialog> 实例化的类，并且在属性中捕获用户选择的打印机 <xref:System.Windows.Forms.DialogResult> 。  
  
     在第二个事件（ <xref:System.Drawing.Printing.PrintDocument.PrintPage> 组件的事件 <xref:System.Drawing.Printing.PrintDocument> ）中，会在指定的打印机上打印一个示例文档。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim PrintDialog1 As New PrintDialog()  
       PrintDialog1.Document = PrintDocument1  
       Dim result As DialogResult = PrintDialog1.ShowDialog()  
  
       If (result = DialogResult.OK) Then  
         PrintDocument1.Print()  
       End If
  
    End Sub  
  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       PrintDialog printDialog1 = new PrintDialog();  
       printDialog1.Document = printDocument1;  
       DialogResult result = printDialog1.ShowDialog();  
       if (result == DialogResult.OK)  
       {  
          printDocument1.Print();  
       }  
    }  
  
    private void printDocument1_PrintPage(object sender,
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          PrintDialog ^ printDialog1 = gcnew PrintDialog();  
          printDialog1->Document = printDocument1;  
          System::Windows::Forms::DialogResult result =
             printDialog1->ShowDialog();  
          if (result == DialogResult::OK)  
          {  
             printDocument1->Print();  
          }  
       }  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
      (Visual c # 和 Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体打印支持](windows-forms-print-support.md)
