---
title: ToolStrip 控件概述
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 931a6a0ea09f9b684b793c05cb1c3db8ee8fb7c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973075"
---
# <a name="toolstrip-control-overview-windows-forms"></a><span data-ttu-id="81994-102">ToolStrip 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="81994-102">ToolStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="81994-103">Windows 窗体 <xref:System.Windows.Forms.ToolStrip> 控件及其关联的类提供一个公共框架，用于将用户界面元素合并到工具栏、状态栏和菜单中。</span><span class="sxs-lookup"><span data-stu-id="81994-103">The Windows Forms <xref:System.Windows.Forms.ToolStrip> control and its associated classes provide a common framework for combining user interface elements into toolbars, status bars, and menus.</span></span> <span data-ttu-id="81994-104"><xref:System.Windows.Forms.ToolStrip> 控件提供丰富的设计时体验，其中包括就地激活和编辑、自定义布局和漂浮（这是工具栏共享水平或垂直空间的能力）。</span><span class="sxs-lookup"><span data-stu-id="81994-104"><xref:System.Windows.Forms.ToolStrip> controls offer a rich design-time experience that includes in-place activation and editing, custom layout, and rafting, which is the ability of toolbars to share horizontal or vertical space.</span></span>  
  
 <span data-ttu-id="81994-105">尽管 <xref:System.Windows.Forms.ToolStrip> 在以前的版本中将替换和添加到控件中的功能，但仍 <xref:System.Windows.Forms.ToolBar> 会保留以实现向后兼容性和将来使用（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="81994-105">Although <xref:System.Windows.Forms.ToolStrip> replaces and adds functionality to the control in previous versions, <xref:System.Windows.Forms.ToolBar> is retained for both backward compatibility and future use if desired.</span></span>  
  
## <a name="features-of-the-toolstrip-controls"></a><span data-ttu-id="81994-106">ToolStrip 控件的功能</span><span class="sxs-lookup"><span data-stu-id="81994-106">Features of the ToolStrip Controls</span></span>  
 <span data-ttu-id="81994-107">使用 <xref:System.Windows.Forms.ToolStrip> 控件可以：</span><span class="sxs-lookup"><span data-stu-id="81994-107">Use the <xref:System.Windows.Forms.ToolStrip> control to:</span></span>  
  
- <span data-ttu-id="81994-108">跨容器显示公共用户界面。</span><span class="sxs-lookup"><span data-stu-id="81994-108">Present a common user interface across containers.</span></span>  
  
- <span data-ttu-id="81994-109">创建可轻松自定义的常用工具栏，这些工具栏支持高级用户界面和布局功能，如停靠、漂浮、带有文本和图像的按钮、下拉按钮和控件、溢出按钮以及项的运行时重新排序 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="81994-109">Create easily customized, commonly employed toolbars that support advanced user interface and layout features, such as docking, rafting, buttons with text and images, drop-down buttons and controls, overflow buttons, and run-time reordering of <xref:System.Windows.Forms.ToolStrip> items.</span></span>  
  
- <span data-ttu-id="81994-110">支持溢出和运行时项重新排序。</span><span class="sxs-lookup"><span data-stu-id="81994-110">Support overflow and run-time item reordering.</span></span> <span data-ttu-id="81994-111">如果没有足够空间在中显示项，溢出功能会将项移动到下拉菜单 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="81994-111">The overflow feature moves items to a drop-down menu when there is not enough room to display them in a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
- <span data-ttu-id="81994-112">通过常见的呈现模型支持操作系统的典型外观和行为。</span><span class="sxs-lookup"><span data-stu-id="81994-112">Support the typical appearance and behavior of the operating system through a common rendering model.</span></span>  
  
