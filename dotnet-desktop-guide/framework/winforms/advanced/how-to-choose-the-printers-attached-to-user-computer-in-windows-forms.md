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
# <a name="how-to-choose-the-printers-attached-to-a-users-computer-in-windows-forms"></a><span data-ttu-id="22461-102">如何：在 Windows 窗体中选择附加到用户计算机的打印机</span><span class="sxs-lookup"><span data-stu-id="22461-102">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>
<span data-ttu-id="22461-103">用户通常希望选择默认打印机之外的打印机进行打印。</span><span class="sxs-lookup"><span data-stu-id="22461-103">Often, users want to choose a printer other than the default printer to print to.</span></span> <span data-ttu-id="22461-104">可以使用 <xref:System.Windows.Forms.PrintDialog> 组件使用户能够从当前安装的打印机中选择打印机。</span><span class="sxs-lookup"><span data-stu-id="22461-104">You can enable users to choose a printer from among those currently installed by using the <xref:System.Windows.Forms.PrintDialog> component.</span></span> <span data-ttu-id="22461-105">通过 <xref:System.Windows.Forms.PrintDialog> 组件，会捕获 <xref:System.Windows.Forms.DialogResult> 组件的 <xref:System.Windows.Forms.PrintDialog> 并用于选择打印机。</span><span class="sxs-lookup"><span data-stu-id="22461-105">Through the <xref:System.Windows.Forms.PrintDialog> component, the <xref:System.Windows.Forms.DialogResult> of the <xref:System.Windows.Forms.PrintDialog> component is captured and used to select the printer.</span></span>  
  
 <span data-ttu-id="22461-106">在下面的过程中，选择一个文本文件以打印到默认打印机。</span><span class="sxs-lookup"><span data-stu-id="22461-106">In the following procedure, a text file is selected to be printed to the default printer.</span></span> <span data-ttu-id="22461-107"><xref:System.Windows.Forms.PrintDialog> 类随后进行实例化。</span><span class="sxs-lookup"><span data-stu-id="22461-107">The <xref:System.Windows.Forms.PrintDialog> class is then instantiated.</span></span>  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a><span data-ttu-id="22461-108">选择打印机，然后打印文件</span><span class="sxs-lookup"><span data-stu-id="22461-108">To choose a printer and then print a file</span></span>  
  
1. <span data-ttu-id="22461-109">选择要使用组件的打印机 <xref:System.Windows.Forms.PrintDialog> 。</span><span class="sxs-lookup"><span data-stu-id="22461-109">Select the printer to be used using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
     <span data-ttu-id="22461-110">在下面的代码示例中，要处理两个事件。</span><span class="sxs-lookup"><span data-stu-id="22461-110">In the following code example, there are two events being handled.</span></span> <span data-ttu-id="22461-111">在第一种情况下， <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Click> 事件是 <xref:System.Windows.Forms.PrintDialog> 实例化的类，并且在属性中捕获用户选择的打印机 <xref:System.Windows.Forms.DialogResult> 。</span><span class="sxs-lookup"><span data-stu-id="22461-111">In the first, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event, the <xref:System.Windows.Forms.PrintDialog> class is instantiated and the printer selected by the user is captured in the <xref:System.Windows.Forms.DialogResult> property.</span></span>  
  
     <span data-ttu-id="22461-112">在第二个事件（ <xref:System.Drawing.Printing.PrintDocument.PrintPage> 组件的事件 <xref:System.Drawing.Printing.PrintDocument> ）中，会在指定的打印机上打印一个示例文档。</span><span class="sxs-lookup"><span data-stu-id="22461-112">In the second event, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event of the <xref:System.Drawing.Printing.PrintDocument> component, a sample document is printed to the printer specified.</span></span>  
  
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
  
     <span data-ttu-id="22461-113"> (Visual c # 和 Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="22461-113">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="22461-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22461-114">See also</span></span>

- [<span data-ttu-id="22461-115">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="22461-115">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
