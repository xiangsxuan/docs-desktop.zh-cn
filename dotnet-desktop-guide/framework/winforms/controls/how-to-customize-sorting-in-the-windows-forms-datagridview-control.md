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
# <a name="how-to-customize-sorting-in-the-windows-forms-datagridview-control"></a>如何：自定义 Windows 窗体 DataGridView 控件中的排序方式
<xref:System.Windows.Forms.DataGridView> 控件提供自动排序，但根据需要，你可能需要自定义排序操作。 例如，你可以使用编程排序来创建替代的用户界面 (UI)。 或者，你可以处理 <xref:System.Windows.Forms.DataGridView.SortCompare> 事件或调用 <xref:System.Windows.Forms.DataGridView.Sort%2A> 方法的 `Sort(IComparer)` 重载，以便进行更灵活的排序，例如对多个列进行排序。  
  
 下面的代码示例演示三种自定义排序方法。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件中的列排序模式](column-sort-modes-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="programmatic-sorting"></a>编程排序  
 下面的代码示例演示使用 <xref:System.Windows.Forms.DataGridView.SortOrder%2A> 和 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> 属性来确定排序方向，使用 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> 属性来手动设置排序标志符号的编程排序。 <xref:System.Windows.Forms.DataGridView.Sort%2A> 方法的 `Sort(DataGridViewColumn,ListSortDirection)` 重载仅用于对单个列中的数据进行排序。  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-sortcompare-event"></a>使用 SortCompare 事件自定义排序  
 下面的代码示例演示使用 <xref:System.Windows.Forms.DataGridView.SortCompare> 事件处理程序进行自定义排序。 对所选 <xref:System.Windows.Forms.DataGridViewColumn> 进行了排序，如果列中有重复的值，则使用 ID 列确定最终顺序。  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-icomparer-interface"></a>使用 IComparer 接口自定义排序  
 下面的代码示例演示使用 <xref:System.Windows.Forms.DataGridView.Sort%2A> 方法的 `Sort(IComparer)` 重载进行自定义排序，它通过实现 <xref:System.Collections.IComparer> 接口来执行多个列的排序。  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## <a name="compiling-the-code"></a>编译代码  
 这些示例需要：  
  
- 对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- [在 Windows 窗体 DataGridView 控件中对数据进行排序](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的列排序模式](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [如何：设置 Windows 窗体 DataGridView 控件中列的排序模式](set-the-sort-modes-for-columns-wf-datagridview-control.md)
