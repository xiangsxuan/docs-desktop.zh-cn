---
title: 冻结 DataGridView 控件中的列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], freezing columns
- DataGridView control [Windows Forms], columns always in view
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
ms.openlocfilehash: 6d1a98e5c4332078c6012cb7c9ed836108abd86c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971171"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d5b9a-102">如何：冻结 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="d5b9a-102">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d5b9a-103">用户查看 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中显示的数据时，有时需要频繁地引用单个列或列集。</span><span class="sxs-lookup"><span data-stu-id="d5b9a-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="d5b9a-104">例如，显示包含许多列的客户信息表时，使其他列可在可使区域外滚动的同时始终显示客户姓名非常有用。</span><span class="sxs-lookup"><span data-stu-id="d5b9a-104">For example, when displaying a table of customer information that contains many columns, it is useful to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>  
  
 <span data-ttu-id="d5b9a-105">若要实现此行为，可冻结控件中的列。</span><span class="sxs-lookup"><span data-stu-id="d5b9a-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="d5b9a-106">冻结列时，也将冻结其左侧（在从右到左的语言脚本中为右侧）的所有列。</span><span class="sxs-lookup"><span data-stu-id="d5b9a-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="d5b9a-107">冻结的列保持不变，而所有其他列可以滚动。</span><span class="sxs-lookup"><span data-stu-id="d5b9a-107">Frozen columns remain in place while all other columns can scroll.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d5b9a-108">如果启用了列重新排序，冻结的列被视为一组不同于未冻结的列。</span><span class="sxs-lookup"><span data-stu-id="d5b9a-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="d5b9a-109">用户可重新定位任一组中的列，但不能将列从一个组移到另一组。</span><span class="sxs-lookup"><span data-stu-id="d5b9a-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>  
  
 <span data-ttu-id="d5b9a-110">列的 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> 属性决定列在网格内是否始终可见。</span><span class="sxs-lookup"><span data-stu-id="d5b9a-110">The <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property of a column determines whether the column is always visible within the grid.</span></span>  
  
 <span data-ttu-id="d5b9a-111">Visual Studio 中对此任务提供支持。</span><span class="sxs-lookup"><span data-stu-id="d5b9a-111">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="d5b9a-112">另请参阅 [如何：使用设计器冻结 Windows 窗体 DataGridView 控件中的列](freeze-columns-in-the-datagrid-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="d5b9a-112">Also see [How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer](freeze-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-freeze-a-column-programmatically"></a><span data-ttu-id="d5b9a-113">以编程方式冻结列</span><span class="sxs-lookup"><span data-stu-id="d5b9a-113">To freeze a column programmatically</span></span>  
  
- <span data-ttu-id="d5b9a-114">将 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="d5b9a-114">Set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d5b9a-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="d5b9a-115">Compiling the Code</span></span>  
 <span data-ttu-id="d5b9a-116">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="d5b9a-116">This example requires:</span></span>  
  
- <span data-ttu-id="d5b9a-117">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件，其包含一个名为 `AddToCartButton` 的列。</span><span class="sxs-lookup"><span data-stu-id="d5b9a-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `AddToCartButton`.</span></span>  
  
- <span data-ttu-id="d5b9a-118">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d5b9a-118">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b9a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5b9a-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="d5b9a-120">Windows 窗体 DataGridView 控件中的基本列、行和单元格功能</span><span class="sxs-lookup"><span data-stu-id="d5b9a-120">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="d5b9a-121">如何：启用 Windows 窗体 DataGridView 控件中列的重新排序</span><span class="sxs-lookup"><span data-stu-id="d5b9a-121">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)
