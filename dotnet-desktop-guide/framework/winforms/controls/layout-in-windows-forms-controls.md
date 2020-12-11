---
title: 控件布局
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windows Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
ms.openlocfilehash: ed8603e997e7d0c1ed7a2ebda6dc960726d32f45
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971100"
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="91f74-102">Windows 窗体控件的布局</span><span class="sxs-lookup"><span data-stu-id="91f74-102">Layout in Windows Forms Controls</span></span>

<span data-ttu-id="91f74-103">在窗体上精确地放置控件对于许多应用程序而言是高优先级。</span><span class="sxs-lookup"><span data-stu-id="91f74-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="91f74-104"><xref:System.Windows.Forms?displayProperty=nameWithType>命名空间提供了许多布局工具来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="91f74-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="91f74-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="91f74-105">In This Section</span></span>

<span data-ttu-id="91f74-106">[AutoSize 属性概述](autosize-property-overview.md)</span><span class="sxs-lookup"><span data-stu-id="91f74-106">[AutoSize Property Overview](autosize-property-overview.md)</span></span>\
<span data-ttu-id="91f74-107">描述 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性及其在布局中的角色。</span><span class="sxs-lookup"><span data-stu-id="91f74-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>

<span data-ttu-id="91f74-108">[Windows 窗体控件中的边距和填充](margin-and-padding-in-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="91f74-108">[Margin and Padding in Windows Forms Controls](margin-and-padding-in-windows-forms-controls.md)</span></span>\
<span data-ttu-id="91f74-109">描述 <xref:System.Windows.Forms.Control.Margin%2A> 和 <xref:System.Windows.Forms.Control.Padding%2A> 属性及其在布局中的角色。</span><span class="sxs-lookup"><span data-stu-id="91f74-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>

<span data-ttu-id="91f74-110">[如何：将控件与窗体边缘对齐](how-to-align-a-control-to-the-edges-of-forms.md)</span><span class="sxs-lookup"><span data-stu-id="91f74-110">[How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md)</span></span>\
<span data-ttu-id="91f74-111">演示如何使用属性将 <xref:System.Windows.Forms.Control.Dock%2A> 控件与它所占有窗体的边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="91f74-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="91f74-112">[如何：使用填充围绕 Windows 窗体控件创建边框](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)</span><span class="sxs-lookup"><span data-stu-id="91f74-112">[How to: Create a Border Around a Windows Forms Control Using Padding](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)</span></span>\
<span data-ttu-id="91f74-113">演示如何使用 <xref:System.Windows.Forms.Control.Padding%2A> 属性来概述控件。</span><span class="sxs-lookup"><span data-stu-id="91f74-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>

<span data-ttu-id="91f74-114">[如何：实现自定义布局引擎](how-to-implement-a-custom-layout-engine.md)</span><span class="sxs-lookup"><span data-stu-id="91f74-114">[How to: Implement a Custom Layout Engine](how-to-implement-a-custom-layout-engine.md)</span></span>\
<span data-ttu-id="91f74-115">演示如何实现 <xref:System.Windows.Forms.Layout.LayoutEngine> 以便排列 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="91f74-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>

## <a name="reference"></a><span data-ttu-id="91f74-116">参考</span><span class="sxs-lookup"><span data-stu-id="91f74-116">Reference</span></span>

<xref:System.Windows.Forms.TableLayoutPanel>\
<span data-ttu-id="91f74-117">提供关于 <xref:System.Windows.Forms.TableLayoutPanel> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="91f74-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

<xref:System.Windows.Forms.FlowLayoutPanel>\
<span data-ttu-id="91f74-118">提供关于 <xref:System.Windows.Forms.FlowLayoutPanel> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="91f74-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="91f74-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91f74-119">See also</span></span>

- [<span data-ttu-id="91f74-120">如何：在 FlowLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="91f74-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="91f74-121">如何：在 TableLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="91f74-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="91f74-122">如何：设计适合本地化的 Windows 窗体布局</span><span class="sxs-lookup"><span data-stu-id="91f74-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="91f74-123">TableLayoutPanel 控件中的自动调整大小行为</span><span class="sxs-lookup"><span data-stu-id="91f74-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](autosize-behavior-in-the-tablelayoutpanel-control.md)
