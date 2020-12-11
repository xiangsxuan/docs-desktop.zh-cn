---
title: 如何：动态添加 ToolStrip 项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- toolbars [Windows Forms], adding items dynamically
- ToolStrip control [Windows Forms]
ms.assetid: 0e8dea56-5f46-408b-914d-7e360341a234
ms.openlocfilehash: 08d08a292995cc5e12fbab3e91a0962c3b895a02
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971906"
---
# <a name="how-to-add-toolstrip-items-dynamically"></a><span data-ttu-id="f4f0a-102">如何：动态添加 ToolStrip 项</span><span class="sxs-lookup"><span data-stu-id="f4f0a-102">How to: Add ToolStrip Items Dynamically</span></span>
<span data-ttu-id="f4f0a-103">打开菜单时，可以动态填充 <xref:System.Windows.Forms.ToolStrip> 控件的菜单项集合。</span><span class="sxs-lookup"><span data-stu-id="f4f0a-103">You can dynamically populate the menu item collection of a <xref:System.Windows.Forms.ToolStrip> control when the menu opens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4f0a-104">示例</span><span class="sxs-lookup"><span data-stu-id="f4f0a-104">Example</span></span>  
 <span data-ttu-id="f4f0a-105">下面的代码示例演示如何将项动态地添加到 <xref:System.Windows.Forms.ContextMenuStrip> 控件中。</span><span class="sxs-lookup"><span data-stu-id="f4f0a-105">The following code example demonstrates how to dynamically add items to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="f4f0a-106">该示例还显示如何对窗体上三个不同的控件重用相同的 <xref:System.Windows.Forms.ContextMenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="f4f0a-106">The example also shows how to reuse the same <xref:System.Windows.Forms.ContextMenuStrip> for three different controls on the form.</span></span>  
  
 <span data-ttu-id="f4f0a-107">在示例中，<xref:System.Windows.Forms.ToolStripDropDown.Opening> 事件处理程序会填充菜单项集合。</span><span class="sxs-lookup"><span data-stu-id="f4f0a-107">In the example, an <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler populates the menu item collection.</span></span> <span data-ttu-id="f4f0a-108"><xref:System.Windows.Forms.ToolStripDropDown.Opening> 事件处理程序将检查 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> 属性并添加 <xref:System.Windows.Forms.ToolStripItem> 描述源控件。</span><span class="sxs-lookup"><span data-stu-id="f4f0a-108">The <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler examines the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> properties and adds a <xref:System.Windows.Forms.ToolStripItem> describing the source control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#40)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f4f0a-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="f4f0a-109">Compiling the Code</span></span>  
 <span data-ttu-id="f4f0a-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f4f0a-110">This example requires:</span></span>  
  
- <span data-ttu-id="f4f0a-111">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="f4f0a-111">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f0a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4f0a-112">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- [<span data-ttu-id="f4f0a-113">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="f4f0a-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
