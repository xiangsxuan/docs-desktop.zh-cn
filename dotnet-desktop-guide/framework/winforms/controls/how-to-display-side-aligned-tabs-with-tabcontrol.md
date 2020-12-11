---
title: 如何：使用 TabControl 显示边对齐的选项卡
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tab pages [Windows Forms], displaying side-aligned tabs
- tabs [Windows Forms], displaying side-aligned tabs
- TabControl control [Windows Forms], displaying side-aligned tabs
ms.assetid: 110d5abd-3ae3-4ded-95bf-778aaac798a0
ms.openlocfilehash: d98c5906d99dff9371f8290e7dbc9c9011cd0c29
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971189"
---
# <a name="how-to-display-side-aligned-tabs-with-tabcontrol"></a><span data-ttu-id="258ad-102">如何：使用 TabControl 显示边对齐的选项卡</span><span class="sxs-lookup"><span data-stu-id="258ad-102">How to: Display Side-Aligned Tabs with TabControl</span></span>
<span data-ttu-id="258ad-103"><xref:System.Windows.Forms.TabControl> 的 <xref:System.Windows.Forms.TabControl.Alignment%2A> 属性支持垂直显示选项卡（沿控件的左边缘或右边缘），而不是水平显示（沿控件的顶部或底部）。</span><span class="sxs-lookup"><span data-stu-id="258ad-103">The <xref:System.Windows.Forms.TabControl.Alignment%2A> property of <xref:System.Windows.Forms.TabControl> supports displaying tabs vertically (along the left or right edge of the control), as opposed to horizontally (across the top or bottom of the control).</span></span> <span data-ttu-id="258ad-104">默认情况下，此垂直显示会造成不良的用户体验，因为当视觉样式启用时，<xref:System.Windows.Forms.TabPage> 对象的 <xref:System.Windows.Forms.TabPage.Text%2A> 属性不显示在选项卡中。</span><span class="sxs-lookup"><span data-stu-id="258ad-104">By default, this vertical display results in a poor user experience, because the <xref:System.Windows.Forms.TabPage.Text%2A> property of the <xref:System.Windows.Forms.TabPage> object does not display in the tab when visual styles are enabled.</span></span> <span data-ttu-id="258ad-105">还没有直接的方法控制选项卡中的文本方向。您可以使用所有者绘图 <xref:System.Windows.Forms.TabControl> 来改善此体验。</span><span class="sxs-lookup"><span data-stu-id="258ad-105">There is also no direct way to control the direction of the text within the tab. You can use owner draw on <xref:System.Windows.Forms.TabControl> to improve this experience.</span></span>  
  
 <span data-ttu-id="258ad-106">下面的过程演示如何使用“所有者描述”功能呈现右对齐的选项卡（选项卡文本的运行方向从左到右）。</span><span class="sxs-lookup"><span data-stu-id="258ad-106">The following procedure shows how to render right-aligned tabs, with the tab text running from left to right, by using the "owner draw" feature.</span></span>  
  
### <a name="to-display-right-aligned-tabs"></a><span data-ttu-id="258ad-107">显示右对齐的选项卡</span><span class="sxs-lookup"><span data-stu-id="258ad-107">To display right-aligned tabs</span></span>  
  
1. <span data-ttu-id="258ad-108">在窗体中添加 <xref:System.Windows.Forms.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="258ad-108">Add a <xref:System.Windows.Forms.TabControl> to your form.</span></span>  
  
2. <span data-ttu-id="258ad-109">将 <xref:System.Windows.Forms.TabControl.Alignment%2A> 属性设置为 <xref:System.Windows.Forms.TabAlignment.Right>。</span><span class="sxs-lookup"><span data-stu-id="258ad-109">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property to <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
3. <span data-ttu-id="258ad-110">将 <xref:System.Windows.Forms.TabControl.SizeMode%2A> 属性设置为 <xref:System.Windows.Forms.TabSizeMode.Fixed>，以以使所有选项卡具有相同的宽度。</span><span class="sxs-lookup"><span data-stu-id="258ad-110">Set the <xref:System.Windows.Forms.TabControl.SizeMode%2A> property to <xref:System.Windows.Forms.TabSizeMode.Fixed>, so that all tabs are the same width.</span></span>  
  
4. <span data-ttu-id="258ad-111">将 <xref:System.Windows.Forms.TabControl.ItemSize%2A> 属性设置为选项卡的首选固定大小。</span><span class="sxs-lookup"><span data-stu-id="258ad-111">Set the <xref:System.Windows.Forms.TabControl.ItemSize%2A> property to the preferred fixed size for the tabs.</span></span> <span data-ttu-id="258ad-112">请记住，<xref:System.Windows.Forms.TabControl.ItemSize%2A> 属性的行为如同选项卡位于顶部时的行为一样，尽管它们是右对齐的。</span><span class="sxs-lookup"><span data-stu-id="258ad-112">Keep in mind that the <xref:System.Windows.Forms.TabControl.ItemSize%2A> property behaves as though the tabs were on top, although they are right-aligned.</span></span> <span data-ttu-id="258ad-113">因此，为了增加选项卡宽度，必须更改 <xref:System.Drawing.Size.Height%2A> 属性；为了增加选项卡高度，必须更改 <xref:System.Drawing.Size.Width%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="258ad-113">As a result, in order to make the tabs wider, you must change the <xref:System.Drawing.Size.Height%2A> property, and in order to make them taller, you must change the <xref:System.Drawing.Size.Width%2A> property.</span></span>  
  
     <span data-ttu-id="258ad-114">在下面的代码示例中，将选项卡的 <xref:System.Drawing.Size.Width%2A> 设置为 25，<xref:System.Drawing.Size.Height%2A> 设置为 100 可得到最佳结果。</span><span class="sxs-lookup"><span data-stu-id="258ad-114">For best result with the code example below, set the <xref:System.Drawing.Size.Width%2A> of the tabs to 25 and the <xref:System.Drawing.Size.Height%2A> to 100.</span></span>  
  
5. <span data-ttu-id="258ad-115">将 <xref:System.Windows.Forms.TabControl.DrawMode%2A> 属性设置为 <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>。</span><span class="sxs-lookup"><span data-stu-id="258ad-115">Set the <xref:System.Windows.Forms.TabControl.DrawMode%2A> property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>.</span></span>  
  
6. <span data-ttu-id="258ad-116">为从左到右呈现文本的 <xref:System.Windows.Forms.TabControl> 的 <xref:System.Windows.Forms.TabControl.DrawItem> 事件定义一个处理程序。</span><span class="sxs-lookup"><span data-stu-id="258ad-116">Define a handler for the <xref:System.Windows.Forms.TabControl.DrawItem> event of <xref:System.Windows.Forms.TabControl> that renders the text from left to right.</span></span>  
  
     [!code-csharp[TabControl.RightAlignedTabs#1](~/samples/snippets/csharp/VS_Snippets_Winforms/TabControl.RightAlignedTabs/CS/Form1.cs#1)]
     [!code-vb[TabControl.RightAlignedTabs#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/TabControl.RightAlignedTabs/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="258ad-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="258ad-117">See also</span></span>

- [<span data-ttu-id="258ad-118">TabControl 控件</span><span class="sxs-lookup"><span data-stu-id="258ad-118">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
