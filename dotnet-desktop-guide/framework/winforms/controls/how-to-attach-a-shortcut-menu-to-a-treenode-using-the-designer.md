---
title: 如何：使用设计器将快捷菜单附加到 TreeNode
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: eb3240d35309e03aa8ce949b9c5000f8581d2c2f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971257"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a><span data-ttu-id="c4b0b-102">如何：使用设计器将快捷菜单附加到 TreeNode</span><span class="sxs-lookup"><span data-stu-id="c4b0b-102">How to: Attach a Shortcut Menu to a TreeNode Using the Designer</span></span>
<span data-ttu-id="c4b0b-103">Windows 窗体 <xref:System.Windows.Forms.TreeView> 控件显示节点的层次结构，这类似于 windows 操作系统中的 Windows 资源管理器功能的左窗格中显示的文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="c4b0b-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of the Windows Explorer feature in Windows operating systems.</span></span> <span data-ttu-id="c4b0b-104">通过设置 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 属性，您可以在用户右键单击控件时为用户提供上下文相关的操作 <xref:System.Windows.Forms.TreeView> 。</span><span class="sxs-lookup"><span data-stu-id="c4b0b-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="c4b0b-105">通过 <xref:System.Windows.Forms.ContextMenuStrip> 将组件与各个 <xref:System.Windows.Forms.TreeNode> 项关联，你可以向控件添加自定义的快捷菜单功能级别 <xref:System.Windows.Forms.TreeView> 。</span><span class="sxs-lookup"><span data-stu-id="c4b0b-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>

## <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a><span data-ttu-id="c4b0b-106">在设计时将快捷菜单与 TreeNode 关联</span><span class="sxs-lookup"><span data-stu-id="c4b0b-106">To associate a shortcut menu with a TreeNode at design time</span></span>

1. <span data-ttu-id="c4b0b-107">向 <xref:System.Windows.Forms.TreeView> 窗体添加一个控件，并根据需要将节点添加到 <xref:System.Windows.Forms.TreeView> 。</span><span class="sxs-lookup"><span data-stu-id="c4b0b-107">Add a <xref:System.Windows.Forms.TreeView> control to your form, and then add nodes to the <xref:System.Windows.Forms.TreeView> as needed.</span></span> <span data-ttu-id="c4b0b-108">有关详细信息，请参阅 [如何：在 Windows 窗体 TreeView 控件中添加和删除节点](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b0b-108">For more information, see [How to: Add and Remove Nodes with the Windows Forms TreeView Control](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span></span>

2. <span data-ttu-id="c4b0b-109">将 <xref:System.Windows.Forms.ContextMenuStrip> 组件添加到窗体，然后将菜单项添加到表示要在运行时提供的节点级操作的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="c4b0b-109">Add a <xref:System.Windows.Forms.ContextMenuStrip> component to your form, and then add menu items to the shortcut menu that represent node-level operations you wish to make available at run time.</span></span> <span data-ttu-id="c4b0b-110">有关详细信息，请参阅 [如何：向 ContextMenuStrip 添加菜单项](how-to-add-menu-items-to-a-contextmenustrip.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b0b-110">For more information, see [How to: Add Menu Items to a ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).</span></span>

3. <span data-ttu-id="c4b0b-111">重新打开该控件的 " **TreeNodeEditor** " 对话框 <xref:System.Windows.Forms.TreeView> ，选择要编辑的节点，并将其 <xref:System.Windows.Forms.ContextMenuStrip> 属性设置为添加的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="c4b0b-111">Reopen the **TreeNodeEditor** dialog box for the <xref:System.Windows.Forms.TreeView> control, select the node to edit, and set its <xref:System.Windows.Forms.ContextMenuStrip> property to the shortcut menu that you added.</span></span>

4. <span data-ttu-id="c4b0b-112">如果设置此属性，则当您右键单击该节点时，将显示快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="c4b0b-112">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>

     <span data-ttu-id="c4b0b-113">此外，您还需要编写代码来处理 <xref:System.Windows.Forms.ToolStripItem.Click> 这些菜单项的事件。</span><span class="sxs-lookup"><span data-stu-id="c4b0b-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4b0b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4b0b-114">See also</span></span>

- [<span data-ttu-id="c4b0b-115">TreeView 控件</span><span class="sxs-lookup"><span data-stu-id="c4b0b-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="c4b0b-116">TreeView 控件概述</span><span class="sxs-lookup"><span data-stu-id="c4b0b-116">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="c4b0b-117">ContextMenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="c4b0b-117">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
