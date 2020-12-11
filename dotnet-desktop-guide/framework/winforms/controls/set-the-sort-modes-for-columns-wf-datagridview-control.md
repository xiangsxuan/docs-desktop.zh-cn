---
title: 设置 DataGridView 控件中列的排序模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 45ee1e7d82f826cddbd3492fed0f63e7a9c2cf1d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970284"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="01cee-102">如何：设置 Windows 窗体 DataGridView 控件中列的排序模式</span><span class="sxs-lookup"><span data-stu-id="01cee-102">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="01cee-103">在 <xref:System.Windows.Forms.DataGridView> 控件中，默认情况下，文本框列使用自动排序，而其他列类型不会自动排序。</span><span class="sxs-lookup"><span data-stu-id="01cee-103">In the <xref:System.Windows.Forms.DataGridView> control, text box columns use automatic sorting by default, while other column types are not sorted automatically.</span></span> <span data-ttu-id="01cee-104">有时，您需要重写这些默认值。</span><span class="sxs-lookup"><span data-stu-id="01cee-104">Sometimes you will want to override these defaults.</span></span> <span data-ttu-id="01cee-105">例如，可以显示图像来代替文本、数字或枚举单元值。</span><span class="sxs-lookup"><span data-stu-id="01cee-105">For example, you can display images in place of text, numbers, or enumeration cell values.</span></span> <span data-ttu-id="01cee-106">当无法对图像进行排序时，可以对它们所表示的基础值进行排序。</span><span class="sxs-lookup"><span data-stu-id="01cee-106">While the images cannot be sorted, the underlying values that they represent can be sorted.</span></span>  
  
 <span data-ttu-id="01cee-107">在 <xref:System.Windows.Forms.DataGridView> 控件中， <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 列的属性值决定了其排序行为。</span><span class="sxs-lookup"><span data-stu-id="01cee-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property value of a column determines its sorting behavior.</span></span>  
  
 <span data-ttu-id="01cee-108">下面的过程显示了 `Priority` [如何：自定义 Windows 窗体 DataGridView 控件中的数据格式](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)的列。</span><span class="sxs-lookup"><span data-stu-id="01cee-108">The following procedure shows the `Priority` column from [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="01cee-109">此列是图像列，默认情况下不可排序。</span><span class="sxs-lookup"><span data-stu-id="01cee-109">This column is an image column and is not sortable by default.</span></span> <span data-ttu-id="01cee-110">它包含作为字符串的实际单元值，因此它可以自动排序。</span><span class="sxs-lookup"><span data-stu-id="01cee-110">It contains actual cell values that are strings, however, so it can be sorted automatically.</span></span>  
  
### <a name="to-set-the-sort-mode-for-a-column"></a><span data-ttu-id="01cee-111">设置列的排序模式</span><span class="sxs-lookup"><span data-stu-id="01cee-111">To set the sort mode for a column</span></span>  
  
- <span data-ttu-id="01cee-112">设置 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="01cee-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="01cee-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="01cee-113">Compiling the Code</span></span>  
 <span data-ttu-id="01cee-114">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="01cee-114">This example requires:</span></span>  
  
- <span data-ttu-id="01cee-115">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件，其包含一个名为 `Priority` 的列。</span><span class="sxs-lookup"><span data-stu-id="01cee-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Priority`.</span></span>  
  
- <span data-ttu-id="01cee-116">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="01cee-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01cee-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01cee-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="01cee-118">在 Windows 窗体 DataGridView 控件中对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="01cee-118">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="01cee-119">Windows 窗体 DataGridView 控件中的列排序模式</span><span class="sxs-lookup"><span data-stu-id="01cee-119">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="01cee-120">如何：在 Windows 窗体 DataGridView 控件中自定义排序</span><span class="sxs-lookup"><span data-stu-id="01cee-120">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
