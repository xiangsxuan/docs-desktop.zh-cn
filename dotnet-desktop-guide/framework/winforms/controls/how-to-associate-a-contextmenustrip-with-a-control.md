---
title: 如何：将 ContextMenuStrip 与控件相关联
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: e1b2a49196d6da66d478a3d44eab64298cebe969
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971259"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="c236e-102">如何：将 ContextMenuStrip 与控件相关联</span><span class="sxs-lookup"><span data-stu-id="c236e-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="c236e-103">创建控件和快捷菜单后，使用以下过程在用户右键单击控件时显示给定的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="c236e-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="c236e-104">这些过程将 <xref:System.Windows.Forms.ContextMenuStrip> 与 Windows 窗体和 <xref:System.Windows.Forms.ToolStrip> 控件相关联。</span><span class="sxs-lookup"><span data-stu-id="c236e-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="c236e-105">将 ContextMenuStrip 与 Windows 窗体关联</span><span class="sxs-lookup"><span data-stu-id="c236e-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1. <span data-ttu-id="c236e-106">将 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 属性设置为关联的 <xref:System.Windows.Forms.ContextMenuStrip> 的名称。</span><span class="sxs-lookup"><span data-stu-id="c236e-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="c236e-107">将 ContextMenuStrip 与 ToolStrip 控件关联</span><span class="sxs-lookup"><span data-stu-id="c236e-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1. <span data-ttu-id="c236e-108">将控件的 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 属性设置为关联的 <xref:System.Windows.Forms.ContextMenuStrip> 的名称。</span><span class="sxs-lookup"><span data-stu-id="c236e-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c236e-109">示例</span><span class="sxs-lookup"><span data-stu-id="c236e-109">Example</span></span>  
 <span data-ttu-id="c236e-110">下面的代码示例创建了 Windows 窗体和 <xref:System.Windows.Forms.ToolStrip>，并将不同的 <xref:System.Windows.Forms.ContextMenuStrip> 与其中每个控件关联。</span><span class="sxs-lookup"><span data-stu-id="c236e-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c236e-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="c236e-111">Compiling the Code</span></span>  
 <span data-ttu-id="c236e-112">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="c236e-112">This example requires:</span></span>  
  
- <span data-ttu-id="c236e-113">对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="c236e-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c236e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c236e-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="c236e-115">如何：向 ContextMenuStrip 添加菜单项</span><span class="sxs-lookup"><span data-stu-id="c236e-115">How to: Add Menu Items to a ContextMenuStrip</span></span>](how-to-add-menu-items-to-a-contextmenustrip.md)
- [<span data-ttu-id="c236e-116">ContextMenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="c236e-116">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
