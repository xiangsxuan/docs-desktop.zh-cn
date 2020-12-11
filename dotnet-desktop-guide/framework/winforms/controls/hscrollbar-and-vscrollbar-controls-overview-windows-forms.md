---
title: HScrollBar 和 VScrollBar 控件概述
ms.date: 03/30/2017
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
ms.openlocfilehash: abe0c8da9723f17cb80715454f6ab7297724a21f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972642"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a><span data-ttu-id="41609-102">HScrollBar 控件和 VScrollBar 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="41609-102">HScrollBar and VScrollBar Controls Overview (Windows Forms)</span></span>
<span data-ttu-id="41609-103">Windows 窗体 <xref:System.Windows.Forms.ScrollBar> 控件用于通过在应用程序或控件中水平或垂直滚动来轻松地浏览较长的项列表或大量的信息。</span><span class="sxs-lookup"><span data-stu-id="41609-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> controls are used to provide easy navigation through a long list of items or a large amount of information by scrolling either horizontally or vertically within an application or control.</span></span> <span data-ttu-id="41609-104">滚动条是 Windows 界面的公共元素，因此该 <xref:System.Windows.Forms.ScrollBar> 控件通常用于不是从类派生的控件 <xref:System.Windows.Forms.ScrollableControl> 。</span><span class="sxs-lookup"><span data-stu-id="41609-104">Scroll bars are a common element of the Windows interface, so the <xref:System.Windows.Forms.ScrollBar> control is often used with controls that do not derive from the <xref:System.Windows.Forms.ScrollableControl> class.</span></span> <span data-ttu-id="41609-105">同样，许多开发人员 <xref:System.Windows.Forms.ScrollBar> 在创作自己的用户控件时选择合并控件。</span><span class="sxs-lookup"><span data-stu-id="41609-105">Similarly, many developers choose to incorporate the <xref:System.Windows.Forms.ScrollBar> control when authoring their own user controls.</span></span>  
  
 <span data-ttu-id="41609-106"><xref:System.Windows.Forms.HScrollBar> (水平) 和 <xref:System.Windows.Forms.VScrollBar> (垂直) 控件独立于其他控件操作，并且具有其自己的一组事件、属性和方法。</span><span class="sxs-lookup"><span data-stu-id="41609-106">The <xref:System.Windows.Forms.HScrollBar> (horizontal) and <xref:System.Windows.Forms.VScrollBar> (vertical) controls operate independently from other controls and have their own set of events, properties, and methods.</span></span> <span data-ttu-id="41609-107"><xref:System.Windows.Forms.ScrollBar> 控件与附加到文本框、列表框、组合框或 MDI 窗体的内置滚动条不同 (<xref:System.Windows.Forms.TextBox> 控件具有 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 用于显示或隐藏附加到控件) 的滚动条的属性。</span><span class="sxs-lookup"><span data-stu-id="41609-107"><xref:System.Windows.Forms.ScrollBar> controls are not the same as the built-in scroll bars that are attached to text boxes, list boxes, combo boxes, or MDI forms (the <xref:System.Windows.Forms.TextBox> control has a <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to show or hide scroll bars that are attached to the control).</span></span>  
  
 <span data-ttu-id="41609-108">这些 <xref:System.Windows.Forms.ScrollBar> 控件使用 <xref:System.Windows.Forms.ScrollBar.Scroll> 事件监视滚动框 (有时称为滚动条) 的滚动框的移动。</span><span class="sxs-lookup"><span data-stu-id="41609-108">The <xref:System.Windows.Forms.ScrollBar> controls use the <xref:System.Windows.Forms.ScrollBar.Scroll> event to monitor the movement of the scroll box (sometimes referred to as the thumb) along the scroll bar.</span></span> <span data-ttu-id="41609-109">使用 <xref:System.Windows.Forms.ScrollBar.Scroll> 事件可在拖动滚动条值时，提供对滚动条值的访问。</span><span class="sxs-lookup"><span data-stu-id="41609-109">Using the <xref:System.Windows.Forms.ScrollBar.Scroll> event provides access to the scroll bar value as it is being dragged.</span></span>  
  
