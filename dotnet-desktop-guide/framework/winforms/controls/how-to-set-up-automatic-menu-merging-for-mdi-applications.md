---
title: 如何：为 MDI 应用程序设置自动菜单合并
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 33e07bb655d81c6a802ebdce871a2fed845a5c96
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972548"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a><span data-ttu-id="cb3ab-102">如何：为 MDI 应用程序设置自动菜单合并</span><span class="sxs-lookup"><span data-stu-id="cb3ab-102">How to: Set Up Automatic Menu Merging for MDI Applications</span></span>
<span data-ttu-id="cb3ab-103">以下过程提供了在多文档界面中设置自动合并的基本步骤， (MDI) 应用程序 <xref:System.Windows.Forms.MenuStrip> 。</span><span class="sxs-lookup"><span data-stu-id="cb3ab-103">The following procedure gives the basic steps for setting up automatic merging in a multiple-document interface (MDI) application with <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
### <a name="to-set-up-automatic-menu-merging"></a><span data-ttu-id="cb3ab-104">设置自动菜单合并</span><span class="sxs-lookup"><span data-stu-id="cb3ab-104">To set up automatic menu merging</span></span>  
  
1. <span data-ttu-id="cb3ab-105">通过将 MDI 父窗体的属性设置为来创建该窗体 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> `true` 。</span><span class="sxs-lookup"><span data-stu-id="cb3ab-105">Create the MDI parent form by setting its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="cb3ab-106">向 <xref:System.Windows.Forms.MenuStrip> MDI 父级添加，并将其 <xref:System.Windows.Forms.Form.MainMenuStrip%2A> 属性设置为 <xref:System.Windows.Forms.MenuStrip> 。</span><span class="sxs-lookup"><span data-stu-id="cb3ab-106">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI parent, setting its <xref:System.Windows.Forms.Form.MainMenuStrip%2A> property to that <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
3. <span data-ttu-id="cb3ab-107">创建一个 MDI 子窗体，并将其 <xref:System.Windows.Forms.Form.MdiParent%2A> 属性设置为父窗体的名称。</span><span class="sxs-lookup"><span data-stu-id="cb3ab-107">Create an MDI child form, and set its <xref:System.Windows.Forms.Form.MdiParent%2A> property to the name of the parent form.</span></span>  
  
4. <span data-ttu-id="cb3ab-108">将添加 <xref:System.Windows.Forms.MenuStrip> 到 MDI 子窗体。</span><span class="sxs-lookup"><span data-stu-id="cb3ab-108">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI child form.</span></span>  
  
5. <span data-ttu-id="cb3ab-109">在子窗体上，将 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 的属性设置 <xref:System.Windows.Forms.MenuStrip> 为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="cb3ab-109">On the child form, set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
6. <span data-ttu-id="cb3ab-110"><xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MenuStrip> 当激活子窗体时，将菜单项添加到要合并到父窗体的子窗体中。</span><span class="sxs-lookup"><span data-stu-id="cb3ab-110">Add menu items to the child form's <xref:System.Windows.Forms.MenuStrip> that you want to merge into the parent form's <xref:System.Windows.Forms.MenuStrip> when the child form is activated.</span></span>  
  
7. <span data-ttu-id="cb3ab-111">使用 <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> 子窗体中菜单项的属性 <xref:System.Windows.Forms.MenuStrip> 来控制它们合并到父窗体中的方式。</span><span class="sxs-lookup"><span data-stu-id="cb3ab-111">Use the <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> property on the menu items in the child form's <xref:System.Windows.Forms.MenuStrip> to control how they merge into the parent form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb3ab-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb3ab-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="cb3ab-113">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="cb3ab-113">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
