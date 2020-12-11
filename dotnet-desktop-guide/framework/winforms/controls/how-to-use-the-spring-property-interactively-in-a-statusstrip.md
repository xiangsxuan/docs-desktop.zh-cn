---
title: 如何：在 StatusStrip 中以交互方式使用 Spring 属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
ms.openlocfilehash: 8750c48d08161260a1dba6ab69098980f25a5d55
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971117"
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a><span data-ttu-id="adde3-102">如何：在 StatusStrip 中以交互方式使用 Spring 属性</span><span class="sxs-lookup"><span data-stu-id="adde3-102">How to: Use the Spring Property Interactively in a StatusStrip</span></span>
<span data-ttu-id="adde3-103">可以使用 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 属性来定位 <xref:System.Windows.Forms.StatusStrip> 控件中的 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件。</span><span class="sxs-lookup"><span data-stu-id="adde3-103">You can use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="adde3-104"><xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 属性确定 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件是否自动填充 <xref:System.Windows.Forms.StatusStrip> 控件中的可用空间。</span><span class="sxs-lookup"><span data-stu-id="adde3-104">The <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property determines whether the <xref:System.Windows.Forms.ToolStripStatusLabel> control automatically fills the available space on the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adde3-105">示例</span><span class="sxs-lookup"><span data-stu-id="adde3-105">Example</span></span>  
 <span data-ttu-id="adde3-106">下面的代码示例演示了如何使用 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 属性定位 <xref:System.Windows.Forms.StatusStrip> 控件中的 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件。</span><span class="sxs-lookup"><span data-stu-id="adde3-106">The following code example demonstrates how to use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="adde3-107"><xref:System.Windows.Forms.ToolStripItem.Click> 事件处理程序执行异或 (XOR) 运算，以便切换 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="adde3-107">The <xref:System.Windows.Forms.ToolStripItem.Click> event handler performs an exclusive-or (XOR) operation to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 <span data-ttu-id="adde3-108">若要使用此代码示例，请编译并运行应用程序，然后单击控件上的 " **中间 (弹簧)** <xref:System.Windows.Forms.StatusStrip> 以切换属性的值 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 。</span><span class="sxs-lookup"><span data-stu-id="adde3-108">To use this code example, compile and run the application, and then click **Middle (Spring)** on the <xref:System.Windows.Forms.StatusStrip> control to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="adde3-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="adde3-109">Compiling the Code</span></span>  
 <span data-ttu-id="adde3-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="adde3-110">This example requires:</span></span>  
  
- <span data-ttu-id="adde3-111">对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="adde3-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adde3-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="adde3-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="adde3-113">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="adde3-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
