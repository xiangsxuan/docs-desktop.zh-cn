---
title: 如何显示 PrintDialog 组件
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: de0acc655bbcf0cfc017d594545fae56cc27f981
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971190"
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="5adf5-102">如何显示 PrintDialog 组件</span><span class="sxs-lookup"><span data-stu-id="5adf5-102">How to display the PrintDialog component</span></span>

<span data-ttu-id="5adf5-103"><xref:System.Windows.Forms.PrintDialog>组件是您的许多用户将熟悉的标准 Windows "打印" 对话框。</span><span class="sxs-lookup"><span data-stu-id="5adf5-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="5adf5-104">由于你的用户会立即熟悉它，因此，你可以使用该 <xref:System.Windows.Forms.PrintDialog> 组件。</span><span class="sxs-lookup"><span data-stu-id="5adf5-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>

## <a name="to-display-the-printdialog-component"></a><span data-ttu-id="5adf5-105">显示 PrintDialog 组件</span><span class="sxs-lookup"><span data-stu-id="5adf5-105">To display the PrintDialog component</span></span>

- <span data-ttu-id="5adf5-106"><xref:System.Windows.Forms.Form.ShowDialog%2A>从应用程序的代码中调用方法。</span><span class="sxs-lookup"><span data-stu-id="5adf5-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>

     <span data-ttu-id="5adf5-107">显示出该组件后，用户可以与之进行交互，设置打印作业的属性。</span><span class="sxs-lookup"><span data-stu-id="5adf5-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="5adf5-108"><xref:System.Drawing.Printing.PrinterSettings> <xref:System.Drawing.Printing.PageSettings> 如果用户通过与该打印作业关联) 组件访问[PageSetupDialog 组件](pagesetupdialog-component-windows-forms.md)，则这些存储在类 (和类中 <xref:System.Windows.Forms.PrintDialog> 。</span><span class="sxs-lookup"><span data-stu-id="5adf5-108">These are saved in the  <xref:System.Drawing.Printing.PrinterSettings> class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="5adf5-109">然后可以调用它们所设置的属性以确定打印作业的细节。</span><span class="sxs-lookup"><span data-stu-id="5adf5-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>

## <a name="see-also"></a><span data-ttu-id="5adf5-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5adf5-110">See also</span></span>

- [<span data-ttu-id="5adf5-111">如何：创建标准的 Windows 窗体打印作业</span><span class="sxs-lookup"><span data-stu-id="5adf5-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [<span data-ttu-id="5adf5-112">如何：在运行时从 PrintDialog 中捕获用户输入</span><span class="sxs-lookup"><span data-stu-id="5adf5-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [<span data-ttu-id="5adf5-113">PrintPreviewDialog 控件</span><span class="sxs-lookup"><span data-stu-id="5adf5-113">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="5adf5-114">PrintDialog 组件</span><span class="sxs-lookup"><span data-stu-id="5adf5-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
- [<span data-ttu-id="5adf5-115">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="5adf5-115">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="5adf5-116">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="5adf5-116">Windows Forms Controls</span></span>](index.md)
