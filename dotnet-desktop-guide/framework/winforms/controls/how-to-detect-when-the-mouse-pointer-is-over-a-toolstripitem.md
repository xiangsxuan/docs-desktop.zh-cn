---
title: 如何：检测鼠标指针何时在 ToolStripItem 上
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: f01a9acb3a566be40d65fb075c8487d4e9cb6e73
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971201"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="7a2cb-102">如何：检测鼠标指针何时在 ToolStripItem 上</span><span class="sxs-lookup"><span data-stu-id="7a2cb-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="7a2cb-103">使用以下过程检测鼠标指针何时位于上 <xref:System.Windows.Forms.ToolStripItem> 。</span><span class="sxs-lookup"><span data-stu-id="7a2cb-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="7a2cb-104">检测指针何时在 ToolStripItem 上</span><span class="sxs-lookup"><span data-stu-id="7a2cb-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
- <span data-ttu-id="7a2cb-105">使用的 <xref:System.Windows.Forms.ToolStripItem.Selected%2A> 项的属性为 <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> `true` 。</span><span class="sxs-lookup"><span data-stu-id="7a2cb-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="7a2cb-106">这会使你不必同步 <xref:System.Windows.Forms.ToolStripItem.MouseEnter> 和 <xref:System.Windows.Forms.ToolStripItem.MouseLeave> 事件。</span><span class="sxs-lookup"><span data-stu-id="7a2cb-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a2cb-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a2cb-107">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [<span data-ttu-id="7a2cb-108">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="7a2cb-108">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
