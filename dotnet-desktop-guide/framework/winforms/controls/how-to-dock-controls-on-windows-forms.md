---
title: 停靠控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 02f1c26dcb322a39c41781c83d8c820bd2fd27e0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972039"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="d0a90-102">如何：在 Windows 窗体上停靠控件</span><span class="sxs-lookup"><span data-stu-id="d0a90-102">How to: Dock controls on Windows Forms</span></span>

<span data-ttu-id="d0a90-103">您可以将控件停靠到窗体的边缘，或者使控件填充控件的容器 () 窗体或容器控件。</span><span class="sxs-lookup"><span data-stu-id="d0a90-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="d0a90-104">例如，Windows 资源管理器将其控件停靠在 <xref:System.Windows.Forms.TreeView> 窗口的左侧，并将其 <xref:System.Windows.Forms.ListView> 控件停靠到窗口的右侧。</span><span class="sxs-lookup"><span data-stu-id="d0a90-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="d0a90-105">使用 <xref:System.Windows.Forms.Control.Dock%2A> 所有可见 Windows 窗体控件的属性来定义停靠模式。</span><span class="sxs-lookup"><span data-stu-id="d0a90-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>

> [!NOTE]
> <span data-ttu-id="d0a90-106">控件按 z 顺序反向停靠。</span><span class="sxs-lookup"><span data-stu-id="d0a90-106">Controls are docked in reverse z-order.</span></span>

<span data-ttu-id="d0a90-107"><xref:System.Windows.Forms.Control.Dock%2A>属性与 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性交互。</span><span class="sxs-lookup"><span data-stu-id="d0a90-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="d0a90-108">有关详细信息，请参阅 [AutoSize 属性概述](autosize-property-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d0a90-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="to-dock-a-control"></a><span data-ttu-id="d0a90-109">停靠控件</span><span class="sxs-lookup"><span data-stu-id="d0a90-109">To dock a control</span></span>

1. <span data-ttu-id="d0a90-110">在 Visual Studio 中，选择要停靠的控件。</span><span class="sxs-lookup"><span data-stu-id="d0a90-110">In Visual Studio, select the control that you want to dock.</span></span>

2. <span data-ttu-id="d0a90-111">在 " **属性** " 窗口中，单击属性右侧的箭头 <xref:System.Windows.Forms.Control.Dock%2A> 。</span><span class="sxs-lookup"><span data-stu-id="d0a90-111">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>

   <span data-ttu-id="d0a90-112">将显示一个编辑器，其中显示一系列表示窗体边缘和中心的框。</span><span class="sxs-lookup"><span data-stu-id="d0a90-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>

3. <span data-ttu-id="d0a90-113">单击表示要停靠控件的窗体边缘的按钮。</span><span class="sxs-lookup"><span data-stu-id="d0a90-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="d0a90-114">若要填充控件的窗体或容器控件的内容，请单击中心框。</span><span class="sxs-lookup"><span data-stu-id="d0a90-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="d0a90-115">单击 " **(无")** 禁用停靠。</span><span class="sxs-lookup"><span data-stu-id="d0a90-115">Click **(none)** to disable docking.</span></span>

   <span data-ttu-id="d0a90-116">控件会自动调整控件的大小以适应停靠边缘的边界。</span><span class="sxs-lookup"><span data-stu-id="d0a90-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d0a90-117">继承的控件必须能够 `Protected` 停靠。</span><span class="sxs-lookup"><span data-stu-id="d0a90-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="d0a90-118">若要更改控件的访问级别，请在 "**属性**" 窗口中设置其 "**修饰符**" 属性。</span><span class="sxs-lookup"><span data-stu-id="d0a90-118">To change the access level of a control, set its **Modifier** property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0a90-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0a90-119">See also</span></span>

- [<span data-ttu-id="d0a90-120">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="d0a90-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="d0a90-121">标记单个 Windows 窗体控件并提供它们的快捷方式</span><span class="sxs-lookup"><span data-stu-id="d0a90-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="d0a90-122">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="d0a90-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="d0a90-123">根据功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="d0a90-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="d0a90-124">如何：在 FlowLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="d0a90-124">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="d0a90-125">如何：在 TableLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="d0a90-125">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="d0a90-126">AutoSize 属性概述</span><span class="sxs-lookup"><span data-stu-id="d0a90-126">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="d0a90-127">如何：在 Windows 窗体上锚定控件</span><span class="sxs-lookup"><span data-stu-id="d0a90-127">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
