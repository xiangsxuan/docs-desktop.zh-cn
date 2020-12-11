---
title: 使用设计器在 ListView 控件中对项进行分组
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 935d8d75517e1028e686ca229f6ada656f58b01e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972020"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="22d93-102">如何：使用设计器对 Windows 窗体 ListView 控件中的项进行分组</span><span class="sxs-lookup"><span data-stu-id="22d93-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="22d93-103">控件的分组功能 <xref:System.Windows.Forms.ListView> 使你能够以组的形式显示相关项集。</span><span class="sxs-lookup"><span data-stu-id="22d93-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="22d93-104">这些组按包含组标题的水平组标头在屏幕上进行分隔。</span><span class="sxs-lookup"><span data-stu-id="22d93-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="22d93-105">你可以使用 <xref:System.Windows.Forms.ListView> 组，通过按字母顺序、日期或任何其他逻辑分组对项进行分组来更轻松地导航大型列表。</span><span class="sxs-lookup"><span data-stu-id="22d93-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="22d93-106">下图显示了一些分组项：</span><span class="sxs-lookup"><span data-stu-id="22d93-106">The following image shows some grouped items:</span></span>

![数字分为奇数甚至是组。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

<span data-ttu-id="22d93-108">下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="22d93-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="22d93-109">有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="22d93-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

<span data-ttu-id="22d93-110">若要启用分组，必须先 <xref:System.Windows.Forms.ListViewGroup> 在设计器中或以编程方式创建一个或多个对象。</span><span class="sxs-lookup"><span data-stu-id="22d93-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="22d93-111">定义组后，可以为其分配项。</span><span class="sxs-lookup"><span data-stu-id="22d93-111">Once a group has been defined, you can assign items to it.</span></span>

## <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="22d93-112">在设计器中添加或删除组</span><span class="sxs-lookup"><span data-stu-id="22d93-112">To add or remove groups in the designer</span></span>

1. <span data-ttu-id="22d93-113">在 "**属性**" 窗口中，**单击省略号按钮 (省略号** ![ 按钮 ( ") " 属性窗口中的 "Visual) Studio"。 ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ListView.Groups%2A></span><span class="sxs-lookup"><span data-stu-id="22d93-113">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>

     <span data-ttu-id="22d93-114">此时将显示 " **ListViewGroup 集合编辑器** "。</span><span class="sxs-lookup"><span data-stu-id="22d93-114">The **ListViewGroup Collection Editor** appears.</span></span>

2. <span data-ttu-id="22d93-115">若要添加组，请单击 " **添加** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="22d93-115">To add a group, click the **Add** button.</span></span> <span data-ttu-id="22d93-116">然后，可以设置新组的属性，如 <xref:System.Windows.Forms.ListViewGroup.Header%2A> 和 <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="22d93-116">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="22d93-117">若要删除某个组，请选择该组，然后单击 " **删除** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="22d93-117">To remove a group, select it and click the **Remove** button.</span></span>

## <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="22d93-118">在设计器中向组分配项</span><span class="sxs-lookup"><span data-stu-id="22d93-118">To assign items to groups in the designer</span></span>

1. <span data-ttu-id="22d93-119">在 "**属性**" 窗口中，**单击省略号按钮 (省略号** ![ 按钮 ( ") " 属性窗口中的 "Visual) Studio"。 ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ListView.Items%2A></span><span class="sxs-lookup"><span data-stu-id="22d93-119">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="22d93-120">此时将显示 " **ListViewItem 集合编辑器** "。</span><span class="sxs-lookup"><span data-stu-id="22d93-120">The **ListViewItem Collection Editor** appears.</span></span>

2. <span data-ttu-id="22d93-121">若要添加新项，请单击 " **添加** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="22d93-121">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="22d93-122">然后，可以设置新项的属性，如 <xref:System.Windows.Forms.ListViewItem.Text%2A> 和 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="22d93-122">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

3. <span data-ttu-id="22d93-123">选择该 <xref:System.Windows.Forms.ListViewItem.Group%2A> 属性，然后从下拉列表中选择一个组。</span><span class="sxs-lookup"><span data-stu-id="22d93-123">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="22d93-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22d93-124">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="22d93-125">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="22d93-125">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="22d93-126">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="22d93-126">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="22d93-127">如何：使用 Windows 窗体 ListView 控件添加和移除项</span><span class="sxs-lookup"><span data-stu-id="22d93-127">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
