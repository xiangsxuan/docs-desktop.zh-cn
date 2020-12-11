---
title: PrintPreviewControl 控件概述
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: 8dfe5802a24d5ec85ed908fd04c5550e1fbec012
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972789"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a><span data-ttu-id="2eb82-102">PrintPreviewControl 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="2eb82-102">PrintPreviewControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="2eb82-103">Windows 窗体 <xref:System.Windows.Forms.PrintPreviewControl> 用于显示 [PrintDocument](printdocument-component-windows-forms.md) ，因为它会在打印后显示。</span><span class="sxs-lookup"><span data-stu-id="2eb82-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> is used to display a [PrintDocument](printdocument-component-windows-forms.md) as it will appear when printed.</span></span> <span data-ttu-id="2eb82-104">此控件具有没有按钮或其他用户界面元素，因此通常仅在你想要编写自己的打印预览用户界面时才使用 <xref:System.Windows.Forms.PrintPreviewControl>。</span><span class="sxs-lookup"><span data-stu-id="2eb82-104">This control has no buttons or other user interface elements, so typically you use the <xref:System.Windows.Forms.PrintPreviewControl> only if you wish to write your own print-preview user interface.</span></span> <span data-ttu-id="2eb82-105">如果需要标准用户界面，请使用 <xref:System.Windows.Forms.PrintPreviewDialog> 控件; 有关概述，请参阅 [PrintPreviewDialog 控件概述](printpreviewdialog-control-overview-windows-forms.md) 。</span><span class="sxs-lookup"><span data-stu-id="2eb82-105">If you want the standard user interface, use a <xref:System.Windows.Forms.PrintPreviewDialog> control; see [PrintPreviewDialog Control Overview](printpreviewdialog-control-overview-windows-forms.md) for an overview.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="2eb82-106">键属性</span><span class="sxs-lookup"><span data-stu-id="2eb82-106">Key Properties</span></span>  
 <span data-ttu-id="2eb82-107">控件的键属性为 <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> ，用于设置要预览的文档。</span><span class="sxs-lookup"><span data-stu-id="2eb82-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="2eb82-108">文档必须为 <xref:System.Drawing.Printing.PrintDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="2eb82-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="2eb82-109">有关创建打印文档的概述，请参阅 [PrintDocument 组件概述](printdocument-component-overview-windows-forms.md) 和 [Windows 窗体打印支持](../advanced/windows-forms-print-support.md)。</span><span class="sxs-lookup"><span data-stu-id="2eb82-109">For an overview of creating documents for printing, see [PrintDocument Component Overview](printdocument-component-overview-windows-forms.md) and [Windows Forms Print Support](../advanced/windows-forms-print-support.md).</span></span> <span data-ttu-id="2eb82-110"><xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>和 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 属性确定控件上横向和纵向显示的页数。</span><span class="sxs-lookup"><span data-stu-id="2eb82-110">The <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="2eb82-111">抗锯齿可以使文本显示得更平滑，但也可以使显示速度变慢;若要使用它，请将 <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="2eb82-111">Antialiasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eb82-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2eb82-112">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewControl>
- [<span data-ttu-id="2eb82-113">PrintPreviewDialog 控件概述</span><span class="sxs-lookup"><span data-stu-id="2eb82-113">PrintPreviewDialog Control Overview</span></span>](printpreviewdialog-control-overview-windows-forms.md)
- [<span data-ttu-id="2eb82-114">PrintPreviewControl 控件</span><span class="sxs-lookup"><span data-stu-id="2eb82-114">PrintPreviewControl Control</span></span>](printpreviewcontrol-control-windows-forms.md)
- [<span data-ttu-id="2eb82-115">对话框控件和组件</span><span class="sxs-lookup"><span data-stu-id="2eb82-115">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
