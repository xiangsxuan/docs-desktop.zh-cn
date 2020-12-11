---
title: MainMenu 组件概述
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971089"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="cdfdb-102">MainMenu 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="cdfdb-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="cdfdb-103">尽管 <xref:System.Windows.Forms.MenuStrip> 和 <xref:System.Windows.Forms.ContextMenuStrip> 将功能替换为 <xref:System.Windows.Forms.MainMenu> 以前版本的和控件，并将其 <xref:System.Windows.Forms.ContextMenu> 保留以 <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> 实现后向兼容性和将来使用（如果你选择）。</span><span class="sxs-lookup"><span data-stu-id="cdfdb-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="cdfdb-104">Windows 窗体 <xref:System.Windows.Forms.MainMenu> 组件在运行时显示菜单。</span><span class="sxs-lookup"><span data-stu-id="cdfdb-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="cdfdb-105">主菜单和各个项的所有子菜单都是 <xref:System.Windows.Forms.MenuItem> 对象。</span><span class="sxs-lookup"><span data-stu-id="cdfdb-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="cdfdb-106">键属性</span><span class="sxs-lookup"><span data-stu-id="cdfdb-106">Key Properties</span></span>  
 <span data-ttu-id="cdfdb-107">可以通过将属性设置为来将菜单项指定为默认项 <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> `true` 。</span><span class="sxs-lookup"><span data-stu-id="cdfdb-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="cdfdb-108">单击菜单时，默认项将以粗体文本显示。</span><span class="sxs-lookup"><span data-stu-id="cdfdb-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="cdfdb-109">菜单项的 <xref:System.Windows.Forms.MenuItem.Checked%2A> 属性为 `true` 或 `false` ，指示菜单项是否已选中。</span><span class="sxs-lookup"><span data-stu-id="cdfdb-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="cdfdb-110">菜单项的 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 属性自定义选定项的外观：如果将 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 设置为，则 `true` 该项旁边会出现一个单选按钮; 如果 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 设置为 `false` ，则该项旁边会出现一个复选标记。</span><span class="sxs-lookup"><span data-stu-id="cdfdb-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdfdb-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdfdb-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="cdfdb-112">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="cdfdb-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
