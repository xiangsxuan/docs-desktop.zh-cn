---
title: 如何：导航数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
ms.openlocfilehash: 2dd900b652b0ff21ea0eb0dbc5463b22c869ec7c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972788"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>如何：在 Windows 窗体中导航数据
在 Windows 应用程序中，在数据源中导航记录的最简单方法是将组件绑定 <xref:System.Windows.Forms.BindingSource> 到数据源，然后将控件绑定到 <xref:System.Windows.Forms.BindingSource> 。 然后，你可以在、和上使用内置的导航方法 <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.MoveNext%2A> <xref:System.Windows.Forms.BindingSource.MoveLast%2A> <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> 。 使用这些方法会 <xref:System.Windows.Forms.BindingSource.Position%2A> <xref:System.Windows.Forms.BindingSource.Current%2A> 正确地调整和属性 <xref:System.Windows.Forms.BindingSource> 。 还可以通过设置属性来查找项并将其设置为当前项 <xref:System.Windows.Forms.BindingSource.Position%2A> 。  
  
### <a name="to-increment-the-position-in-a-data-source"></a>递增数据源中的位置  
  
1. 将 <xref:System.Windows.Forms.BindingSource.Position%2A> 绑定数据的的属性设置为 <xref:System.Windows.Forms.BindingSource> 要定位到的记录位置。 下面的示例演示如何使用的 <xref:System.Windows.Forms.BindingSource.MoveNext%2A> 方法在 <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.Position%2A> 单击时递增属性 `nextButton` 。 <xref:System.Windows.Forms.BindingSource>与 dataset 的表相关联 `Customers` `Northwind` 。  
  
    > [!NOTE]
    > 将 <xref:System.Windows.Forms.BindingSource.Position%2A> 属性设置为超出第一条或最后一条记录的值不会导致错误，因为 .NET Framework 不允许将位置设置为列表边界以外的值。 如果你的应用程序中有必要了解你是否已超出第一条或最后一条记录，请包括用于测试是否会超出数据元素计数的逻辑。  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>检查是否已通过结尾或开头  
  
1. 为 <xref:System.Windows.Forms.BindingSource.PositionChanged> 事件创建一个事件处理程序。 在处理程序中，你可以测试建议的位置值是否超过了实际的数据元素计数。  
  
     下面的示例演示如何测试是否已到达最后一个数据元素。 在此示例中，如果您位于最后一个元素，则窗体上的 " **下一步** " 按钮处于禁用状态。  
  
    > [!NOTE]
    > 请注意，如果您在代码中导航列表，应重新启用 " **下一步** " 按钮，以便用户可以浏览新列表的整个长度。 此外，请注意，所使用的 <xref:System.Windows.Forms.BindingSource.PositionChanged> 特定的事件 <xref:System.Windows.Forms.BindingSource> 需要与其事件处理方法关联。 下面是用于处理事件的方法的示例 <xref:System.Windows.Forms.BindingSource.PositionChanged> ：  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>查找项并将其设置为当前项  
  
1. 查找要设置为当前项的记录。 <xref:System.Windows.Forms.BindingSource.Find%2A> <xref:System.Windows.Forms.BindingSource> 如果数据源实现，则可以使用的方法执行此操作 <xref:System.ComponentModel.IBindingList> 。 实现的数据源的一些示例 <xref:System.ComponentModel.IBindingList> 包括 <xref:System.ComponentModel.BindingList%601> 和 <xref:System.Data.DataView> 。  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体支持的数据源](data-sources-supported-by-windows-forms.md)
- [Windows 窗体数据绑定中的更改通知](change-notification-in-windows-forms-data-binding.md)
- [数据绑定和 Windows 窗体](data-binding-and-windows-forms.md)
- [Windows 窗体数据绑定](windows-forms-data-binding.md)
