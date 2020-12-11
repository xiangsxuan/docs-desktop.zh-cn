---
title: 自定义 DataGridView 控件中单元格的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970149"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="15992-102">如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观</span><span class="sxs-lookup"><span data-stu-id="15992-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="15992-103">您可以通过处理控件的事件来自定义任意单元格的外观 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.CellPainting> 。</span><span class="sxs-lookup"><span data-stu-id="15992-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="15992-104">你可以 <xref:System.Windows.Forms.DataGridView> <xref:System.Drawing.Graphics> 从的属性中提取控件的 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="15992-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="15992-105">这样 <xref:System.Drawing.Graphics> ，你就可以影响整个控件的外观 <xref:System.Windows.Forms.DataGridView> ，但你通常只想影响当前正在绘制的单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="15992-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="15992-106"><xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A>的属性 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> 使你能够将绘制操作限制为当前正在绘制的单元格。</span><span class="sxs-lookup"><span data-stu-id="15992-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="15992-107">在下面的代码示例中，您将 `ContactName` 使用 <xref:System.Windows.Forms.DataGridView> 控件的配色方案绘制列中的所有单元格。</span><span class="sxs-lookup"><span data-stu-id="15992-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="15992-108">在中绘制每个单元格的文本内容 <xref:System.Drawing.Color.Crimson%2A> ，并以与 <xref:System.Windows.Forms.DataGridView> 控件的属性相同的颜色绘制嵌入矩形 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 。</span><span class="sxs-lookup"><span data-stu-id="15992-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15992-109">示例</span><span class="sxs-lookup"><span data-stu-id="15992-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="15992-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="15992-110">Compiling the Code</span></span>  
 <span data-ttu-id="15992-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="15992-111">This example requires:</span></span>  
  
- <span data-ttu-id="15992-112">一个 <xref:System.Windows.Forms.DataGridView> 名为的控件 `dataGridView1` ，其 `ContactName` 列如 Northwind 示例数据库的 Customers 表中的列。</span><span class="sxs-lookup"><span data-stu-id="15992-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="15992-113">对 System、System.Windows.Forms 和 System.Drawing 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="15992-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15992-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15992-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="15992-115">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="15992-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
