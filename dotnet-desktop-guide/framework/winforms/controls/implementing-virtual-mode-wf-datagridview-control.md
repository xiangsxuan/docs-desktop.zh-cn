---
title: 演练：在 DataGridView 控件中实现虚拟模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 5db97b321238bc371c94e627a387bd83ca31b58a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972630"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a>演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式
如果要在控件中显示大量的表格数据 <xref:System.Windows.Forms.DataGridView> ，可以将 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 属性设置为， `true` 并显式管理控件与其数据存储区的交互。 这使您能够在这种情况下微调控件的性能。  
  
 <xref:System.Windows.Forms.DataGridView>控件提供若干事件，您可以处理这些事件以与自定义数据存储进行交互。 本演练将指导您完成实现这些事件处理程序的过程。 出于说明目的，本主题中的代码示例使用非常简单的数据源。 在生产设置中，通常只加载需要显示到缓存中的行，并处理 <xref:System.Windows.Forms.DataGridView> 事件以与缓存交互并更新缓存。 有关详细信息，请参阅 [在 Windows 窗体 DataGridView 控件中实现包含实时数据加载的虚拟模式](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
  
 若要将本主题中的代码复制为单个列表，请参阅 [如何：在 Windows 窗体 DataGridView 控件中实现虚拟模式](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="creating-the-form"></a>创建窗体  
  
#### <a name="to-implement-virtual-mode"></a>实现虚拟模式  
  
1. 创建一个派生自的类 <xref:System.Windows.Forms.Form> ，并包含一个 <xref:System.Windows.Forms.DataGridView> 控件。  
  
     下面的代码包含一些基本的初始化。 它声明将在后面的步骤中使用的一些变量，提供 `Main` 方法，并在类构造函数中提供简单的窗体布局。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. 实现窗体事件的处理程序 <xref:System.Windows.Forms.Form.Load> ，该处理程序初始化 <xref:System.Windows.Forms.DataGridView> 控件并使用示例值填充数据存储区。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. 实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> ，该事件从数据存储区或当前正在编辑的对象中检索请求的单元格值 `Customer` 。  
  
     此事件在 <xref:System.Windows.Forms.DataGridView> 控件需要绘制单元格时发生。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. 实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.CellValuePushed> ，该事件在 `Customer` 表示所编辑的行的对象中存储已编辑的单元值。 当用户提交单元值更改时，将发生此事件。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. 实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.NewRowNeeded> ，该事件创建 `Customer` 表示新创建的行的新对象。  
  
     此事件在用户进入新记录行时出现。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. 实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.RowValidated> ，该事件将新行或修改过的行保存到数据存储区。  
  
     当用户更改当前行时，将发生此事件。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. 实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> ，该事件指示 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 当用户通过在编辑模式中按 ESC 两次或在编辑模式之外时，是否会发出事件。  
  
     默认情况下， <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 当修改了当前行中的任何单元格时，除非在 <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> `true` <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 事件处理程序中将属性设置为，否则将在行重新确定时出现。 在运行时确定提交范围时，此事件很有用。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. 实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> ，该事件会丢弃 `Customer` 表示当前行的对象的值。  
  
     当用户通过在编辑模式中按 ESC 两次或在编辑模式之外时，将发生此事件。 如果当前行中没有单元格已修改，或者在 <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> `false` 事件处理程序中已将属性的值设置为，则不会发生此事件 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. 实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.UserDeletingRow> ，该事件 `Customer` 从数据存储区中删除现有的对象，或者放弃 `Customer` 表示新创建的行的未保存对象。  
  
     当用户通过单击行标题并按 DELETE 键删除行时，将发生此事件。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. 实现一个简单的 `Customers` 类，以表示此代码示例使用的数据项。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a>测试应用程序  
 你现在可以对窗体进行测试，以确保它按预期方式运行。  
  
#### <a name="to-test-the-form"></a>测试窗体  
  
- 编译并运行该应用程序。  
  
     你将看到一个 <xref:System.Windows.Forms.DataGridView> 控件填充了三个客户记录。 您可以修改某个行中多个单元格的值，并在编辑模式下按 ESC 两次，在编辑模式之外，将整行还原为其原始值。 在控件中修改、添加或删除行时， `Customer` 也会修改、添加或删除数据存储区中的对象。  
  
## <a name="next-steps"></a>后续步骤  
 通过此应用程序，您可以对在控件中实现虚拟模式所必须处理的事件有一个基本的了解 <xref:System.Windows.Forms.DataGridView> 。 可以通过多种方式改进此基本应用程序：  
  
- 实现用于缓存外部数据库中的值的数据存储区。 缓存应根据需要检索和丢弃值，以便它仅包含在使用客户端计算机上的少量内存时显示所需的内容。  
  
- 根据您的要求，微调数据存储区的性能。 例如，你可能想要使用较大的缓存大小来补偿慢速网络连接而不是客户端计算机内存限制，并将数据库查询的数量降至最低。  
  
 有关从外部数据库缓存值的详细信息，请参阅 [如何：使用 Windows 窗体 DataGridView 控件中的实时数据加载实现虚拟模式](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [Windows 窗体 DataGridView 控件中的性能优化](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [缩放 Windows 窗体 DataGridView 控件的最佳做法](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [如何：在 Windows 窗体 DataGridView 控件中实现虚拟模式](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
