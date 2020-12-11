---
title: 创建标准打印作业
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970801"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="735dc-102">如何：创建标准的 Windows 窗体打印作业</span><span class="sxs-lookup"><span data-stu-id="735dc-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="735dc-103">Windows 窗体中打印的基础是组件， <xref:System.Drawing.Printing.PrintDocument> 更具体地说，是 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件。</span><span class="sxs-lookup"><span data-stu-id="735dc-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="735dc-104">通过编写代码来处理 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件，您可以指定要打印的内容以及打印方式。</span><span class="sxs-lookup"><span data-stu-id="735dc-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="735dc-105">创建打印作业</span><span class="sxs-lookup"><span data-stu-id="735dc-105">To create a print job</span></span>  
  
1. <span data-ttu-id="735dc-106">将 <xref:System.Drawing.Printing.PrintDocument> 组件添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="735dc-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="735dc-107">编写代码以处理 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件。</span><span class="sxs-lookup"><span data-stu-id="735dc-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="735dc-108">您必须编写自己的打印逻辑代码。</span><span class="sxs-lookup"><span data-stu-id="735dc-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="735dc-109">此外，您还必须指定要打印的材料。</span><span class="sxs-lookup"><span data-stu-id="735dc-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="735dc-110">在下面的代码示例中，会在事件处理程序中创建一个红色矩形的示例图形， <xref:System.Drawing.Printing.PrintDocument.PrintPage> 作为要打印的材料。</span><span class="sxs-lookup"><span data-stu-id="735dc-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="735dc-111"> (Visual c # 和 Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="735dc-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     <span data-ttu-id="735dc-112">你可能还需要为和事件编写代码 <xref:System.Drawing.Printing.PrintDocument.BeginPrint> <xref:System.Drawing.Printing.PrintDocument.EndPrint> ，可能包括一个整数，该整数表示在每个页面打印时减少的打印页数。</span><span class="sxs-lookup"><span data-stu-id="735dc-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="735dc-113">可以将组件添加 <xref:System.Windows.Forms.PrintDialog> 到窗体中，以便向用户 (UI) 提供清晰且高效的用户界面。</span><span class="sxs-lookup"><span data-stu-id="735dc-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="735dc-114">设置 <xref:System.Windows.Forms.PrintDialog.Document%2A> 组件的属性 <xref:System.Windows.Forms.PrintDialog> 使您能够设置与您在窗体上使用的打印文档相关的属性。</span><span class="sxs-lookup"><span data-stu-id="735dc-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="735dc-115">有关组件的详细信息 <xref:System.Windows.Forms.PrintDialog> ，请参阅 [PrintDialog component](../controls/printdialog-component-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="735dc-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="735dc-116">有关 Windows 窗体打印作业的详细信息，包括如何以编程方式创建打印作业的详细信息，请参阅 <xref:System.Drawing.Printing.PrintPageEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="735dc-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="735dc-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="735dc-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="735dc-118">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="735dc-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