- <span data-ttu-id="81994-113">以一致的方式处理所有容器和包含项的事件，其方式与处理其他控件的事件的方式相同。</span><span class="sxs-lookup"><span data-stu-id="81994-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
- <span data-ttu-id="81994-114">将项从一项拖动 <xref:System.Windows.Forms.ToolStrip> 到另一个 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="81994-114">Drag items from one <xref:System.Windows.Forms.ToolStrip> to another or within a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
- <span data-ttu-id="81994-115">在中创建具有高级布局的下拉控件和用户界面类型编辑器 <xref:System.Windows.Forms.ToolStripDropDown> 。</span><span class="sxs-lookup"><span data-stu-id="81994-115">Create drop-down controls and user interface type editors with advanced layouts in a <xref:System.Windows.Forms.ToolStripDropDown>.</span></span>  
  
 <span data-ttu-id="81994-116">使用 <xref:System.Windows.Forms.ToolStripControlHost> 类来使用上的其他控件 <xref:System.Windows.Forms.ToolStrip> ，并获取 <xref:System.Windows.Forms.ToolStrip> 这些控件的功能。</span><span class="sxs-lookup"><span data-stu-id="81994-116">Use the <xref:System.Windows.Forms.ToolStripControlHost> class to use other controls on a <xref:System.Windows.Forms.ToolStrip> and gain <xref:System.Windows.Forms.ToolStrip> functionality for them.</span></span>  
  
 <span data-ttu-id="81994-117">可以通过将 <xref:System.Windows.Forms.ToolStripRenderer> 、 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 和 <xref:System.Windows.Forms.ToolStripManager> 与 <xref:System.Windows.Forms.ToolStripRenderMode> 和 <xref:System.Windows.Forms.ToolStripManagerRenderMode> 枚举一起使用来扩展功能并修改外观和行为。</span><span class="sxs-lookup"><span data-stu-id="81994-117">You can extend the functionality and modify the appearance and behavior by using the <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, and <xref:System.Windows.Forms.ToolStripManager> along with the <xref:System.Windows.Forms.ToolStripRenderMode> and <xref:System.Windows.Forms.ToolStripManagerRenderMode> enumerations.</span></span>  
  
 <span data-ttu-id="81994-118"><xref:System.Windows.Forms.ToolStrip>控件高度可配置且可扩展，并且提供了许多属性、方法和事件来自定义外观和行为。</span><span class="sxs-lookup"><span data-stu-id="81994-118">The <xref:System.Windows.Forms.ToolStrip> control is highly configurable and extensible, and it provides many properties, methods, and events to customize appearance and behavior.</span></span> <span data-ttu-id="81994-119">下面是一些值得注意的成员：</span><span class="sxs-lookup"><span data-stu-id="81994-119">Below are some noteworthy members:</span></span>  
  
### <a name="important-toolstrip-members"></a><span data-ttu-id="81994-120">重要 ToolStrip 成员</span><span class="sxs-lookup"><span data-stu-id="81994-120">Important ToolStrip Members</span></span>  
  
