---
title: ToolStripContainer 控件概述
ms.date: 03/30/2017
f1_keywords:
- ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
ms.openlocfilehash: c279316c2a372a1498707b27ec8658813306304b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973068"
---
# <a name="toolstripcontainer-control-overview"></a><span data-ttu-id="fcdf6-102">ToolStripContainer 控件概述</span><span class="sxs-lookup"><span data-stu-id="fcdf6-102">ToolStripContainer Control Overview</span></span>
<span data-ttu-id="fcdf6-103">在 <xref:System.Windows.Forms.ToolStripContainer> 其左、右、上和下有一个用于定位和漂浮 <xref:System.Windows.Forms.ToolStrip> 、 <xref:System.Windows.Forms.MenuStrip> 和控件的面板 <xref:System.Windows.Forms.StatusStrip> 。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-103">A <xref:System.Windows.Forms.ToolStripContainer> has panels on its left, right, top, and bottom sides for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="fcdf6-104">如果将多个 <xref:System.Windows.Forms.ToolStrip> 控件放置在 <xref:System.Windows.Forms.ToolStripContainer> 左侧或右侧，它们会垂直堆叠。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically if you put them in the left or right <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="fcdf6-105">如果将其放置在 <xref:System.Windows.Forms.ToolStripContainer> 顶部或底部，则水平堆叠。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-105">They stack horizontally if you put them in the top or bottom <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="fcdf6-106">可使用 <xref:System.Windows.Forms.ToolStripContainer> 的中央 <xref:System.Windows.Forms.ToolStripContentPanel> 将传统控件放置在窗体上。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-106">You can use the central <xref:System.Windows.Forms.ToolStripContentPanel> of the <xref:System.Windows.Forms.ToolStripContainer> to position traditional controls on the form.</span></span>  
  
 <span data-ttu-id="fcdf6-107">任何或所有 <xref:System.Windows.Forms.ToolStripContainer> 控件都可在设计时选择且可删除。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-107">Any or all <xref:System.Windows.Forms.ToolStripContainer> controls are directly selectable at design time and can be deleted.</span></span> <span data-ttu-id="fcdf6-108">的每个面板 <xref:System.Windows.Forms.ToolStripContainer> 都可展开和折叠，并使用它所包含的控件调整其大小。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-108">Each panel of a <xref:System.Windows.Forms.ToolStripContainer> is expandable and collapsible, and resizes with the controls that it contains.</span></span>  
  
### <a name="important-toolstripcontainer-members"></a><span data-ttu-id="fcdf6-109">重要 ToolStripContainer 成员</span><span class="sxs-lookup"><span data-stu-id="fcdf6-109">Important ToolStripContainer Members</span></span>  
  
|<span data-ttu-id="fcdf6-110">名称</span><span class="sxs-lookup"><span data-stu-id="fcdf6-110">Name</span></span>|<span data-ttu-id="fcdf6-111">描述</span><span class="sxs-lookup"><span data-stu-id="fcdf6-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<span data-ttu-id="fcdf6-112">获取 <xref:System.Windows.Forms.ToolStripContainer> 的底部面板。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-112">Gets the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<span data-ttu-id="fcdf6-113">获取或设置一个值，该值指示 <xref:System.Windows.Forms.ToolStripContainer> 的底部面板是否可见。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-113">Gets or sets a value indicating whether the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<span data-ttu-id="fcdf6-114">获取 <xref:System.Windows.Forms.ToolStripContainer> 的左面板。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-114">Gets the left panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<span data-ttu-id="fcdf6-115">获取或设置一个值，该值指示 <xref:System.Windows.Forms.ToolStripContainer> 的左面板是否可见。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-115">Gets or sets a value indicating whether the left panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<span data-ttu-id="fcdf6-116">获取 <xref:System.Windows.Forms.ToolStripContainer> 的右面板。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-116">Gets the right panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<span data-ttu-id="fcdf6-117">获取或设置一个值，该值指示 <xref:System.Windows.Forms.ToolStripContainer> 的右面板是否可见。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-117">Gets or sets a value indicating whether the right panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<span data-ttu-id="fcdf6-118">获取 <xref:System.Windows.Forms.ToolStripContainer> 的顶部面板。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-118">Gets the top panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<span data-ttu-id="fcdf6-119">获取或设置一个值，该值指示 <xref:System.Windows.Forms.ToolStripContainer> 的顶部面板是否可见。</span><span class="sxs-lookup"><span data-stu-id="fcdf6-119">Gets or sets a value indicating whether the top panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fcdf6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fcdf6-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- <xref:System.Windows.Forms.ToolStripContentPanel>
