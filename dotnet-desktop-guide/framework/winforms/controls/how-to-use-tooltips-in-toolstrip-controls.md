---
title: 如何：在 ToolStrip 控件中使用工具提示
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 3f383b6cccba7825637ea65a0e13280b91b406c9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972646"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="3788d-102">如何：在 ToolStrip 控件中使用工具提示</span><span class="sxs-lookup"><span data-stu-id="3788d-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="3788d-103">可以 <xref:System.Windows.Forms.ToolTip> <xref:System.Windows.Forms.ToolStrip> 通过将控件的属性设置为，为所需的控件显示 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> `true` 。</span><span class="sxs-lookup"><span data-stu-id="3788d-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="3788d-104">显示工具提示</span><span class="sxs-lookup"><span data-stu-id="3788d-104">To display a ToolTip</span></span>  
  
- <span data-ttu-id="3788d-105">将 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> 控件的属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="3788d-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="3788d-106">的默认值为，而的默认值 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> `true` <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> 为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="3788d-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="3788d-107">使用 ToolStripButton 的工具提示文本的 ToolTipText 属性</span><span class="sxs-lookup"><span data-stu-id="3788d-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1. <span data-ttu-id="3788d-108">将 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> 按钮的属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="3788d-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2. <span data-ttu-id="3788d-109">将 <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> 按钮的属性设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="3788d-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="3788d-110">`AutoToolTip` `true` 默认情况下，属性为 <xref:System.Windows.Forms.ToolStripButton> 、 <xref:System.Windows.Forms.ToolStripDropDownButton> 和 <xref:System.Windows.Forms.ToolStripSplitButton> 。</span><span class="sxs-lookup"><span data-stu-id="3788d-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="3788d-111"><xref:System.Windows.Forms.ToolStripButton> `Text` 默认情况下，为文本使用其属性 <xref:System.Windows.Forms.ToolTip> 。</span><span class="sxs-lookup"><span data-stu-id="3788d-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="3788d-112">使用此过程在中显示自定义文本 <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip> 。</span><span class="sxs-lookup"><span data-stu-id="3788d-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3788d-113">如果将设置 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 为 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> 或 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image> ，则按钮上不会显示任何文本，但会出现工具提示。</span><span class="sxs-lookup"><span data-stu-id="3788d-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3788d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3788d-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="3788d-115">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="3788d-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
