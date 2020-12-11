---
title: 用 ListView 控件在列中显示子项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: 5c6d807410ad4ee0198d6334844bd65b148edff4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972041"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="1e2de-102">如何：使用 Windows 窗体 ListView 控件在列中显示子项</span><span class="sxs-lookup"><span data-stu-id="1e2de-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="1e2de-103">Windows 窗体 <xref:System.Windows.Forms.ListView> 控件可以为详细信息视图中的每个项显示其他文本或子项。</span><span class="sxs-lookup"><span data-stu-id="1e2de-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="1e2de-104">第一列显示项文本，例如雇员编号。</span><span class="sxs-lookup"><span data-stu-id="1e2de-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="1e2de-105">第二个、第三个和后续列显示第一个、第二个和后续关联的子项。</span><span class="sxs-lookup"><span data-stu-id="1e2de-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="1e2de-106">将子项添加到列表项</span><span class="sxs-lookup"><span data-stu-id="1e2de-106">To add subitems to a list item</span></span>  
  
1. <span data-ttu-id="1e2de-107">添加所需的任何列。</span><span class="sxs-lookup"><span data-stu-id="1e2de-107">Add any columns needed.</span></span> <span data-ttu-id="1e2de-108">因为第一列将显示项目的 <xref:System.Windows.Forms.ListView.Text%2A> 属性，所以需要比子项更多的列。</span><span class="sxs-lookup"><span data-stu-id="1e2de-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="1e2de-109">有关添加列的详细信息，请参阅 [如何：将列添加到 Windows 窗体 ListView 控件](how-to-add-columns-to-the-windows-forms-listview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1e2de-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2. <span data-ttu-id="1e2de-110">调用 <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> 由项的属性返回的集合的 <xref:System.Windows.Forms.ListViewItem.SubItems%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1e2de-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="1e2de-111">下面的代码示例设置了一个列表项的雇员姓名和部门。</span><span class="sxs-lookup"><span data-stu-id="1e2de-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="1e2de-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e2de-112">See also</span></span>

- [<span data-ttu-id="1e2de-113">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="1e2de-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="1e2de-114">如何：使用 Windows 窗体 ListView 控件添加和移除项</span><span class="sxs-lookup"><span data-stu-id="1e2de-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="1e2de-115">如何：向 Windows 窗体 ListView 控件中添加列</span><span class="sxs-lookup"><span data-stu-id="1e2de-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="1e2de-116">如何：显示 Windows 窗体 ListView 控件的图标</span><span class="sxs-lookup"><span data-stu-id="1e2de-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="1e2de-117">如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="1e2de-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
