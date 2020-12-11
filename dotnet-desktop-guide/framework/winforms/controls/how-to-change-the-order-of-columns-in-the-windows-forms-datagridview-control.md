---
title: 更改 DataGridView 控件中列的顺序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: 2aef196e9544a81f42a563783ce6c357869aa247
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972058"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a>如何：更改 Windows 窗体 DataGridView 控件中列的顺序
使用 <xref:System.Windows.Forms.DataGridView> 显示来自数据源的数据时，有时数据源架构中的列不会按你想要显示的顺序显示。 可以通过使用 <xref:System.Windows.Forms.DataGridViewColumn> 类的 <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> 属性，更改列的显示顺序。  
  
 以下代码示例将重新定位绑定到 Northwind 示例数据库中的客户表时自动生成的某些列。 有关如何将 <xref:System.Windows.Forms.DataGridView> 控件绑定到数据库表的详细信息，请参阅 [如何：将数据绑定到 Windows 窗体 DataGridView 控件](how-to-bind-data-to-the-windows-forms-datagridview-control.md)。  
  
 Visual Studio 中对此任务提供支持。  另请参阅 [如何：使用设计器更改 Windows 窗体 DataGridView 控件中列的顺序](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 绑定到具有指示列名的表（例如 Northwind 示例数据库中的 `Customers` 表）的、名为 `customersDataGridView` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
- 对 <xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、<xref:System.Data?displayProperty=nameWithType> 和 <xref:System.Xml?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [在 Windows 窗体 DataGridView 控件中显示数据](displaying-data-in-the-windows-forms-datagridview-control.md)
- [如何：将数据绑定到 Windows 窗体 DataGridView 控件](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