|<span data-ttu-id="81994-121">名称</span><span class="sxs-lookup"><span data-stu-id="81994-121">Name</span></span>|<span data-ttu-id="81994-122">描述</span><span class="sxs-lookup"><span data-stu-id="81994-122">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|<span data-ttu-id="81994-123">获取或设置将停靠到的父容器的边缘 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="81994-123">Gets or sets which edge of the parent container a <xref:System.Windows.Forms.ToolStrip> is docked to.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|<span data-ttu-id="81994-124">获取或设置一个用于指示是否专门由 <xref:System.Windows.Forms.ToolStrip> 类处理拖放和项重新排序操作的值。</span><span class="sxs-lookup"><span data-stu-id="81994-124">Gets or sets a value indicating whether drag-and-drop and item reordering are handled privately by the <xref:System.Windows.Forms.ToolStrip> class.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|<span data-ttu-id="81994-125">获取或设置一个值，该值指示如何对 <xref:System.Windows.Forms.ToolStrip> 项进行布局。</span><span class="sxs-lookup"><span data-stu-id="81994-125">Gets or sets a value indicating how the <xref:System.Windows.Forms.ToolStrip> lays out its items.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|<span data-ttu-id="81994-126">获取或设置 <xref:System.Windows.Forms.ToolStripItem> 是附加到或，还是 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripOverflowButton> 可以在两者之间浮动。</span><span class="sxs-lookup"><span data-stu-id="81994-126">Gets or sets whether a <xref:System.Windows.Forms.ToolStripItem> is attached to the <xref:System.Windows.Forms.ToolStrip> or <xref:System.Windows.Forms.ToolStripOverflowButton> or can float between the two.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|<span data-ttu-id="81994-127">获取一个值，该值指示在 <xref:System.Windows.Forms.ToolStripItem> 单击时是否在下拉列表中显示其他项 <xref:System.Windows.Forms.ToolStripItem> 。</span><span class="sxs-lookup"><span data-stu-id="81994-127">Gets a value indicating whether a <xref:System.Windows.Forms.ToolStripItem> displays other items in a drop-down list when the <xref:System.Windows.Forms.ToolStripItem> is clicked.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|<span data-ttu-id="81994-128">获取 <xref:System.Windows.Forms.ToolStripItem>，它是启用了溢出的 <xref:System.Windows.Forms.ToolStrip> 的“溢出”按钮。</span><span class="sxs-lookup"><span data-stu-id="81994-128">Gets the <xref:System.Windows.Forms.ToolStripItem> that is the overflow button for a <xref:System.Windows.Forms.ToolStrip> with overflow enabled.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|<span data-ttu-id="81994-129">获取或设置一个，它 <xref:System.Windows.Forms.ToolStripRenderer> 用于自定义的外观和行为 (的外观和感觉) <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="81994-129">Gets or sets a <xref:System.Windows.Forms.ToolStripRenderer> used to customize the appearance and behavior (look and feel) of a <xref:System.Windows.Forms.ToolStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|<span data-ttu-id="81994-130">获取或设置要应用于 <xref:System.Windows.Forms.ToolStrip> 的绘制样式。</span><span class="sxs-lookup"><span data-stu-id="81994-130">Gets or sets the painting styles to be applied to the <xref:System.Windows.Forms.ToolStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|<span data-ttu-id="81994-131">在 <xref:System.Windows.Forms.ToolStrip.Renderer%2A> 属性更改时引发。</span><span class="sxs-lookup"><span data-stu-id="81994-131">Raised when the <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property changes.</span></span>|  
  
 <span data-ttu-id="81994-132"><xref:System.Windows.Forms.ToolStrip>通过使用多个伴生类来实现控件的灵活性。</span><span class="sxs-lookup"><span data-stu-id="81994-132">The <xref:System.Windows.Forms.ToolStrip> control's flexibility is achieved through the use of a number of companion classes.</span></span> <span data-ttu-id="81994-133">下面是一些最值得注意的事项：</span><span class="sxs-lookup"><span data-stu-id="81994-133">Below are some of the most noteworthy:</span></span>  
  
### <a name="important-toolstrip-companion-classes"></a><span data-ttu-id="81994-134">重要的 ToolStrip 伴生类</span><span class="sxs-lookup"><span data-stu-id="81994-134">Important ToolStrip Companion Classes</span></span>  
  