## <a name="value-property"></a><span data-ttu-id="41609-110">Value 属性</span><span class="sxs-lookup"><span data-stu-id="41609-110">Value Property</span></span>  
 <span data-ttu-id="41609-111"><xref:System.Windows.Forms.ScrollBar.Value%2A>默认情况下，属性 (为 0) 是 `integer` 与滚动条中滚动框的位置相对应的值。</span><span class="sxs-lookup"><span data-stu-id="41609-111">The <xref:System.Windows.Forms.ScrollBar.Value%2A> property (which, by default, is 0) is an `integer` value corresponding to the position of the scroll box in the scroll bar.</span></span> <span data-ttu-id="41609-112">当滚动框位置为最小值时，它会移动到水平滚动条的最左边位置 () 或垂直滚动条) 的顶部位置 (。</span><span class="sxs-lookup"><span data-stu-id="41609-112">When the scroll box position is at the minimum value, it moves to the left-most position (for horizontal scroll bars) or the top position (for vertical scroll bars).</span></span> <span data-ttu-id="41609-113">当滚动框处于最大值时，滚动框会移动到最右侧或底部位置。</span><span class="sxs-lookup"><span data-stu-id="41609-113">When the scroll box is at the maximum value, the scroll box moves to the right-most or bottom position.</span></span> <span data-ttu-id="41609-114">同样，范围底部和顶部中间的值将在滚动条的中间放置滚动框的上边缘。</span><span class="sxs-lookup"><span data-stu-id="41609-114">Similarly, a value halfway between the bottom and top of the range places the leading edge of the scroll box in the middle of the scroll bar.</span></span>  
  
 <span data-ttu-id="41609-115">除了使用鼠标单击更改滚动条值以外，用户还可以将滚动框拖动到滚动条上的任意点。</span><span class="sxs-lookup"><span data-stu-id="41609-115">In addition to using mouse clicks to change the scroll bar value, a user can also drag the scroll box to any point along the bar.</span></span> <span data-ttu-id="41609-116">生成的值取决于滚动框的位置，但它始终在 <xref:System.Windows.Forms.ScrollBar.Minimum%2A> 用户设置的到属性的范围内 <xref:System.Windows.Forms.ScrollBar.Maximum%2A> 。</span><span class="sxs-lookup"><span data-stu-id="41609-116">The resulting value depends on the position of the scroll box, but it is always within the range of the <xref:System.Windows.Forms.ScrollBar.Minimum%2A> to <xref:System.Windows.Forms.ScrollBar.Maximum%2A> properties set by the user.</span></span>  
  
## <a name="largechange-and-smallchange-properties"></a><span data-ttu-id="41609-117">LargeChange 和 SmallChange 属性</span><span class="sxs-lookup"><span data-stu-id="41609-117">LargeChange and SmallChange Properties</span></span>  
 <span data-ttu-id="41609-118">当用户按下 PAGE UP 或 PAGE DOWN 键或单击滚动框两侧的滚动条轨道时， <xref:System.Windows.Forms.ScrollBar.Value%2A> 属性将根据属性中设置的值进行更改 <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> 。</span><span class="sxs-lookup"><span data-stu-id="41609-118">When the user presses the PAGE UP or PAGE DOWN key or clicks in the scroll bar track on either side of the scroll box, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> property.</span></span>  
  
 <span data-ttu-id="41609-119">当用户按下某个箭头键或单击某个滚动条按钮时， <xref:System.Windows.Forms.ScrollBar.Value%2A> 属性将根据属性中设置的值进行更改 <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> 。</span><span class="sxs-lookup"><span data-stu-id="41609-119">When the user presses one of the arrow keys or clicks one of the scroll bar buttons, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41609-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41609-120">See also</span></span>

- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [<span data-ttu-id="41609-121">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="41609-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
