---
title: ListView 控件概述
ms.date: 03/30/2017
f1_keywords:
- ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
ms.openlocfilehash: 9308ff6646704d16b32669827a1f26bebf6958d8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972622"
---
# <a name="listview-control-overview-windows-forms"></a><span data-ttu-id="0cbdc-102">ListView 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="0cbdc-102">ListView Control Overview (Windows Forms)</span></span>
<span data-ttu-id="0cbdc-103">Windows 窗体 <xref:System.Windows.Forms.ListView> 控件显示带图标的项列表。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-103">The Windows Forms <xref:System.Windows.Forms.ListView> control displays a list of items with icons.</span></span> <span data-ttu-id="0cbdc-104">你可以使用列表视图创建类似 Windows 资源管理器右窗格的用户界面。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-104">You can use a list view to create a user interface like the right pane of Windows Explorer.</span></span> <span data-ttu-id="0cbdc-105">控件具有四个视图模式： LargeIcon、SmallIcon、List 和 Details。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-105">The control has four view modes: LargeIcon, SmallIcon, List, and Details.</span></span>  
  
## <a name="what-you-can-do-with-the-listview-control"></a><span data-ttu-id="0cbdc-106">ListView 控件可以执行的操作</span><span class="sxs-lookup"><span data-stu-id="0cbdc-106">What You Can Do with the ListView Control</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0cbdc-107">其他视图模式磁贴仅适用于 Windows XP 和 Windows Server 2003 操作系统。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-107">An additional view mode, Tile, is only available on Windows XP and the Windows Server 2003 operating system.</span></span> <span data-ttu-id="0cbdc-108">有关详细信息，请参阅 [如何：在 Windows 窗体 ListView 控件中启用磁贴视图](how-to-enable-tile-view-in-a-windows-forms-listview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-108">For more information, see [How to: Enable Tile View in a Windows Forms ListView Control](how-to-enable-tile-view-in-a-windows-forms-listview-control.md).</span></span>  
  
 <span data-ttu-id="0cbdc-109">LargeIcon 模式显示项文本旁边的大图标;如果控件足够大，则项显示在多个列中。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-109">The LargeIcon mode displays large icons next to the item text; the items appear in multiple columns if the control is large enough.</span></span> <span data-ttu-id="0cbdc-110">SmallIcon 模式相同，只不过它显示小图标。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-110">The SmallIcon mode is the same except that it displays small icons.</span></span> <span data-ttu-id="0cbdc-111">列表模式显示小图标，但始终显示在单个列中。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-111">The List mode displays small icons but is always in a single column.</span></span> <span data-ttu-id="0cbdc-112">详细信息模式显示多个列中的项。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-112">The Details mode displays items in multiple columns.</span></span> <span data-ttu-id="0cbdc-113">有关详细信息，请参阅 [如何：将列添加到 Windows 窗体 ListView 控件](how-to-add-columns-to-the-windows-forms-listview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-113">For details, see [How to: Add Columns to the Windows Forms ListView Control](how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span> <span data-ttu-id="0cbdc-114">视图模式由 <xref:System.Windows.Forms.ListView.View%2A> 属性确定。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-114">The view mode is determined by the <xref:System.Windows.Forms.ListView.View%2A> property.</span></span> <span data-ttu-id="0cbdc-115">所有视图模式都可以显示图像列表中的图像。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-115">All of the view modes can display images from image lists.</span></span> <span data-ttu-id="0cbdc-116">有关详细信息，请参阅 [如何：显示 Windows 窗体 ListView 控件的图标](how-to-display-icons-for-the-windows-forms-listview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-116">For details, see [How to: Display Icons for the Windows Forms ListView Control](how-to-display-icons-for-the-windows-forms-listview-control.md).</span></span>  
  
 <span data-ttu-id="0cbdc-117">下表列出了一些 <xref:System.Windows.Forms.ListView> 成员以及它们在中有效的视图。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-117">The following table lists some of the <xref:System.Windows.Forms.ListView> members and the views they are valid in.</span></span>  
  
|<span data-ttu-id="0cbdc-118">ListView 成员</span><span class="sxs-lookup"><span data-stu-id="0cbdc-118">ListView member</span></span>|<span data-ttu-id="0cbdc-119">视图</span><span class="sxs-lookup"><span data-stu-id="0cbdc-119">View</span></span>|  
|---------------------|----------|  
|<span data-ttu-id="0cbdc-120"><xref:System.Windows.Forms.ListView.Alignment%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="0cbdc-120"><xref:System.Windows.Forms.ListView.Alignment%2A> property</span></span>|<span data-ttu-id="0cbdc-121"><xref:System.Windows.Forms.View.SmallIcon> 或 <xref:System.Windows.Forms.View.LargeIcon></span><span class="sxs-lookup"><span data-stu-id="0cbdc-121"><xref:System.Windows.Forms.View.SmallIcon> or <xref:System.Windows.Forms.View.LargeIcon></span></span>|  
|<span data-ttu-id="0cbdc-122"><xref:System.Windows.Forms.ListView.AutoArrange%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="0cbdc-122"><xref:System.Windows.Forms.ListView.AutoArrange%2A> property</span></span>|<span data-ttu-id="0cbdc-123"><xref:System.Windows.Forms.View.SmallIcon> 或 <xref:System.Windows.Forms.View.LargeIcon></span><span class="sxs-lookup"><span data-stu-id="0cbdc-123"><xref:System.Windows.Forms.View.SmallIcon> or <xref:System.Windows.Forms.View.LargeIcon></span></span>|  
|<span data-ttu-id="0cbdc-124"><xref:System.Windows.Forms.ListView.AutoResizeColumn%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="0cbdc-124"><xref:System.Windows.Forms.ListView.AutoResizeColumn%2A> method</span></span>|<xref:System.Windows.Forms.View.Details>|  
|<span data-ttu-id="0cbdc-125"><xref:System.Windows.Forms.ListView.Columns%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="0cbdc-125"><xref:System.Windows.Forms.ListView.Columns%2A> property</span></span>|<span data-ttu-id="0cbdc-126"><xref:System.Windows.Forms.View.Details> 或 <xref:System.Windows.Forms.View.Tile></span><span class="sxs-lookup"><span data-stu-id="0cbdc-126"><xref:System.Windows.Forms.View.Details> or <xref:System.Windows.Forms.View.Tile></span></span>|  
|<span data-ttu-id="0cbdc-127"><xref:System.Windows.Forms.ListView.DrawSubItem> 事件</span><span class="sxs-lookup"><span data-stu-id="0cbdc-127"><xref:System.Windows.Forms.ListView.DrawSubItem> event</span></span>|<xref:System.Windows.Forms.View.Details>|  
|<span data-ttu-id="0cbdc-128"><xref:System.Windows.Forms.ListView.FindItemWithText%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="0cbdc-128"><xref:System.Windows.Forms.ListView.FindItemWithText%2A> method</span></span>|<span data-ttu-id="0cbdc-129"><xref:System.Windows.Forms.View.Details>、<xref:System.Windows.Forms.View.List> 或 <xref:System.Windows.Forms.View.Tile></span><span class="sxs-lookup"><span data-stu-id="0cbdc-129"><xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>, or <xref:System.Windows.Forms.View.Tile></span></span>|  
|<span data-ttu-id="0cbdc-130"><xref:System.Windows.Forms.ListView.FindNearestItem%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="0cbdc-130"><xref:System.Windows.Forms.ListView.FindNearestItem%2A> method</span></span>|<span data-ttu-id="0cbdc-131"><xref:System.Windows.Forms.View.SmallIcon> 或 <xref:System.Windows.Forms.View.LargeIcon></span><span class="sxs-lookup"><span data-stu-id="0cbdc-131"><xref:System.Windows.Forms.View.SmallIcon> or <xref:System.Windows.Forms.View.LargeIcon></span></span>|  
|<span data-ttu-id="0cbdc-132"><xref:System.Windows.Forms.ListView.GetItemAt%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="0cbdc-132"><xref:System.Windows.Forms.ListView.GetItemAt%2A> method</span></span>|<span data-ttu-id="0cbdc-133"><xref:System.Windows.Forms.View.Details> 或 <xref:System.Windows.Forms.View.Tile></span><span class="sxs-lookup"><span data-stu-id="0cbdc-133"><xref:System.Windows.Forms.View.Details> or <xref:System.Windows.Forms.View.Tile></span></span>|  
|<span data-ttu-id="0cbdc-134"><xref:System.Windows.Forms.ListView.Groups%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="0cbdc-134"><xref:System.Windows.Forms.ListView.Groups%2A> property</span></span>|<span data-ttu-id="0cbdc-135">除之外的所有视图 <xref:System.Windows.Forms.View.List></span><span class="sxs-lookup"><span data-stu-id="0cbdc-135">All views except <xref:System.Windows.Forms.View.List></span></span>|  
|<span data-ttu-id="0cbdc-136"><xref:System.Windows.Forms.ListView.HeaderStyle%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="0cbdc-136"><xref:System.Windows.Forms.ListView.HeaderStyle%2A> property</span></span>|<span data-ttu-id="0cbdc-137"><xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="0cbdc-137"><xref:System.Windows.Forms.View.Details>.</span></span>|  
|<span data-ttu-id="0cbdc-138"><xref:System.Windows.Forms.ListView.InsertionMark%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="0cbdc-138"><xref:System.Windows.Forms.ListView.InsertionMark%2A> property</span></span>|<span data-ttu-id="0cbdc-139"><xref:System.Windows.Forms.View.LargeIcon>、<xref:System.Windows.Forms.View.SmallIcon> 或 <xref:System.Windows.Forms.View.Tile></span><span class="sxs-lookup"><span data-stu-id="0cbdc-139"><xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>, or <xref:System.Windows.Forms.View.Tile></span></span>|  
  
 <span data-ttu-id="0cbdc-140">控件的键属性 <xref:System.Windows.Forms.ListView> 为 <xref:System.Windows.Forms.ListView.Items%2A> ，它包含控件所显示的项。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-140">The key property of the <xref:System.Windows.Forms.ListView> control is <xref:System.Windows.Forms.ListView.Items%2A>, which contains the items displayed by the control.</span></span> <span data-ttu-id="0cbdc-141"><xref:System.Windows.Forms.ListView.SelectedItems%2A>属性包含控件中当前选定项的集合。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-141">The <xref:System.Windows.Forms.ListView.SelectedItems%2A> property contains a collection of the items currently selected in the control.</span></span> <span data-ttu-id="0cbdc-142">用户可以选择多个项，例如，如果属性设置为，则将多个项一次拖放到另一个控件 <xref:System.Windows.Forms.ListView.MultiSelect%2A> `true` 。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-142">The user can select multiple items, for example to drag and drop several items at a time to another control, if the <xref:System.Windows.Forms.ListView.MultiSelect%2A> property is set to `true`.</span></span> <span data-ttu-id="0cbdc-143"><xref:System.Windows.Forms.ListView>如果将属性设置为，则控件可以显示项旁边的复选框 <xref:System.Windows.Forms.ListView.CheckBoxes%2A> `true` 。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-143">The <xref:System.Windows.Forms.ListView> control can display check boxes next to the items, if the <xref:System.Windows.Forms.ListView.CheckBoxes%2A> property is set to `true`.</span></span>  
  
 <span data-ttu-id="0cbdc-144"><xref:System.Windows.Forms.ListView.Activation%2A>属性确定用户激活列表中的项时必须执行的操作类型：选项为 <xref:System.Windows.Forms.ItemActivation.Standard> 、 <xref:System.Windows.Forms.ItemActivation.OneClick> 和 <xref:System.Windows.Forms.ItemActivation.TwoClick> 。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-144">The <xref:System.Windows.Forms.ListView.Activation%2A> property determines what type of action the user must take to activate an item in the list: the options are <xref:System.Windows.Forms.ItemActivation.Standard>, <xref:System.Windows.Forms.ItemActivation.OneClick>, and <xref:System.Windows.Forms.ItemActivation.TwoClick>.</span></span> <span data-ttu-id="0cbdc-145"><xref:System.Windows.Forms.ItemActivation.OneClick> 激活只需单击一次即可激活该项。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-145"><xref:System.Windows.Forms.ItemActivation.OneClick> activation requires a single click to activate the item.</span></span> <span data-ttu-id="0cbdc-146"><xref:System.Windows.Forms.ItemActivation.TwoClick> 激活要求用户双击激活该项;单击一次即可更改项文本的颜色。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-146"><xref:System.Windows.Forms.ItemActivation.TwoClick> activation requires the user to double-click to activate the item; a single click changes the color of the item text.</span></span> <span data-ttu-id="0cbdc-147"><xref:System.Windows.Forms.ItemActivation.Standard> 激活要求用户双击激活项，但该项不会更改外观。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-147"><xref:System.Windows.Forms.ItemActivation.Standard> activation requires the user to double-click to activate an item, but the item does not change appearance.</span></span>  
  
 <span data-ttu-id="0cbdc-148">该 <xref:System.Windows.Forms.ListView> 控件还支持 WINDOWS XP 平台上可用的视觉样式和其他功能，包括分组、平铺视图和插入标记。</span><span class="sxs-lookup"><span data-stu-id="0cbdc-148">The <xref:System.Windows.Forms.ListView> control also supports the visual styles and other features available on the Windows XP platform, including grouping, tile view, and insertion marks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cbdc-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cbdc-149">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="0cbdc-150">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="0cbdc-150">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="0cbdc-151">如何：使用 Windows 窗体 ListView 控件添加和移除项</span><span class="sxs-lookup"><span data-stu-id="0cbdc-151">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="0cbdc-152">如何：向 Windows 窗体 ListView 控件中添加列</span><span class="sxs-lookup"><span data-stu-id="0cbdc-152">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="0cbdc-153">如何：显示 Windows 窗体 ListView 控件的图标</span><span class="sxs-lookup"><span data-stu-id="0cbdc-153">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="0cbdc-154">如何：使用 Windows 窗体 ListView 控件在列中显示子项</span><span class="sxs-lookup"><span data-stu-id="0cbdc-154">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="0cbdc-155">如何：选择 Windows 窗体 ListView 控件中的项</span><span class="sxs-lookup"><span data-stu-id="0cbdc-155">How to: Select an Item in the Windows Forms ListView Control</span></span>](how-to-select-an-item-in-the-windows-forms-listview-control.md)
- [<span data-ttu-id="0cbdc-156">如何：对 Windows 窗体 ListView 控件中的项进行分组</span><span class="sxs-lookup"><span data-stu-id="0cbdc-156">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)
- [<span data-ttu-id="0cbdc-157">如何：在 Windows 窗体 ListView 控件中显示插入标记</span><span class="sxs-lookup"><span data-stu-id="0cbdc-157">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>](how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)
- [<span data-ttu-id="0cbdc-158">如何：向 ListView 控件添加搜索功能</span><span class="sxs-lookup"><span data-stu-id="0cbdc-158">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)
- [<span data-ttu-id="0cbdc-159">如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="0cbdc-159">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="0cbdc-160">如何：使用 Windows 窗体创建多窗格用户界面</span><span class="sxs-lookup"><span data-stu-id="0cbdc-160">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)