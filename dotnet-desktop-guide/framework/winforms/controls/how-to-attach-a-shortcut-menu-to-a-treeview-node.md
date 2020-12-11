---
title: 如何：将快捷菜单附加到 TreeView 节点
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: f818cccb3103866af993f1aff527a9c1a7c82109
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971256"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="1da4f-102">如何：将快捷菜单附加到 TreeView 节点</span><span class="sxs-lookup"><span data-stu-id="1da4f-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="1da4f-103">Windows 窗体 <xref:System.Windows.Forms.TreeView> 控件显示节点的层次结构，类似于在 Windows 资源管理器的左窗格中显示的文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="1da4f-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="1da4f-104">通过设置 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 属性，您可以在用户右键单击控件时为用户提供上下文相关的操作 <xref:System.Windows.Forms.TreeView> 。</span><span class="sxs-lookup"><span data-stu-id="1da4f-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="1da4f-105">通过 <xref:System.Windows.Forms.ContextMenuStrip> 将组件与各个 <xref:System.Windows.Forms.TreeNode> 项关联，你可以向控件添加自定义的快捷菜单功能级别 <xref:System.Windows.Forms.TreeView> 。</span><span class="sxs-lookup"><span data-stu-id="1da4f-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="1da4f-106">以编程方式将快捷菜单与 TreeNode 关联</span><span class="sxs-lookup"><span data-stu-id="1da4f-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1. <span data-ttu-id="1da4f-107"><xref:System.Windows.Forms.TreeView>使用适当的属性设置实例化控件，创建根 <xref:System.Windows.Forms.TreeNode> ，然后添加子节点。</span><span class="sxs-lookup"><span data-stu-id="1da4f-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2. <span data-ttu-id="1da4f-108">实例化 <xref:System.Windows.Forms.ContextMenuStrip> 组件，然后 <xref:System.Windows.Forms.ToolStripMenuItem> 为要在运行时提供的每个操作添加。</span><span class="sxs-lookup"><span data-stu-id="1da4f-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3. <span data-ttu-id="1da4f-109">将相应的的 <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> 属性设置 <xref:System.Windows.Forms.TreeNode> 为你创建的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="1da4f-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4. <span data-ttu-id="1da4f-110">如果设置此属性，则当您右键单击该节点时，将显示快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="1da4f-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="1da4f-111">下面的代码示例创建一个基本 <xref:System.Windows.Forms.TreeView> 的，并 <xref:System.Windows.Forms.ContextMenuStrip> 与 <xref:System.Windows.Forms.TreeNode> 的根关联 <xref:System.Windows.Forms.TreeView> 。</span><span class="sxs-lookup"><span data-stu-id="1da4f-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="1da4f-112">您将需要自定义菜单选项，使其适合 <xref:System.Windows.Forms.TreeView> 您正在开发的用户。</span><span class="sxs-lookup"><span data-stu-id="1da4f-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="1da4f-113">此外，您还需要编写代码来处理 <xref:System.Windows.Forms.ToolStripItem.Click> 这些菜单项的事件。</span><span class="sxs-lookup"><span data-stu-id="1da4f-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1da4f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1da4f-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="1da4f-115">TreeView 控件</span><span class="sxs-lookup"><span data-stu-id="1da4f-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
