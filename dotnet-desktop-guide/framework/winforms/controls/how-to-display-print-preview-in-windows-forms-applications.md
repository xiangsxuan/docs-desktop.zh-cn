---
title: 在 Windows 窗体应用程序中显示打印预览
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: 7737cd06001f9acfde5eb44fdff9aaa880f23e79
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971194"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>如何：在 Windows 窗体应用程序中显示打印预览
您可以使用 <xref:System.Windows.Forms.PrintPreviewDialog> 控件使用户能够在打印之前经常显示文档。  
  
 为此，需要指定类的实例 <xref:System.Drawing.Printing.PrintDocument> ; 这是要打印的文档。 有关将打印预览与组件一起使用的详细信息 <xref:System.Drawing.Printing.PrintDocument> ，请参阅 [如何：使用打印预览在 Windows 窗体中打印](../advanced/how-to-print-in-windows-forms-using-print-preview.md)。  
  
> [!NOTE]
> 若要 <xref:System.Windows.Forms.PrintPreviewDialog> 在运行时使用该控件，用户必须在其计算机上安装打印机（本地或通过网络），因为这部分 <xref:System.Windows.Forms.PrintPreviewDialog> 组件会确定文档打印时的外观。  
  
 <xref:System.Windows.Forms.PrintPreviewDialog>控件使用 <xref:System.Drawing.Printing.PrinterSettings> 类。 此外， <xref:System.Windows.Forms.PrintPreviewDialog> 控件使用 <xref:System.Drawing.Printing.PageSettings> 类，正如 <xref:System.Windows.Forms.PrintPreviewDialog> 组件所做的那样。 控件的属性中指定的打印文档 <xref:System.Windows.Forms.PrintPreviewDialog> <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> 引用 <xref:System.Drawing.Printing.PrinterSettings> 和类的实例 <xref:System.Drawing.Printing.PageSettings> ，这些实例用于在预览窗口中呈现文档。  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>使用 PrintPreviewDialog 控件查看页  
  
- 使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法可显示对话框，从而指定要使用的 <xref:System.Drawing.Printing.PrintDocument> 。  
  
     在下面的代码示例中， <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Click> 事件处理程序将打开该控件的一个实例 <xref:System.Windows.Forms.PrintPreviewDialog> 。 打印文档在属性中指定 <xref:System.Windows.Forms.PrintDialog.Document%2A> 。 在下面的示例中，未指定打印文档。  
  
     该示例要求窗体具有一个 <xref:System.Windows.Forms.Button> 控件、一个 <xref:System.Drawing.Printing.PrintDocument> 名为的组件 `myDocument` 和一个 <xref:System.Windows.Forms.PrintPreviewDialog> 控件。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
      (Visual c # 中，Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>另请参阅

- [PrintDocument 组件](printdocument-component-windows-forms.md)
- [PrintPreviewDialog 控件](printpreviewdialog-control-windows-forms.md)
- [Windows 窗体打印支持](../advanced/windows-forms-print-support.md)
- [Windows 窗体](../index.yml)
