---
title: 如何：设计时将控件与窗体边缘对齐
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: b08e01eb9adb984a32a8fc435cf1f3b93b159a14
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971904"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a><span data-ttu-id="1ae88-102">如何：设计时将控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="1ae88-102">How to: Align a Control to the Edges of Forms at Design Time</span></span>

<span data-ttu-id="1ae88-103">可以通过设置属性的值，使控件与窗体的边缘对齐 <xref:System.Windows.Forms.Control.Dock%2A> 。</span><span class="sxs-lookup"><span data-stu-id="1ae88-103">You can make your control align to the edge of your forms by setting the value of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span> <span data-ttu-id="1ae88-104">此属性指定控件在窗体中的驻留位置。</span><span class="sxs-lookup"><span data-stu-id="1ae88-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="1ae88-105">可以将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为下列值：</span><span class="sxs-lookup"><span data-stu-id="1ae88-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>

|<span data-ttu-id="1ae88-106">设置</span><span class="sxs-lookup"><span data-stu-id="1ae88-106">Setting</span></span>|<span data-ttu-id="1ae88-107">控件上的效果</span><span class="sxs-lookup"><span data-stu-id="1ae88-107">Effect on your control</span></span>|
|-------------|----------------------------|
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="1ae88-108">停靠到窗体底部。</span><span class="sxs-lookup"><span data-stu-id="1ae88-108">Docks to the bottom of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="1ae88-109">占据窗体中的所有剩余空间。</span><span class="sxs-lookup"><span data-stu-id="1ae88-109">Fills all remaining space in the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="1ae88-110">停靠到窗体的左侧。</span><span class="sxs-lookup"><span data-stu-id="1ae88-110">Docks to the left side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="1ae88-111">不会停靠在任何位置，并且它会出现在由其指定的位置 <xref:System.Windows.Forms.Control.Location%2A> 。</span><span class="sxs-lookup"><span data-stu-id="1ae88-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A>.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="1ae88-112">停靠到窗体的右侧。</span><span class="sxs-lookup"><span data-stu-id="1ae88-112">Docks to the right side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="1ae88-113">停靠到窗体的顶部。</span><span class="sxs-lookup"><span data-stu-id="1ae88-113">Docks to the top of the form.</span></span>|

<span data-ttu-id="1ae88-114">也可以在代码中设置这些值。</span><span class="sxs-lookup"><span data-stu-id="1ae88-114">These values can also be set in code.</span></span> <span data-ttu-id="1ae88-115">有关详细信息，请参阅 [如何：将控件与窗体边缘对齐](how-to-align-a-control-to-the-edges-of-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="1ae88-115">For more information, see [How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md).</span></span>

## <a name="set-the-dock-property-for-your-control-at-design-time"></a><span data-ttu-id="1ae88-116">在设计时设置控件的 Dock 属性</span><span class="sxs-lookup"><span data-stu-id="1ae88-116">Set the Dock property for your control at design time</span></span>

1. <span data-ttu-id="1ae88-117">在 Visual Studio 的 "Windows 窗体设计器中，选择控件。</span><span class="sxs-lookup"><span data-stu-id="1ae88-117">In the Windows Forms Designer in Visual Studio, select your control.</span></span>

2. <span data-ttu-id="1ae88-118">在 " **属性** " 窗口中，单击属性旁边的下拉框 <xref:System.Windows.Forms.Control.Dock%2A> 。</span><span class="sxs-lookup"><span data-stu-id="1ae88-118">In the **Properties** window, click the drop-down box next to the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>

     <span data-ttu-id="1ae88-119">显示了六种可能的设置的图形界面 <xref:System.Windows.Forms.Control.Dock%2A> 。</span><span class="sxs-lookup"><span data-stu-id="1ae88-119">A graphical interface representing the six possible <xref:System.Windows.Forms.Control.Dock%2A> settings is displayed.</span></span>

3. <span data-ttu-id="1ae88-120">选择适当的设置。</span><span class="sxs-lookup"><span data-stu-id="1ae88-120">Choose the appropriate setting.</span></span>

4. <span data-ttu-id="1ae88-121">控件现在将按设置指定的方式停靠。</span><span class="sxs-lookup"><span data-stu-id="1ae88-121">Your control will now dock in the manner specified by the setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ae88-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ae88-122">See also</span></span>

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1ae88-123">如何：使控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="1ae88-123">How to: Align a Control to the Edges of Forms</span></span>](how-to-align-a-control-to-the-edges-of-forms.md)
- [<span data-ttu-id="1ae88-124">演练：使用对齐线在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="1ae88-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="1ae88-125">如何：在 Windows 窗体上锚定控件</span><span class="sxs-lookup"><span data-stu-id="1ae88-125">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
- [<span data-ttu-id="1ae88-126">如何：在 TableLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="1ae88-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="1ae88-127">如何：在 FlowLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="1ae88-127">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="1ae88-128">演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="1ae88-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="1ae88-129">演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="1ae88-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="1ae88-130">设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="1ae88-130">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
