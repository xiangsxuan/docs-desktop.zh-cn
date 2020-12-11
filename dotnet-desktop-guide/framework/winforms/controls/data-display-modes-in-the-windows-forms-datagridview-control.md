---
title: DataGridView 控件中的数据显示模式
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
ms.openlocfilehash: ad6be647e3a36904b055fd6771f539df28938fab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970140"
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的数据显示模式
<xref:System.Windows.Forms.DataGridView>控件可以在三种不同模式下显示数据：绑定、未绑定和虚拟。 根据要求选择最适合的模式。  
  
## <a name="unbound"></a>未绑定  
 取消绑定模式适用于显示以编程方式管理的相对较少的数据量。 不要将 <xref:System.Windows.Forms.DataGridView> 控件直接作为绑定模式附加到数据源。 相反，您必须自行填充控件，通常使用 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> 方法。  
  
 未绑定模式对于静态、只读数据，或者当你想要提供你自己的与外部数据存储交互的代码时特别有用。 但是，如果希望用户与外部数据源进行交互，通常会使用绑定模式。  
  
 有关使用只读未绑定的示例 <xref:System.Windows.Forms.DataGridView> ，请参阅 [如何：创建未绑定的 Windows 窗体 DataGridView 控件](how-to-create-an-unbound-windows-forms-datagridview-control.md)。  
  
## <a name="bound"></a>Bound  
 绑定模式适用于使用与数据存储区的自动交互来管理数据。 <xref:System.Windows.Forms.DataGridView>通过设置属性，可以将控件直接附加到其数据源 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 。 当控件被数据绑定时，将推送和拉取数据行，而无需对你的部分进行显式管理。 当 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> 属性为时 `true` ，数据源中的每一列都将导致在控件中创建相应的列。 如果你想要创建自己的列，则可以将此属性设置为， `false` 并在 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> 配置每列时使用属性对其进行绑定。 如果要使用默认情况下生成的类型之外的列类型，则此方法非常有用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件中的列类型](column-types-in-the-windows-forms-datagridview-control.md)。  
  
 有关使用绑定控件的示例 <xref:System.Windows.Forms.DataGridView> ，请参阅 [演练：验证 Windows 窗体 DataGridView 控件中的数据](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)。  
  
 还可以 <xref:System.Windows.Forms.DataGridView> 在绑定模式下向控件添加未绑定的列。 当您想要显示允许用户对特定行执行操作的按钮或链接列时，这非常有用。 它还可用于显示包含从绑定列计算的值的列。 您可以在事件的处理程序中填充计算列的单元值 <xref:System.Windows.Forms.DataGridView.CellFormatting> 。 但是，如果您使用的是 <xref:System.Data.DataSet> 或 <xref:System.Data.DataTable> 作为数据源，则可以改为使用 <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType> 属性创建计算列。 在这种情况下， <xref:System.Windows.Forms.DataGridView> 控件将像处理数据源中的任何其他列一样处理计算列。  
  
 不支持在绑定模式下按未绑定列进行排序。 如果在绑定模式下创建的未绑定列包含用户可编辑的值，则当控件按绑定列进行排序时，必须实现虚拟模式来维护这些值。  
  
## <a name="virtual"></a>虚拟  
 在虚拟模式下，你可以实现你自己的数据管理操作。 在按绑定列对控件进行排序时，必须使用此方法来维护绑定模式下未绑定列的值。 不过，虚拟模式的主要用途是在与大量数据进行交互时优化性能。  
  
 将该 <xref:System.Windows.Forms.DataGridView> 控件附加到你管理的缓存，你的代码将控制何时推送和拉取数据行。 若要使内存占用量较小，缓存大小应与当前显示的行数大小相似。 当用户将新行滚动到视图中时，你的代码将请求缓存中的新数据，并选择性地从内存中刷新旧数据。  
  
 在实现虚拟模式时，需要跟踪数据模型中何时需要新行以及何时回滚新行的添加。 此功能的确切实现将取决于数据模型的实现和数据模型的事务语义;提交范围是否位于单元或行级别。  
  
 有关虚拟模式的详细信息，请参阅 [Windows 窗体 DataGridView 控件中的虚拟模式](virtual-mode-in-the-windows-forms-datagridview-control.md)。 有关演示如何使用虚拟模式事件的示例，请参阅 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>
- [在 Windows 窗体 DataGridView 控件中显示数据](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的列类型](column-types-in-the-windows-forms-datagridview-control.md)
- [演练：创建未绑定的 Windows 窗体 DataGridView 控件](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [如何：将数据绑定到 Windows 窗体 DataGridView 控件](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的虚拟模式](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)
