---
title: 如何：处理 ContextMenuStrip 打开事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
ms.openlocfilehash: 3001480959ef90cb31048cbcf70aeff1632979fb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971833"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a><span data-ttu-id="70fd2-102">如何：处理 ContextMenuStrip 打开事件</span><span class="sxs-lookup"><span data-stu-id="70fd2-102">How to: Handle the ContextMenuStrip Opening Event</span></span>
<span data-ttu-id="70fd2-103">可以 <xref:System.Windows.Forms.ContextMenuStrip> 通过处理事件自定义控件的行为 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 。</span><span class="sxs-lookup"><span data-stu-id="70fd2-103">You can customize the behavior of your <xref:System.Windows.Forms.ContextMenuStrip> control by handling the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70fd2-104">示例</span><span class="sxs-lookup"><span data-stu-id="70fd2-104">Example</span></span>  
 <span data-ttu-id="70fd2-105">下面的代码示例演示如何处理 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 事件。</span><span class="sxs-lookup"><span data-stu-id="70fd2-105">The following code example demonstrates how to handle the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span> <span data-ttu-id="70fd2-106">事件处理程序将项动态添加到 <xref:System.Windows.Forms.ContextMenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="70fd2-106">The event handler adds items dynamically to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="70fd2-107">有关完整的代码示例，请参阅 [如何：动态添加 ToolStrip 项](how-to-add-toolstrip-items-dynamically.md)。</span><span class="sxs-lookup"><span data-stu-id="70fd2-107">For the complete code example, see [How to: Add ToolStrip Items Dynamically](how-to-add-toolstrip-items-dynamically.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <span data-ttu-id="70fd2-108">将 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> 属性设置为， `true` 以防止菜单打开。</span><span class="sxs-lookup"><span data-stu-id="70fd2-108">Set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> property to `true` to prevent the menu from opening.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70fd2-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70fd2-109">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="70fd2-110">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="70fd2-110">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
