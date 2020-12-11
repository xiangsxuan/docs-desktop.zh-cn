---
title: TabControl 控件概述
ms.date: 03/30/2017
f1_keywords:
- TabControl
helpviewer_keywords:
- TabControl control [Windows Forms], about TabControl control
- tab pages [Windows Forms], about tab pages
- property pages [Windows Forms], Windows Forms
- Windows Forms dialog boxes [Windows Forms], tabs
ms.assetid: 2b4ea784-a39d-463c-81d8-af74ce068476
ms.openlocfilehash: 2668169488b4087673fbf2552650c23cda780642
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970895"
---
# <a name="tabcontrol-control-overview-windows-forms"></a><span data-ttu-id="fffef-102">TabControl 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="fffef-102">TabControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="fffef-103">Windows 窗体 <xref:System.Windows.Forms.TabControl> 显示多个选项卡，就像笔记本中的分隔线或档案柜中一组文件夹的标签。</span><span class="sxs-lookup"><span data-stu-id="fffef-103">The Windows Forms <xref:System.Windows.Forms.TabControl> displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="fffef-104">选项卡可以包含图片和其他控件。</span><span class="sxs-lookup"><span data-stu-id="fffef-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="fffef-105">您可以使用选项卡控件来生成在 Windows 操作系统中显示的多个位置的多页对话框，如 "控制面板" 的 "显示属性"。</span><span class="sxs-lookup"><span data-stu-id="fffef-105">You can use the tab control to produce the kind of multiple-page dialog box that appears many places in the Windows operating system, such as the Control Panel Display Properties.</span></span> <span data-ttu-id="fffef-106">此外，还 <xref:System.Windows.Forms.TabControl> 可用于创建用于设置一组相关属性的属性页。</span><span class="sxs-lookup"><span data-stu-id="fffef-106">Additionally, the <xref:System.Windows.Forms.TabControl> can be used to create property pages, which are used to set a group of related properties.</span></span>  
  
## <a name="working-with-tabcontrol"></a><span data-ttu-id="fffef-107">使用 TabControl</span><span class="sxs-lookup"><span data-stu-id="fffef-107">Working with TabControl</span></span>  
 <span data-ttu-id="fffef-108">的最重要的属性 <xref:System.Windows.Forms.TabControl> 是 <xref:System.Windows.Forms.TabControl.TabPages%2A> ，其中包含各个选项卡。</span><span class="sxs-lookup"><span data-stu-id="fffef-108">The most important property of the <xref:System.Windows.Forms.TabControl> is <xref:System.Windows.Forms.TabControl.TabPages%2A>, which contains the individual tabs.</span></span> <span data-ttu-id="fffef-109">每个单独的选项卡都是一个 <xref:System.Windows.Forms.TabPage> 对象。</span><span class="sxs-lookup"><span data-stu-id="fffef-109">Each individual tab is a <xref:System.Windows.Forms.TabPage> object.</span></span> <span data-ttu-id="fffef-110">当单击某个选项卡时，它将引发 <xref:System.Windows.Forms.Control.Click> 该对象的事件 <xref:System.Windows.Forms.TabPage> 。</span><span class="sxs-lookup"><span data-stu-id="fffef-110">When a tab is clicked, it raises the <xref:System.Windows.Forms.Control.Click> event for that <xref:System.Windows.Forms.TabPage> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fffef-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fffef-111">See also</span></span>

- <xref:System.Windows.Forms.TabControl>
- [<span data-ttu-id="fffef-112">TabControl 控件</span><span class="sxs-lookup"><span data-stu-id="fffef-112">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="fffef-113">如何：更改 Windows 窗体 TabControl 的外观</span><span class="sxs-lookup"><span data-stu-id="fffef-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="fffef-114">如何：将控件添加到选项卡页</span><span class="sxs-lookup"><span data-stu-id="fffef-114">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="fffef-115">如何：使用 Windows 窗体 TabControl 添加和移除选项卡</span><span class="sxs-lookup"><span data-stu-id="fffef-115">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="fffef-116">如何：禁用选项卡页</span><span class="sxs-lookup"><span data-stu-id="fffef-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="fffef-117">Windows 窗体中的对话框</span><span class="sxs-lookup"><span data-stu-id="fffef-117">Dialog Boxes in Windows Forms</span></span>](../dialog-boxes-in-windows-forms.md)
