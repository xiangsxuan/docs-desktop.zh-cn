---
title: ToolStripProgressBar 控件概述
ms.date: 03/30/2017
f1_keywords:
- ToolStripProgressBar
helpviewer_keywords:
- toolbars [Windows Forms], progress bars
- progress controls [Windows Forms]
- ToolStripProgressBar control [Windows Forms], about ToolStripProgressBar control
ms.assetid: ec3ab522-5fe4-4b4d-a551-bc19e84f4774
ms.openlocfilehash: 380dabe2468ae3c7d9d7303498823d847a8d119e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973062"
---
# <a name="toolstripprogressbar-control-overview"></a><span data-ttu-id="d0e2f-102">ToolStripProgressBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="d0e2f-102">ToolStripProgressBar Control Overview</span></span>
<span data-ttu-id="d0e2f-103">将 <xref:System.Windows.Forms.ToolStripProgressBar> 所有控件的漂浮和呈现功能 <xref:System.Windows.Forms.ToolStrip> 与它的典型进程跟踪功能组合在一起。</span><span class="sxs-lookup"><span data-stu-id="d0e2f-103">The <xref:System.Windows.Forms.ToolStripProgressBar> combines the rafting and rendering functionality of all <xref:System.Windows.Forms.ToolStrip> controls with its typical process-tracking functionality.</span></span> <span data-ttu-id="d0e2f-104"><xref:System.Windows.Forms.ToolStripProgressBar>通常由承载 <xref:System.Windows.Forms.StatusStrip> ，而不是经常由承载 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="d0e2f-104">A <xref:System.Windows.Forms.ToolStripProgressBar> is most usually hosted by <xref:System.Windows.Forms.StatusStrip>, and less frequently by a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="d0e2f-105">尽管 <xref:System.Windows.Forms.ToolStripProgressBar> 在以前的版本中将替换和添加到控件中的功能，但仍 <xref:System.Windows.Forms.ToolStripProgressBar> 会保留以实现向后兼容性和将来使用（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="d0e2f-105">Although <xref:System.Windows.Forms.ToolStripProgressBar> replaces and adds functionality to the control in previous versions, <xref:System.Windows.Forms.ToolStripProgressBar> is retained for both backward compatibility and future use if desired.</span></span>  
  
### <a name="important-toolstripprogressbar-members"></a><span data-ttu-id="d0e2f-106">重要 ToolStripProgressBar 成员</span><span class="sxs-lookup"><span data-stu-id="d0e2f-106">Important ToolStripProgressBar Members</span></span>  
  
|<span data-ttu-id="d0e2f-107">名称</span><span class="sxs-lookup"><span data-stu-id="d0e2f-107">Name</span></span>|<span data-ttu-id="d0e2f-108">描述</span><span class="sxs-lookup"><span data-stu-id="d0e2f-108">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripProgressBar.MarqueeAnimationSpeed%2A>|<span data-ttu-id="d0e2f-109">获取或设置一个值，该值表示每次 <xref:System.Windows.Forms.ProgressBarStyle.Marquee> 显示更新之间的延迟（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="d0e2f-109">Gets or sets a value representing the delay between each <xref:System.Windows.Forms.ProgressBarStyle.Marquee> display update, in milliseconds.</span></span>|  
|<xref:System.Windows.Forms.ProgressBar.Maximum%2A>|<span data-ttu-id="d0e2f-110">获取或设置为此 <xref:System.Windows.Forms.ToolStripProgressBar> 定义的范围上限。</span><span class="sxs-lookup"><span data-stu-id="d0e2f-110">Gets or sets the upper bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Minimum%2A>|<span data-ttu-id="d0e2f-111">获取或设置为此 <xref:System.Windows.Forms.ToolStripProgressBar> 定义的范围下限。</span><span class="sxs-lookup"><span data-stu-id="d0e2f-111">Gets or sets the lower bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Style%2A>|<span data-ttu-id="d0e2f-112">获取或设置用于 <xref:System.Windows.Forms.ToolStripProgressBar> 显示操作进度的样式。</span><span class="sxs-lookup"><span data-stu-id="d0e2f-112">Gets or sets the style that the <xref:System.Windows.Forms.ToolStripProgressBar> uses to display the progress of an operation.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Value%2A>|<span data-ttu-id="d0e2f-113">获取或设置 <xref:System.Windows.Forms.ToolStripProgressBar> 的当前值。</span><span class="sxs-lookup"><span data-stu-id="d0e2f-113">Gets or sets the current value of the <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.PerformStep%2A>|<span data-ttu-id="d0e2f-114">按照 <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> 属性的数量增加进度栏的当前位置。</span><span class="sxs-lookup"><span data-stu-id="d0e2f-114">Advances the current position of the progress bar by the amount of the <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0e2f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0e2f-115">See also</span></span>

- <xref:System.Windows.Forms.ToolStripProgressBar>
