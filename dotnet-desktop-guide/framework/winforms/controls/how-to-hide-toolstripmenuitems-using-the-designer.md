---
title: 如何：使用设计器隐藏 ToolStripMenuItem
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 0e1cd7d1868adabd4d3eec9510f6ee567ba3867d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971169"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="49de9-102">如何：使用设计器隐藏 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="49de9-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="49de9-103">通过隐藏菜单项，可以控制应用程序 (UI) 的用户界面并限制用户命令。</span><span class="sxs-lookup"><span data-stu-id="49de9-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="49de9-104">通常，当菜单上的所有菜单项均不可用时，您需要隐藏整个菜单。</span><span class="sxs-lookup"><span data-stu-id="49de9-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="49de9-105">这为用户提供的干扰更少。</span><span class="sxs-lookup"><span data-stu-id="49de9-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="49de9-106">此外，您可能还希望隐藏和禁用菜单项或菜单项，因为仅隐藏不会阻止用户使用快捷键访问菜单命令。</span><span class="sxs-lookup"><span data-stu-id="49de9-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="49de9-107">有关禁用菜单项的详细信息，请参阅 [如何：使用设计器禁用 toolstripmenuitem](how-to-disable-toolstripmenuitems-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="49de9-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>

## <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="49de9-108">隐藏顶级菜单及其子菜单项</span><span class="sxs-lookup"><span data-stu-id="49de9-108">To hide a top-level menu and its submenu items</span></span>

1. <span data-ttu-id="49de9-109">选择顶级菜单项，并将其 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 或属性设置 <xref:System.Windows.Forms.ToolStripItem.Available%2A> 为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="49de9-109">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>

     <span data-ttu-id="49de9-110">隐藏顶级菜单项时，该菜单内的所有菜单项也将隐藏。</span><span class="sxs-lookup"><span data-stu-id="49de9-110">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="49de9-111">如果在 "设置为" 后单击 "除" 之外的任何位置 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ToolStripItem.Visible%2A> `false` ，则整个顶级菜单项及其子菜单项将从窗体中消失，从而显示操作的运行时效果。</span><span class="sxs-lookup"><span data-stu-id="49de9-111">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="49de9-112">若要在设计时显示隐藏的顶级菜单项，请在 <xref:System.Windows.Forms.MenuStrip> **组件栏**、" **文档大纲**" 中或在属性网格顶部单击。</span><span class="sxs-lookup"><span data-stu-id="49de9-112">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>

> [!NOTE]
> <span data-ttu-id="49de9-113">在合并方案中，你几乎不会隐藏除多个文档界面 (MDI) 子菜单之外的整个菜单。</span><span class="sxs-lookup"><span data-stu-id="49de9-113">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>

## <a name="to-hide-a-submenu-item"></a><span data-ttu-id="49de9-114">隐藏子菜单项</span><span class="sxs-lookup"><span data-stu-id="49de9-114">To hide a submenu item</span></span>

1. <span data-ttu-id="49de9-115">选择子菜单项，并将其 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 属性设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="49de9-115">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>

     <span data-ttu-id="49de9-116">隐藏子菜单项时，它会在设计时在窗体上保持可见，以便您可以轻松地选择它来进行进一步的工作。</span><span class="sxs-lookup"><span data-stu-id="49de9-116">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="49de9-117">它实际上会在运行时隐藏。</span><span class="sxs-lookup"><span data-stu-id="49de9-117">It will actually be hidden at run time.</span></span>

## <a name="see-also"></a><span data-ttu-id="49de9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49de9-118">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [<span data-ttu-id="49de9-119">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="49de9-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="49de9-120">如何：使用设计器禁用 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="49de9-120">How to: Disable ToolStripMenuItems Using the Designer</span></span>](how-to-disable-toolstripmenuitems-using-the-designer.md)
