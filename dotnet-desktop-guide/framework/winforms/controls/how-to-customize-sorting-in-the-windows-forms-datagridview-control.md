---
title: 自定义 DataGridView 控件中的排序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], sorting
- data grids [Windows Forms], customizing sorting
ms.assetid: 92fb5c14-afab-4cf5-a97e-924fd9cb99f5
ms.openlocfilehash: 20f581b2df6fd172a0a1998aed60c56b0306f2eb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971856"
---
# <a name="how-to-customize-sorting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="5ed7a-102">如何：自定义 Windows 窗体 DataGridView 控件中的排序方式</span><span class="sxs-lookup"><span data-stu-id="5ed7a-102">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5ed7a-103"><xref:System.Windows.Forms.DataGridView> 控件提供自动排序，但根据需要，你可能需要自定义排序操作。</span><span class="sxs-lookup"><span data-stu-id="5ed7a-103">The <xref:System.Windows.Forms.DataGridView> control provides automatic sorting but, depending on your needs, you might need to customize sort operations.</span></span> <span data-ttu-id="5ed7a-104">例如，你可以使用编程排序来创建替代的用户界面 (UI)。</span><span class="sxs-lookup"><span data-stu-id="5ed7a-104">For example, you can use programmatic sorting to create an alternate user interface (UI).</span></span> <span data-ttu-id="5ed7a-105">或者，你可以处理 <xref:System.Windows.Forms.DataGridView.SortCompare> 事件或调用 <xref:System.Windows.Forms.DataGridView.Sort%2A> 方法的 `Sort(IComparer)` 重载，以便进行更灵活的排序，例如对多个列进行排序。</span><span class="sxs-lookup"><span data-stu-id="5ed7a-105">Alternatively, you can handle the <xref:System.Windows.Forms.DataGridView.SortCompare> event or call the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method for greater sorting flexibility, such as sorting multiple columns.</span></span>  
  
 <span data-ttu-id="5ed7a-106">下面的代码示例演示三种自定义排序方法。</span><span class="sxs-lookup"><span data-stu-id="5ed7a-106">The following code examples demonstrate these three approaches to custom sorting.</span></span> <span data-ttu-id="5ed7a-107">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件中的列排序模式](column-sort-modes-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="5ed7a-107">For more information, see [Column Sort Modes in the Windows Forms DataGridView Control](column-sort-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="programmatic-sorting"></a><span data-ttu-id="5ed7a-108">编程排序</span><span class="sxs-lookup"><span data-stu-id="5ed7a-108">Programmatic Sorting</span></span>  
 <span data-ttu-id="5ed7a-109">下面的代码示例演示使用 <xref:System.Windows.Forms.DataGridView.SortOrder%2A> 和 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> 属性来确定排序方向，使用 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> 属性来手动设置排序标志符号的编程排序。</span><span class="sxs-lookup"><span data-stu-id="5ed7a-109">The following code example demonstrates a programmatic sort using the <xref:System.Windows.Forms.DataGridView.SortOrder%2A> and <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> properties to determine the direction of the sort, and the <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> property to manually set the sort glyph.</span></span> <span data-ttu-id="5ed7a-110"><xref:System.Windows.Forms.DataGridView.Sort%2A> 方法的 `Sort(DataGridViewColumn,ListSortDirection)` 重载仅用于对单个列中的数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="5ed7a-110">The `Sort(DataGridViewColumn,ListSortDirection)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method is used to sort data only in a single column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-sortcompare-event"></a><span data-ttu-id="5ed7a-111">使用 SortCompare 事件自定义排序</span><span class="sxs-lookup"><span data-stu-id="5ed7a-111">Custom Sorting Using the SortCompare Event</span></span>  
 <span data-ttu-id="5ed7a-112">下面的代码示例演示使用 <xref:System.Windows.Forms.DataGridView.SortCompare> 事件处理程序进行自定义排序。</span><span class="sxs-lookup"><span data-stu-id="5ed7a-112">The following code example demonstrates custom sorting using a <xref:System.Windows.Forms.DataGridView.SortCompare> event handler.</span></span> <span data-ttu-id="5ed7a-113">对所选 <xref:System.Windows.Forms.DataGridViewColumn> 进行了排序，如果列中有重复的值，则使用 ID 列确定最终顺序。</span><span class="sxs-lookup"><span data-stu-id="5ed7a-113">The selected <xref:System.Windows.Forms.DataGridViewColumn> is sorted and, if there are duplicate values in the column, the ID column is used to determine the final order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-icomparer-interface"></a><span data-ttu-id="5ed7a-114">使用 IComparer 接口自定义排序</span><span class="sxs-lookup"><span data-stu-id="5ed7a-114">Custom Sorting Using the IComparer Interface</span></span>  
 <span data-ttu-id="5ed7a-115">下面的代码示例演示使用 <xref:System.Windows.Forms.DataGridView.Sort%2A> 方法的 `Sort(IComparer)` 重载进行自定义排序，它通过实现 <xref:System.Collections.IComparer> 接口来执行多个列的排序。</span><span class="sxs-lookup"><span data-stu-id="5ed7a-115">The following code example demonstrates custom sorting using the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method, which takes an implementation of the <xref:System.Collections.IComparer> interface to perform a multiple-column sort.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5ed7a-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="5ed7a-116">Compiling the Code</span></span>  
 <span data-ttu-id="5ed7a-117">这些示例需要：</span><span class="sxs-lookup"><span data-stu-id="5ed7a-117">These examples require:</span></span>  
  
- <span data-ttu-id="5ed7a-118">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="5ed7a-118">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ed7a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ed7a-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="5ed7a-120">在 Windows 窗体 DataGridView 控件中对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="5ed7a-120">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5ed7a-121">Windows 窗体 DataGridView 控件中的列排序模式</span><span class="sxs-lookup"><span data-stu-id="5ed7a-121">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5ed7a-122">如何：设置 Windows 窗体 DataGridView 控件中列的排序模式</span><span class="sxs-lookup"><span data-stu-id="5ed7a-122">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)
