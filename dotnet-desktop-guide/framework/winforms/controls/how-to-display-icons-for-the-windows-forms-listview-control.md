---
title: 显示 ListView 控件的图标
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 5fc54c448dae95cab50cdafa8403769fb421dffa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971196"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="cf811-102">如何：显示 Windows 窗体 ListView 控件的图标</span><span class="sxs-lookup"><span data-stu-id="cf811-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="cf811-103">Windows 窗体 <xref:System.Windows.Forms.ListView> 控件可以显示三个图像列表中的图标。</span><span class="sxs-lookup"><span data-stu-id="cf811-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="cf811-104">"列表"、"详细信息" 和 "SmallIcon" 视图显示在属性中指定的图像列表中的图像 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 。</span><span class="sxs-lookup"><span data-stu-id="cf811-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="cf811-105">LargeIcon 视图显示了在属性中指定的图像列表中的图像 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 。</span><span class="sxs-lookup"><span data-stu-id="cf811-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="cf811-106">列表视图还可以显示一组附加的图标，在属性中的 " <xref:System.Windows.Forms.ListView.StateImageList%2A> 大" 或 "小" 图标旁显示。</span><span class="sxs-lookup"><span data-stu-id="cf811-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="cf811-107">有关图像列表的详细信息，请参阅 [Imagelist 组件](imagelist-component-windows-forms.md) 和 [如何：通过 Windows 窗体 ImageList 组件添加或删除图像](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。</span><span class="sxs-lookup"><span data-stu-id="cf811-107">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="cf811-108">在列表视图中显示图像</span><span class="sxs-lookup"><span data-stu-id="cf811-108">To display images in a list view</span></span>  
  
1. <span data-ttu-id="cf811-109">将相应的属性（ <xref:System.Windows.Forms.ListView.SmallImageList%2A> 、 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 或 <xref:System.Windows.Forms.ListView.StateImageList%2A> ）设置为要使用的现有 <xref:System.Windows.Forms.ImageList> 组件。</span><span class="sxs-lookup"><span data-stu-id="cf811-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="cf811-110">这些属性可以在设计器中设置属性窗口或代码中。</span><span class="sxs-lookup"><span data-stu-id="cf811-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. <span data-ttu-id="cf811-111"><xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> 为每个具有关联图标的列表项设置或属性。</span><span class="sxs-lookup"><span data-stu-id="cf811-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="cf811-112">可以在代码中或在 **ListViewItem 集合编辑器** 中设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="cf811-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="cf811-113">若要打开 " **ListViewItem 集合编辑器**"，请单击省略号按钮 (![ Visual Studio 属性窗口中的省略号按钮 ( ") "。在 ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ListView.Items%2A> " **属性** " 窗口中的属性旁) 。</span><span class="sxs-lookup"><span data-stu-id="cf811-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="cf811-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf811-114">See also</span></span>

- [<span data-ttu-id="cf811-115">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="cf811-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="cf811-116">如何：使用 Windows 窗体 ListView 控件添加和移除项</span><span class="sxs-lookup"><span data-stu-id="cf811-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="cf811-117">如何：向 Windows 窗体 ListView 控件中添加列</span><span class="sxs-lookup"><span data-stu-id="cf811-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="cf811-118">如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="cf811-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="cf811-119">ImageList 组件</span><span class="sxs-lookup"><span data-stu-id="cf811-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