|<span data-ttu-id="81994-135">名称</span><span class="sxs-lookup"><span data-stu-id="81994-135">Name</span></span>|<span data-ttu-id="81994-136">描述</span><span class="sxs-lookup"><span data-stu-id="81994-136">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|<span data-ttu-id="81994-137">替换类并向类添加功能 <xref:System.Windows.Forms.MainMenu> 。</span><span class="sxs-lookup"><span data-stu-id="81994-137">Replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> class.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip>|<span data-ttu-id="81994-138">替换类并向类添加功能 <xref:System.Windows.Forms.StatusBar> 。</span><span class="sxs-lookup"><span data-stu-id="81994-138">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> class.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="81994-139">替换类并向类添加功能 <xref:System.Windows.Forms.ContextMenu> 。</span><span class="sxs-lookup"><span data-stu-id="81994-139">Replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> class.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem>|<span data-ttu-id="81994-140">管理 <xref:System.Windows.Forms.ToolStrip> 、 <xref:System.Windows.Forms.ToolStripControlHost> 或可以包含的所有元素的事件和布局的抽象基类 <xref:System.Windows.Forms.ToolStripDropDown> 。</span><span class="sxs-lookup"><span data-stu-id="81994-140">Abstract base class that manages events and layout for all the elements that a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, or <xref:System.Windows.Forms.ToolStripDropDown> can contain.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="81994-141">提供一个容器，该容器在窗体的每一侧有一个面板，可通过多种方式排列控件。</span><span class="sxs-lookup"><span data-stu-id="81994-141">Provides a container with a panel on each side of the form in which controls can be arranged in various ways.</span></span>|  
|<xref:System.Windows.Forms.ToolStripRenderer>|<span data-ttu-id="81994-142">处理 <xref:System.Windows.Forms.ToolStrip> 对象的绘制功能。</span><span class="sxs-lookup"><span data-stu-id="81994-142">Handles the painting functionality for <xref:System.Windows.Forms.ToolStrip> objects.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|<span data-ttu-id="81994-143">提供 Microsoft Office 样式的外观。</span><span class="sxs-lookup"><span data-stu-id="81994-143">Provides Microsoft Office-style appearance.</span></span>|  
|<xref:System.Windows.Forms.ToolStripManager>|<span data-ttu-id="81994-144">控制 <xref:System.Windows.Forms.ToolStrip> 的呈现和漂浮，以及 <xref:System.Windows.Forms.MenuStrip>、<xref:System.Windows.Forms.ToolStripDropDownMenu> 和 <xref:System.Windows.Forms.ToolStripMenuItem> 对象的合并。</span><span class="sxs-lookup"><span data-stu-id="81994-144">Controls <xref:System.Windows.Forms.ToolStrip> rendering and rafting, and the merging of <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, and <xref:System.Windows.Forms.ToolStripMenuItem> objects.</span></span>|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|<span data-ttu-id="81994-145">指定 (自定义、Windows XP 或 Microsoft Office Professional) 应用于 <xref:System.Windows.Forms.ToolStrip> 窗体中包含的多个对象的绘制样式。</span><span class="sxs-lookup"><span data-stu-id="81994-145">Specifies the painting style (custom, Windows XP, or Microsoft Office Professional) applied to multiple <xref:System.Windows.Forms.ToolStrip> objects contained in a form.</span></span>|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|<span data-ttu-id="81994-146">指定 (自定义、Windows XP 或 Microsoft Office Professional) 应用于 <xref:System.Windows.Forms.ToolStrip> 窗体中包含的一个对象的绘制样式。</span><span class="sxs-lookup"><span data-stu-id="81994-146">Specifies the painting style (custom, Windows XP, or Microsoft Office Professional) applied to one <xref:System.Windows.Forms.ToolStrip> object contained in a form.</span></span>|  
|<xref:System.Windows.Forms.ToolStripControlHost>|<span data-ttu-id="81994-147">承载并非专门 <xref:System.Windows.Forms.ToolStrip> 控制但需要其功能的其他控件 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="81994-147">Hosts other controls that are not specifically <xref:System.Windows.Forms.ToolStrip> controls but for which you want <xref:System.Windows.Forms.ToolStrip> functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|<span data-ttu-id="81994-148">指定 <xref:System.Windows.Forms.ToolStripItem> 是要在主上还是在溢出上进行布局 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="81994-148">Specifies whether a <xref:System.Windows.Forms.ToolStripItem> is to be laid out on the main <xref:System.Windows.Forms.ToolStrip>, on the overflow <xref:System.Windows.Forms.ToolStrip>, or neither.</span></span>|  
  
 <span data-ttu-id="81994-149">有关详细信息，请参阅 [Toolstrip 技术摘要](toolstrip-technology-summary.md) 和 [Toolstrip 控件体系结构](toolstrip-control-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="81994-149">For more information, see [ToolStrip Technology Summary](toolstrip-technology-summary.md) and [ToolStrip Control Architecture](toolstrip-control-architecture.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81994-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81994-150">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
