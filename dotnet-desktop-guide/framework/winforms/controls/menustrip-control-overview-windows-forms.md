---
title: MenuStrip 控件概述
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: a536d13cb7be3f4e4e4a085e1a4da1b0899b3a0c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972609"
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="96859-102">MenuStrip 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="96859-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="96859-103">菜单通过保存按公共主题分组的命令向用户公开功能。</span><span class="sxs-lookup"><span data-stu-id="96859-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="96859-104"><xref:System.Windows.Forms.MenuStrip>控件是在 .NET Framework 2.0 版中引入的。</span><span class="sxs-lookup"><span data-stu-id="96859-104">The <xref:System.Windows.Forms.MenuStrip> control was introduced in version 2.0 of the .NET Framework.</span></span> <span data-ttu-id="96859-105">借助 <xref:System.Windows.Forms.MenuStrip> 控件，可以轻松创建菜单，如 Microsoft Office 中找到的菜单。</span><span class="sxs-lookup"><span data-stu-id="96859-105">With the <xref:System.Windows.Forms.MenuStrip> control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="96859-106"><xref:System.Windows.Forms.MenuStrip>控件支持多文档界面 (MDI) 和菜单合并、工具提示和溢出。</span><span class="sxs-lookup"><span data-stu-id="96859-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="96859-107">您可以通过添加访问键、快捷键、复选标记、图像和分隔栏来增强菜单的可用性和可读性。</span><span class="sxs-lookup"><span data-stu-id="96859-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="96859-108"><xref:System.Windows.Forms.MenuStrip>控件将替换并添加到控件中的功能 <xref:System.Windows.Forms.MainMenu> ; 但是， <xref:System.Windows.Forms.MainMenu> 会保留控件以实现向后兼容性和将来使用（如果你选择）。</span><span class="sxs-lookup"><span data-stu-id="96859-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="96859-109">使用 MenuStrip 控件的方式</span><span class="sxs-lookup"><span data-stu-id="96859-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="96859-110">使用 <xref:System.Windows.Forms.MenuStrip> 控件可以：</span><span class="sxs-lookup"><span data-stu-id="96859-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
- <span data-ttu-id="96859-111">创建可轻松自定义的常用菜单，这些菜单支持高级用户界面和布局功能，如文本和图像顺序和对齐方式、拖放操作、MDI、溢出以及访问菜单命令的其他模式。</span><span class="sxs-lookup"><span data-stu-id="96859-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
- <span data-ttu-id="96859-112">支持操作系统的典型外观和行为。</span><span class="sxs-lookup"><span data-stu-id="96859-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
- <span data-ttu-id="96859-113">以一致的方式处理所有容器和包含项的事件，其方式与处理其他控件的事件的方式相同。</span><span class="sxs-lookup"><span data-stu-id="96859-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="96859-114">下表显示了和关联类的一些特别重要的属性 <xref:System.Windows.Forms.MenuStrip> 。</span><span class="sxs-lookup"><span data-stu-id="96859-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="96859-115">属性</span><span class="sxs-lookup"><span data-stu-id="96859-115">Property</span></span>|<span data-ttu-id="96859-116">描述</span><span class="sxs-lookup"><span data-stu-id="96859-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="96859-117">获取或设置 <xref:System.Windows.Forms.ToolStripMenuItem> 用于显示 MDI 子窗体列表的。</span><span class="sxs-lookup"><span data-stu-id="96859-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="96859-118">获取或设置如何在 MDI 应用程序中将子菜单与父菜单合并。</span><span class="sxs-lookup"><span data-stu-id="96859-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="96859-119">获取或设置在 MDI 应用程序中的菜单内的合并项的位置。</span><span class="sxs-lookup"><span data-stu-id="96859-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="96859-120">获取或设置一个值，该值指示窗体是否为 MDI 子窗体的容器。</span><span class="sxs-lookup"><span data-stu-id="96859-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="96859-121">获取或设置一个值，该值指示是否显示的工具提示 <xref:System.Windows.Forms.MenuStrip> 。</span><span class="sxs-lookup"><span data-stu-id="96859-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="96859-122">获取或设置一个值，该值指示 <xref:System.Windows.Forms.MenuStrip> 是否支持溢出功能。</span><span class="sxs-lookup"><span data-stu-id="96859-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="96859-123">获取或设置与 <xref:System.Windows.Forms.ToolStripMenuItem> 关联的快捷键。</span><span class="sxs-lookup"><span data-stu-id="96859-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="96859-124">获取或设置一个值，该值指示与 <xref:System.Windows.Forms.ToolStripMenuItem> 关联的快捷键是否显示在 <xref:System.Windows.Forms.ToolStripMenuItem> 旁边。</span><span class="sxs-lookup"><span data-stu-id="96859-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="96859-125">下表显示了重要的 <xref:System.Windows.Forms.MenuStrip> 伴生类。</span><span class="sxs-lookup"><span data-stu-id="96859-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="96859-126">类</span><span class="sxs-lookup"><span data-stu-id="96859-126">Class</span></span>|<span data-ttu-id="96859-127">描述</span><span class="sxs-lookup"><span data-stu-id="96859-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="96859-128">表示 <xref:System.Windows.Forms.MenuStrip> 或 <xref:System.Windows.Forms.ContextMenuStrip> 上显示的可选选项。</span><span class="sxs-lookup"><span data-stu-id="96859-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="96859-129">表示快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="96859-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="96859-130">表示一个控件，该控件允许用户从列表中选择单个项（当用户单击 <xref:System.Windows.Forms.ToolStripDropDownButton> 或更高级别菜单项时显示）。</span><span class="sxs-lookup"><span data-stu-id="96859-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="96859-131">为 <xref:System.Windows.Forms.ToolStripItem> 在单击时显示的下拉项的控件提供基本功能。</span><span class="sxs-lookup"><span data-stu-id="96859-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96859-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96859-132">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
