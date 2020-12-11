---
title: ContextMenuStrip 控件概述
ms.date: 03/30/2017
f1_keywords:
- ContextMenuStrip
helpviewer_keywords:
- context menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- shortcut menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- ContextMenuStrip control [Windows Forms], about ContextMenuStrip control
ms.assetid: 9787cdb3-88f1-4198-972f-eefd9524ce39
ms.openlocfilehash: e4a6add5297ba7db606ca1891e9279141f8d6d20
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970183"
---
# <a name="contextmenustrip-control-overview"></a><span data-ttu-id="dafe5-102">ContextMenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="dafe5-102">ContextMenuStrip Control Overview</span></span>
> [!NOTE]
> <span data-ttu-id="dafe5-103"><xref:System.Windows.Forms.ContextMenuStrip>控件将替换并添加到控件中的功能 <xref:System.Windows.Forms.ContextMenu> ; 但是， <xref:System.Windows.Forms.ContextMenu> 会保留控件以实现向后兼容性和将来使用（如果你选择）。</span><span class="sxs-lookup"><span data-stu-id="dafe5-103">The <xref:System.Windows.Forms.ContextMenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> control; however, the <xref:System.Windows.Forms.ContextMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="dafe5-104">当用户单击鼠标右键时，快捷菜单（也称为上下文菜单）出现在鼠标位置。</span><span class="sxs-lookup"><span data-stu-id="dafe5-104">Shortcut menus, also called context menus, appear at the mouse position when the user clicks the right mouse button.</span></span> <span data-ttu-id="dafe5-105">快捷 *菜单* 为工作区或鼠标指针位置的控件提供选项。</span><span class="sxs-lookup"><span data-stu-id="dafe5-105">Shortcut *menus* provide options for the client area or the control at the mouse pointer location.</span></span>  
  
 <span data-ttu-id="dafe5-106"><xref:System.Windows.Forms.ContextMenuStrip>控件设计为与新的和相关的控件无缝协作 <xref:System.Windows.Forms.ToolStrip> ，但你也可以 <xref:System.Windows.Forms.ContextMenuStrip> 轻松地将与其他控件相关联。</span><span class="sxs-lookup"><span data-stu-id="dafe5-106">The <xref:System.Windows.Forms.ContextMenuStrip> control is designed to work seamlessly with the new <xref:System.Windows.Forms.ToolStrip> and related controls, but you can associate a <xref:System.Windows.Forms.ContextMenuStrip> with other controls just as easily.</span></span>  
  
 <span data-ttu-id="dafe5-107">下表显示了重要的 <xref:System.Windows.Forms.ContextMenuStrip> 伴生类。</span><span class="sxs-lookup"><span data-stu-id="dafe5-107">The following table shows the important <xref:System.Windows.Forms.ContextMenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="dafe5-108">类</span><span class="sxs-lookup"><span data-stu-id="dafe5-108">Class</span></span>|<span data-ttu-id="dafe5-109">描述</span><span class="sxs-lookup"><span data-stu-id="dafe5-109">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="dafe5-110">表示 <xref:System.Windows.Forms.MenuStrip> 或 <xref:System.Windows.Forms.ContextMenuStrip> 上显示的可选选项。</span><span class="sxs-lookup"><span data-stu-id="dafe5-110">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="dafe5-111">表示一个控件，该控件使用户能够从列表中选择单个项（当用户单击 <xref:System.Windows.Forms.ToolStripDropDownButton> 或更高级别菜单项时显示）。</span><span class="sxs-lookup"><span data-stu-id="dafe5-111">Represents a control that enables the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="dafe5-112">为 <xref:System.Windows.Forms.ToolStripItem> 在单击时显示的下拉项的控件提供基本功能。</span><span class="sxs-lookup"><span data-stu-id="dafe5-112">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dafe5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dafe5-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
