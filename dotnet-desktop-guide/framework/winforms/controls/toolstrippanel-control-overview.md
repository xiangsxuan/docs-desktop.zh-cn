---
title: ToolStripPanel 控件概述
ms.date: 03/30/2017
f1_keywords:
- ToolStripPanel
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms], about ToolStripPanel control
ms.assetid: ce54a60c-5eba-4b4c-bd77-cf0748a666cc
ms.openlocfilehash: 154a1b77a9312b19fe8dd51a4f603f29a219ec50
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973065"
---
# <a name="toolstrippanel-control-overview"></a><span data-ttu-id="c2e60-102">ToolStripPanel 控件概述</span><span class="sxs-lookup"><span data-stu-id="c2e60-102">ToolStripPanel Control Overview</span></span>

<span data-ttu-id="c2e60-103">为 <xref:System.Windows.Forms.ToolStripPanel> 定位和漂浮 <xref:System.Windows.Forms.ToolStrip> 、和控件提供了一个区域 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.StatusStrip> 。</span><span class="sxs-lookup"><span data-stu-id="c2e60-103">A <xref:System.Windows.Forms.ToolStripPanel> provides a single area for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="c2e60-104">多个 <xref:System.Windows.Forms.ToolStrip> 控件根据的，垂直或水平堆叠 <xref:System.Windows.Forms.ToolStripPanelRow.Orientation%2A> <xref:System.Windows.Forms.ToolStripPanel> 。</span><span class="sxs-lookup"><span data-stu-id="c2e60-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically or horizontally depending on the <xref:System.Windows.Forms.ToolStripPanelRow.Orientation%2A> of the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>  
  
### <a name="important-toolstrippanel-members"></a><span data-ttu-id="c2e60-105">重要 ToolStripPanel 成员</span><span class="sxs-lookup"><span data-stu-id="c2e60-105">Important ToolStripPanel Members</span></span>  
  
|<span data-ttu-id="c2e60-106">名称</span><span class="sxs-lookup"><span data-stu-id="c2e60-106">Name</span></span>|<span data-ttu-id="c2e60-107">描述</span><span class="sxs-lookup"><span data-stu-id="c2e60-107">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripPanel.Orientation%2A>|<span data-ttu-id="c2e60-108">获取或设置一个值，该值指示 <xref:System.Windows.Forms.ToolStripPanel> 是水平方向还是垂直方向。</span><span class="sxs-lookup"><span data-stu-id="c2e60-108">Gets or sets a value indicating the horizontal or vertical orientation of the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Renderer%2A>|<span data-ttu-id="c2e60-109">获取或设置用来自定义 <xref:System.Windows.Forms.ToolStripRenderer> 的外观的 <xref:System.Windows.Forms.ToolStripPanel>。</span><span class="sxs-lookup"><span data-stu-id="c2e60-109">Gets or sets a <xref:System.Windows.Forms.ToolStripRenderer> used to customize the appearance of a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.RenderMode%2A>|<span data-ttu-id="c2e60-110">获取或设置要应用于 <xref:System.Windows.Forms.ToolStripPanel> 的绘制样式。</span><span class="sxs-lookup"><span data-stu-id="c2e60-110">Gets or sets the painting styles to be applied to the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.RowMargin%2A>|<span data-ttu-id="c2e60-111">获取或设置与之间的间距（以像素为单位） <xref:System.Windows.Forms.ToolStripPanelRow> <xref:System.Windows.Forms.ToolStripPanel> 。</span><span class="sxs-lookup"><span data-stu-id="c2e60-111">Gets or sets the spacing, in pixels, between the <xref:System.Windows.Forms.ToolStripPanelRow> and the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Rows%2A>|<span data-ttu-id="c2e60-112">获取 <xref:System.Windows.Forms.ToolStripPanelRow> 此中的 <xref:System.Windows.Forms.ToolStripPanel> 。</span><span class="sxs-lookup"><span data-stu-id="c2e60-112">Gets the <xref:System.Windows.Forms.ToolStripPanelRow> in this <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Join%2A>|<span data-ttu-id="c2e60-113">将 <xref:System.Windows.Forms.ToolStrip> 添加到 <xref:System.Windows.Forms.ToolStripPanel>。</span><span class="sxs-lookup"><span data-stu-id="c2e60-113">Adds a <xref:System.Windows.Forms.ToolStrip> to a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2e60-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2e60-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- <xref:System.Windows.Forms.ToolStripContentPanel>
- <span data-ttu-id="c2e60-115">[ToolStrip 示例](/previous-versions/visualstudio/visual-studio-2008/ms181005(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c2e60-115">[ToolStrip Sample](/previous-versions/visualstudio/visual-studio-2008/ms181005(v=vs.90))</span></span>
