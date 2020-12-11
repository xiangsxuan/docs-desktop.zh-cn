---
title: TrackBar 控件概述
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 6901405100df4633c84850757f55b756bc9a0199
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973047"
---
# <a name="trackbar-control-overview-windows-forms"></a><span data-ttu-id="32872-102">TrackBar 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="32872-102">TrackBar Control Overview (Windows Forms)</span></span>
<span data-ttu-id="32872-103">Windows 窗体 <xref:System.Windows.Forms.TrackBar> (控件有时也称为 "滑块" 控件) 用于在大量信息中导航，或用于直观地调整数字设置。</span><span class="sxs-lookup"><span data-stu-id="32872-103">The Windows Forms <xref:System.Windows.Forms.TrackBar> control (also sometimes called a "slider" control) is used for navigating through a large amount of information or for visually adjusting a numeric setting.</span></span> <span data-ttu-id="32872-104"><xref:System.Windows.Forms.TrackBar>控件包含两部分：滚动块（也称为滑块）和刻度线。</span><span class="sxs-lookup"><span data-stu-id="32872-104">The <xref:System.Windows.Forms.TrackBar> control has two parts: the thumb, also known as a slider, and the tick marks.</span></span> <span data-ttu-id="32872-105">滚动块是可以调整的部分。</span><span class="sxs-lookup"><span data-stu-id="32872-105">The thumb is the part that can be adjusted.</span></span> <span data-ttu-id="32872-106">其位置与属性相对应 <xref:System.Windows.Forms.TrackBar.Value%2A> 。</span><span class="sxs-lookup"><span data-stu-id="32872-106">Its position corresponds to the <xref:System.Windows.Forms.TrackBar.Value%2A> property.</span></span> <span data-ttu-id="32872-107">刻度线是按固定间隔分隔的可视指示器。</span><span class="sxs-lookup"><span data-stu-id="32872-107">The tick marks are visual indicators that are spaced at regular intervals.</span></span> <span data-ttu-id="32872-108">跟踪条以指定的增量移动，并可水平或垂直对齐。</span><span class="sxs-lookup"><span data-stu-id="32872-108">The trackbar moves in increments that you specify and can be aligned horizontally or vertically.</span></span> <span data-ttu-id="32872-109">例如，您可以使用跟踪栏来控制系统的光标闪烁速率或鼠标速度。</span><span class="sxs-lookup"><span data-stu-id="32872-109">For example, you might use the track bar to control the cursor blink rate or mouse speed for a system.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="32872-110">键属性</span><span class="sxs-lookup"><span data-stu-id="32872-110">Key Properties</span></span>  
 <span data-ttu-id="32872-111">控件的键属性 <xref:System.Windows.Forms.TrackBar> 为、、 <xref:System.Windows.Forms.TrackBar.Value%2A> <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> <xref:System.Windows.Forms.TrackBar.Minimum%2A> 和 <xref:System.Windows.Forms.TrackBar.Maximum%2A> 。</span><span class="sxs-lookup"><span data-stu-id="32872-111">The key properties of the <xref:System.Windows.Forms.TrackBar> control are <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, and <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span></span> <span data-ttu-id="32872-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A> 刻度的间距。</span><span class="sxs-lookup"><span data-stu-id="32872-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A> is the spacing of the ticks.</span></span> <span data-ttu-id="32872-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A> 和 <xref:System.Windows.Forms.TrackBar.Maximum%2A> 是可在跟踪条上表示的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="32872-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A> and <xref:System.Windows.Forms.TrackBar.Maximum%2A> are the smallest and largest values that can be represented on the track bar.</span></span>  
  
 <span data-ttu-id="32872-114">另外两个重要的属性是 <xref:System.Windows.Forms.TrackBar.SmallChange%2A> 和 <xref:System.Windows.Forms.TrackBar.LargeChange%2A> 。</span><span class="sxs-lookup"><span data-stu-id="32872-114">Two other important properties are <xref:System.Windows.Forms.TrackBar.SmallChange%2A> and <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span></span> <span data-ttu-id="32872-115">属性的值 <xref:System.Windows.Forms.TrackBar.SmallChange%2A> 是指在按下左箭头键或右箭头键时移动的位置数。</span><span class="sxs-lookup"><span data-stu-id="32872-115">The value of the <xref:System.Windows.Forms.TrackBar.SmallChange%2A> property is the number of positions the thumb moves in response to having the LEFT or RIGHT ARROW key pressed.</span></span> <span data-ttu-id="32872-116">属性的值 <xref:System.Windows.Forms.TrackBar.LargeChange%2A> 是指在按下 PAGE UP 或 PAGE DOWN 键时移动的位置数，或响应滚动块两侧的跟踪条的鼠标单击。</span><span class="sxs-lookup"><span data-stu-id="32872-116">The value of the <xref:System.Windows.Forms.TrackBar.LargeChange%2A> property is the number of positions the thumb moves in response to having the PAGE UP or PAGE DOWN key pressed, or in response to mouse clicks on the track bar on either side of the thumb.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32872-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32872-117">See also</span></span>

- <xref:System.Windows.Forms.TrackBar>
- [<span data-ttu-id="32872-118">TrackBar 控件</span><span class="sxs-lookup"><span data-stu-id="32872-118">TrackBar Control</span></span>](trackbar-control-windows-forms.md)
