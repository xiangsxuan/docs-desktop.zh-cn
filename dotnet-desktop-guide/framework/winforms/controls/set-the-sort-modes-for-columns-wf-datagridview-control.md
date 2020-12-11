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
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a>如何：设置 Windows 窗体 DataGridView 控件中列的排序模式
在 <xref:System.Windows.Forms.DataGridView> 控件中，默认情况下，文本框列使用自动排序，而其他列类型不会自动排序。 有时，您需要重写这些默认值。 例如，可以显示图像来代替文本、数字或枚举单元值。 当无法对图像进行排序时，可以对它们所表示的基础值进行排序。  
  
 在 <xref:System.Windows.Forms.DataGridView> 控件中， <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 列的属性值决定了其排序行为。  
  
 下面的过程显示了 `Priority` [如何：自定义 Windows 窗体 DataGridView 控件中的数据格式](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)的列。 此列是图像列，默认情况下不可排序。 它包含作为字符串的实际单元值，因此它可以自动排序。  
  
### <a name="to-set-the-sort-mode-for-a-column"></a>设置列的排序模式  
  
- 设置 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> 属性。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件，其包含一个名为 `Priority` 的列。  
  
- 对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [在 Windows 窗体 DataGridView 控件中对数据进行排序](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的列排序模式](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [如何：在 Windows 窗体 DataGridView 控件中自定义排序](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
