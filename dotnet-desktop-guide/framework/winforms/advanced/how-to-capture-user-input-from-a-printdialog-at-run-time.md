---
title: 如何：在运行时从 PrintDialog 中捕获用户输入
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
ms.openlocfilehash: 2aaf988f362baf9cd80eb16e4a08f7f65a5077bb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970906"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a><span data-ttu-id="f88f6-102">如何：在运行时从 PrintDialog 中捕获用户输入</span><span class="sxs-lookup"><span data-stu-id="f88f6-102">How to: Capture User Input from a PrintDialog at Run Time</span></span>
<span data-ttu-id="f88f6-103">虽然您可以在设计时设置与打印相关的选项，但有时您可能希望在运行时更改这些选项，这很可能是由用户做出的选择。</span><span class="sxs-lookup"><span data-stu-id="f88f6-103">While you can set options related to printing at design time, you will sometimes want to change these options at run time, most likely because of choices made by the user.</span></span> <span data-ttu-id="f88f6-104">您可以使用和组件捕获用于打印文档的用户输入 <xref:System.Windows.Forms.PrintDialog> <xref:System.Drawing.Printing.PrintDocument> 。</span><span class="sxs-lookup"><span data-stu-id="f88f6-104">You can capture user input for printing a document using the <xref:System.Windows.Forms.PrintDialog> and the <xref:System.Drawing.Printing.PrintDocument> components.</span></span>  
  
### <a name="to-change-print-options-programmatically"></a><span data-ttu-id="f88f6-105">以编程方式更改打印选项</span><span class="sxs-lookup"><span data-stu-id="f88f6-105">To change print options programmatically</span></span>  
  
1. <span data-ttu-id="f88f6-106">向 <xref:System.Windows.Forms.PrintDialog> <xref:System.Drawing.Printing.PrintDocument> 窗体添加和组件。</span><span class="sxs-lookup"><span data-stu-id="f88f6-106">Add a <xref:System.Windows.Forms.PrintDialog> and a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="f88f6-107">将 <xref:System.Windows.Forms.PrintDialog.Document%2A> 的属性设置 <xref:System.Windows.Forms.PrintDialog> 为 <xref:System.Drawing.Printing.PrintDocument> 添加到窗体中的。</span><span class="sxs-lookup"><span data-stu-id="f88f6-107">Set the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> to the <xref:System.Drawing.Printing.PrintDocument> added to the form.</span></span>  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3. <span data-ttu-id="f88f6-108"><xref:System.Windows.Forms.PrintDialog>使用方法显示组件 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f88f6-108">Display the <xref:System.Windows.Forms.PrintDialog> component by using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4. <span data-ttu-id="f88f6-109">用户在对话框中的打印选项将复制到 <xref:System.Drawing.Printing.PrinterSettings> 组件的属性 <xref:System.Drawing.Printing.PrintDocument> 。</span><span class="sxs-lookup"><span data-stu-id="f88f6-109">The user's printing choices from the dialog will be copied to the <xref:System.Drawing.Printing.PrinterSettings> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f88f6-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f88f6-110">See also</span></span>

- [<span data-ttu-id="f88f6-111">如何：打印 Windows 窗体中的多页文本文件</span><span class="sxs-lookup"><span data-stu-id="f88f6-111">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [<span data-ttu-id="f88f6-112">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="f88f6-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
