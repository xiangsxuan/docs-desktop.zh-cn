---
title: StatusStrip 控件概述
ms.date: 03/30/2017
f1_keywords:
- StatusStrip
helpviewer_keywords:
- StatusStrip control [Windows Forms], about StatusStrip control
- status bars [Windows Forms], about status bars
ms.assetid: c0d9bcbb-f8b8-46ef-bae2-4146b8c8ce99
ms.openlocfilehash: 9f2426220e8fe0f13d2098de8975be2ad2e43845
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971992"
---
# <a name="statusstrip-control-overview"></a><span data-ttu-id="3198f-102">StatusStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="3198f-102">StatusStrip Control Overview</span></span>

<span data-ttu-id="3198f-103"><xref:System.Windows.Forms.StatusStrip> 控件将显示有关在 <xref:System.Windows.Forms.Form> 上查看的对象、对象组件的信息或应用程序内与该对象操作相关的上下文信息。</span><span class="sxs-lookup"><span data-stu-id="3198f-103">A <xref:System.Windows.Forms.StatusStrip> control displays information about an object being viewed on a <xref:System.Windows.Forms.Form>, the object's components, or contextual information that relates to that object's operation within your application.</span></span> <span data-ttu-id="3198f-104">通常，<xref:System.Windows.Forms.StatusStrip> 控件由 <xref:System.Windows.Forms.ToolStripStatusLabel> 对象组成，每个对象将显示文本、图标或两者都有。</span><span class="sxs-lookup"><span data-stu-id="3198f-104">Typically, a <xref:System.Windows.Forms.StatusStrip> control consists of <xref:System.Windows.Forms.ToolStripStatusLabel> objects, each of which displays text, an icon, or both.</span></span> <span data-ttu-id="3198f-105"><xref:System.Windows.Forms.StatusStrip> 也可以包括 <xref:System.Windows.Forms.ToolStripDropDownButton>、<xref:System.Windows.Forms.ToolStripSplitButton> 和 <xref:System.Windows.Forms.ToolStripProgressBar> 控件。</span><span class="sxs-lookup"><span data-stu-id="3198f-105">The <xref:System.Windows.Forms.StatusStrip> can also contain <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton>, and <xref:System.Windows.Forms.ToolStripProgressBar> controls.</span></span>  
  
 <span data-ttu-id="3198f-106">默认 <xref:System.Windows.Forms.StatusStrip> 没有面板。</span><span class="sxs-lookup"><span data-stu-id="3198f-106">The default <xref:System.Windows.Forms.StatusStrip> has no panels.</span></span> <span data-ttu-id="3198f-107">若要将面板添加到 <xref:System.Windows.Forms.StatusStrip>，则使用 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="3198f-107">To add panels to a <xref:System.Windows.Forms.StatusStrip>, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="3198f-108">广泛支持用于处理 <xref:System.Windows.Forms.StatusStrip> 项目和 Visual Studio 中的常见命令。</span><span class="sxs-lookup"><span data-stu-id="3198f-108">There is extensive support for handling <xref:System.Windows.Forms.StatusStrip> items and common commands in Visual Studio.</span></span>  
  
 <span data-ttu-id="3198f-109">另请参阅 [StatusStrip Items Collection Editor](/previous-versions/visualstudio/visual-studio-2010/ms233631(v=vs.100)) And [StatusStrip Tasks 对话框](/previous-versions/visualstudio/visual-studio-2010/ms233642(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="3198f-109">Also see [StatusStrip Items Collection Editor](/previous-versions/visualstudio/visual-studio-2010/ms233631(v=vs.100)) and [StatusStrip Tasks Dialog Box](/previous-versions/visualstudio/visual-studio-2010/ms233642(v=vs.100)).</span></span>  
  
 <span data-ttu-id="3198f-110">尽管 <xref:System.Windows.Forms.StatusStrip> 替换并扩展了早期版本的 <xref:System.Windows.Forms.StatusBar> 控件，但也可以选择保留 <xref:System.Windows.Forms.StatusBar> 以备向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="3198f-110">Although <xref:System.Windows.Forms.StatusStrip> replaces and extends the <xref:System.Windows.Forms.StatusBar> control of previous versions, <xref:System.Windows.Forms.StatusBar> is retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="important-statusstrip-members"></a><span data-ttu-id="3198f-111">重要 StatusStrip 成员</span><span class="sxs-lookup"><span data-stu-id="3198f-111">Important StatusStrip Members</span></span>  
  
|<span data-ttu-id="3198f-112">名称</span><span class="sxs-lookup"><span data-stu-id="3198f-112">Name</span></span>|<span data-ttu-id="3198f-113">描述</span><span class="sxs-lookup"><span data-stu-id="3198f-113">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.StatusStrip.CanOverflow%2A>|<span data-ttu-id="3198f-114">获取或设置一个值，该值指示 <xref:System.Windows.Forms.StatusStrip> 是否支持溢出功能。</span><span class="sxs-lookup"><span data-stu-id="3198f-114">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip.Stretch%2A>|<span data-ttu-id="3198f-115">获取或设置一个值，该值指示 <xref:System.Windows.Forms.StatusStrip> 是否在其 <xref:System.Windows.Forms.ToolStripContainer> 中从一端拉伸到了另一端。</span><span class="sxs-lookup"><span data-stu-id="3198f-115">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> stretches from end to end in its <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
  
### <a name="important-statusstrip-companion-classes"></a><span data-ttu-id="3198f-116">重要 StatusStrip 伴随类</span><span class="sxs-lookup"><span data-stu-id="3198f-116">Important StatusStrip Companion Classes</span></span>  
  
|<span data-ttu-id="3198f-117">名称</span><span class="sxs-lookup"><span data-stu-id="3198f-117">Name</span></span>|<span data-ttu-id="3198f-118">描述</span><span class="sxs-lookup"><span data-stu-id="3198f-118">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|<span data-ttu-id="3198f-119">表示 <xref:System.Windows.Forms.StatusStrip> 控件中的一个面板。</span><span class="sxs-lookup"><span data-stu-id="3198f-119">Represents a panel in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|<span data-ttu-id="3198f-120">显示一个相关联的 <xref:System.Windows.Forms.ToolStripDropDown>，用户可以从中选择单个项目。</span><span class="sxs-lookup"><span data-stu-id="3198f-120">Displays an associated <xref:System.Windows.Forms.ToolStripDropDown> from which the user can select a single item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|<span data-ttu-id="3198f-121">表示一个两部分的控件，其中包括一个标准按钮和一个下拉菜单。</span><span class="sxs-lookup"><span data-stu-id="3198f-121">Represents a two-part control that is a standard button and a drop-down menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|<span data-ttu-id="3198f-122">显示进程的完成状态。</span><span class="sxs-lookup"><span data-stu-id="3198f-122">Displays the completion state of a process.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3198f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3198f-123">See also</span></span>

- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>
