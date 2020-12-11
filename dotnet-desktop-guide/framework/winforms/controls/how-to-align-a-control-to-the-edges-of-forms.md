---
title: 如何：使控件与窗体边缘对齐
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
ms.openlocfilehash: 5d662489b7e31f391bbd508409e69c091a25592c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971769"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a><span data-ttu-id="1c3fe-102">如何：使控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="1c3fe-102">How to: Align a Control to the Edges of Forms</span></span>

<span data-ttu-id="1c3fe-103">通过设置 <xref:System.Windows.Forms.Control.Dock%2A> 属性，可以使控件与窗体的边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="1c3fe-103">You can make your control align to the edge of your forms by setting the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span> <span data-ttu-id="1c3fe-104">此属性指定控件在窗体中的驻留位置。</span><span class="sxs-lookup"><span data-stu-id="1c3fe-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="1c3fe-105">可以将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为下列值：</span><span class="sxs-lookup"><span data-stu-id="1c3fe-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>

|<span data-ttu-id="1c3fe-106">设置</span><span class="sxs-lookup"><span data-stu-id="1c3fe-106">Setting</span></span>|<span data-ttu-id="1c3fe-107">控件上的效果</span><span class="sxs-lookup"><span data-stu-id="1c3fe-107">Effect on your control</span></span>|
|-------------|----------------------------|
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="1c3fe-108">停靠到窗体底部。</span><span class="sxs-lookup"><span data-stu-id="1c3fe-108">Docks to the bottom of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="1c3fe-109">占据窗体中的所有剩余空间。</span><span class="sxs-lookup"><span data-stu-id="1c3fe-109">Fills all remaining space in the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="1c3fe-110">停靠到窗体的左侧。</span><span class="sxs-lookup"><span data-stu-id="1c3fe-110">Docks to the left side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="1c3fe-111">不在任何位置停靠，它显示在由 <xref:System.Windows.Forms.Control.Location%2A> 属性指定的位置。</span><span class="sxs-lookup"><span data-stu-id="1c3fe-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="1c3fe-112">停靠到窗体的右侧。</span><span class="sxs-lookup"><span data-stu-id="1c3fe-112">Docks to the right side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="1c3fe-113">停靠到窗体的顶部。</span><span class="sxs-lookup"><span data-stu-id="1c3fe-113">Docks to the top of the form.</span></span>|

<span data-ttu-id="1c3fe-114">Visual Studio 中具有对此功能的设计时支持。</span><span class="sxs-lookup"><span data-stu-id="1c3fe-114">There is design-time support for this feature in Visual Studio.</span></span>

## <a name="set-the-dock-property-for-your-control-at-run-time"></a><span data-ttu-id="1c3fe-115">在运行时设置控件的 Dock 属性</span><span class="sxs-lookup"><span data-stu-id="1c3fe-115">Set the Dock property for your control at run time</span></span>

<span data-ttu-id="1c3fe-116">在代码中将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="1c3fe-116">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to the appropriate value in code.</span></span>

```vb
' To set the Dock property internally.
Me.Dock = DockStyle.Top
' To set the Dock property from another object.
UserControl1.Dock = DockStyle.Top
```

```csharp
// To set the Dock property internally.
this.Dock = DockStyle.Top;
// To set the Dock property from another object.
UserControl1.Dock = DockStyle.Top;
```

## <a name="see-also"></a><span data-ttu-id="1c3fe-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c3fe-117">See also</span></span>

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1c3fe-118">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="1c3fe-118">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="1c3fe-119">如何：在 FlowLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="1c3fe-119">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="1c3fe-120">如何：在 TableLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="1c3fe-120">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="1c3fe-121">AutoSize 属性概述</span><span class="sxs-lookup"><span data-stu-id="1c3fe-121">AutoSize Property Overview</span></span>](autosize-property-overview.md)
