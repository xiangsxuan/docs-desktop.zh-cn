---
title: 如何：复制 ToolStripMenuItem
ms.date: 03/30/2017
helpviewer_keywords:
- menu items [Windows Forms], copying and pasting
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], copying and pasting
ms.assetid: 17ef4207-e92e-4db2-b648-27246e6517ad
ms.openlocfilehash: c59af175a6ee23395e19247efd8fa15e6d19ae66
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971236"
---
# <a name="how-to-copy-toolstripmenuitems"></a><span data-ttu-id="19110-102">如何：复制 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="19110-102">How to: Copy ToolStripMenuItems</span></span>
<span data-ttu-id="19110-103">在设计时，你可以将整个顶级菜单及其子菜单项复制到 <xref:System.Windows.Forms.MenuStrip>上的其他位置。</span><span class="sxs-lookup"><span data-stu-id="19110-103">At design time, you can copy entire top-level menus and their submenu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="19110-104">还可以复制顶级菜单之间的单个菜单项或在菜单中更改菜单项的位置。</span><span class="sxs-lookup"><span data-stu-id="19110-104">You can also copy individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-another-top-level-location"></a><span data-ttu-id="19110-105">若要将顶级菜单及其子菜单项复制到另一个顶级位置</span><span class="sxs-lookup"><span data-stu-id="19110-105">To copy a top-level menu and its submenu items to another top-level location</span></span>  
  
1. <span data-ttu-id="19110-106">左键单击想要复制的菜单并按 CTRL+C，或右键单击该菜单，并从快捷菜单选择“复制”  。</span><span class="sxs-lookup"><span data-stu-id="19110-106">Left-click the menu that you want to copy and press CTRL+C, or right-click the menu and select **Copy** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="19110-107">左键单击预期新位置之后的顶级菜单并按 CTRL+V，或右键单击预期新位置之前的顶级菜单项，并从快捷菜单选择“粘贴”  。</span><span class="sxs-lookup"><span data-stu-id="19110-107">Left-click the top-level menu that is after the intended new location and press CTRL+V, or right-click the top-level menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="19110-108">复制的菜单将插入到所选顶级菜单之前。</span><span class="sxs-lookup"><span data-stu-id="19110-108">The menu that you copied is inserted before the selected top-level menu.</span></span>  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-a-drop-down-location"></a><span data-ttu-id="19110-109">若要将顶级菜单及其子菜单项复制到一个下拉位置</span><span class="sxs-lookup"><span data-stu-id="19110-109">To copy a top-level menu and its submenu items to a drop-down location</span></span>  
  
1. <span data-ttu-id="19110-110">左键单击想要移动的菜单并按 CTRL+C，或右键单击该菜单，并从快捷菜单选择“复制”  。</span><span class="sxs-lookup"><span data-stu-id="19110-110">Left-click the menu that you want to move and press CTRL+C, or right-click the menu and select **Copy** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="19110-111">在目标顶级菜单中，左键单击预期新位置上方的子菜单项并按 CTRL+V，或右键单击目标新位置上方的子菜单项，并从快捷菜单选择“粘贴”  。</span><span class="sxs-lookup"><span data-stu-id="19110-111">In the destination top-level menu, left-click the submenu item that is above the intended new location and press CTRL+V, or right-click the submenu item that is above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="19110-112">复制的菜单将插入到所选子菜单项之前。</span><span class="sxs-lookup"><span data-stu-id="19110-112">The menu that you copied is inserted before the selected submenu item.</span></span>  
  
### <a name="to-copy-a-submenu-item-to-another-menu"></a><span data-ttu-id="19110-113">若要将子菜单项复制到另一菜单</span><span class="sxs-lookup"><span data-stu-id="19110-113">To copy a submenu item to another menu</span></span>  
  
1. <span data-ttu-id="19110-114">左键单击想要复制的子菜单项并按 CTRL+C，或右键单击该子菜单项，并从快捷菜单选择“复制”  。</span><span class="sxs-lookup"><span data-stu-id="19110-114">Left-click the submenu item that you want to copy and press CTRL+C, or right-click the submenu item and choose **Copy** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="19110-115">左键单击将包含你所剪切的子菜单项的菜单。</span><span class="sxs-lookup"><span data-stu-id="19110-115">Left-click the menu that will contain the submenu item that you cut.</span></span>  
  
3. <span data-ttu-id="19110-116">左键单击预期新位置之前的子菜单项并按 CTRL+V，或右键单击预期新位置之前的子菜单项，并从快捷菜单选择“粘贴”  。</span><span class="sxs-lookup"><span data-stu-id="19110-116">Left-click the submenu item that is before the intended new location and press CTRL+V, or right-click the submenu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="19110-117">复制的子菜单项将插入到所选子菜单项之前。</span><span class="sxs-lookup"><span data-stu-id="19110-117">The submenu item that you copied is inserted before the selected submenu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19110-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19110-118">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="19110-119">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="19110-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
