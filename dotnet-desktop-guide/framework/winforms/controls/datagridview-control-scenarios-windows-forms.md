---
title: DataGridView 控件方案
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
ms.openlocfilehash: 160d967c6445fb753cb6c73babfb02a734a07e28
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970115"
---
# <a name="datagridview-control-scenarios-windows-forms"></a>DataGridView 控件方案（Windows 窗体）
使用 <xref:System.Windows.Forms.DataGridView> 控件，可以显示来自各种数据源的表格数据。 对于简单的用法，可以手动填充 <xref:System.Windows.Forms.DataGridView> 并通过控件直接操作数据。 不过，通常会将数据存储在外部数据源中，并通过组件将控件绑定到该数据源 <xref:System.Windows.Forms.BindingSource> 。  
  
 本主题介绍了一些涉及控件的常见方案 <xref:System.Windows.Forms.DataGridView> 。  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a>方案1：显示少量数据  
 无需将数据存储在外部数据源中即可在控件中显示数据 <xref:System.Windows.Forms.DataGridView> 。 如果你使用少量的数据，则可以自行填充控件，并通过控件处理数据。 这称为 *未绑定模式*。 有关详细信息，请参阅 [如何：创建未绑定的 Windows 窗体 DataGridView 控件](how-to-create-an-unbound-windows-forms-datagridview-control.md)。  
  
### <a name="scenario-key-points"></a>方案关键点  
  
- 在未绑定模式下，手动填充控件。  
  
- 未绑定模式特别适用于少量的只读数据。  
  
- 未绑定模式也适用于类似电子表格或稀疏填充的表。  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a>方案2：查看和更新存储在外部数据源中的数据  
 您可以使用 <xref:System.Windows.Forms.DataGridView> 控件作为 (UI) 用户界面，用户可以通过该界面访问数据源（如数据库表或业务对象集合）中保存的数据。 有关详细信息，请参阅 [如何：将数据绑定到 Windows 窗体 DataGridView 控件](how-to-bind-data-to-the-windows-forms-datagridview-control.md)。  
  
### <a name="scenario-key-points"></a>方案关键点  
  
- 绑定模式使您可以连接到数据源，并基于数据源属性或数据库列自动生成列，并自动填充控件。  
  
- 绑定模式适用于与数据的繁重用户交互。 数据可以设置为显示格式，用户指定的数据可以解析为数据源所需的格式。 可以检测到数据输入格式错误和数据库约束错误，以便可以警告用户和更正错误的单元格。  
  
- 其他功能（如列排序、冻结和重新排序）使用户能够以最方便的方式查看其工作流中的数据。  
  
- 剪贴板支持使用户能够将数据从应用程序复制到其他应用程序。  
  
## <a name="scenario-3-advanced-data"></a>方案3：高级数据  
 如果你有标准数据绑定模型没有解决的特殊需求，则可以通过实现 *虚拟模式* 来管理控件和数据之间的交互。 实现虚拟模式意味着实现一个或多个事件处理程序，以便在需要信息时控制单元请求相关信息。  
  
 例如，如果你使用大量数据，则可能需要实现虚拟模式，以确保获得最佳效率。 虚拟模式对于维护与从另一个数据源检索的列一起显示的未绑定列的值也很有用。  
  
 有关虚拟模式的详细信息，请参阅 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)。  
  
### <a name="scenario-key-points"></a>方案关键点  
  
- 当你需要对性能进行微调时，虚拟模式适用于显示大量的数据。  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a>方案4：自动调整行和列的大小  
 当显示定期更新的数据时，可以自动调整行和列的大小，以确保所有内容都可见。 <xref:System.Windows.Forms.DataGridView>控件提供了几个选项，可用于启用或禁用手动调整大小、在特定时间以编程方式调整大小，或在内容发生更改时自动调整大小。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件中的调整大小选项](sizing-options-in-the-windows-forms-datagridview-control.md)。  
  
### <a name="scenario-key-points"></a>方案关键点  
  
- 手动调整大小使用户能够调整单元高度和宽度。  
  
- 自动调整大小使您能够保持单元大小，以便永远不会剪辑单元内容。  
  
- 编程调整大小使您能够在特定时间调整单元格的大小，以避免连续自动调整大小的性能损失。  
  
## <a name="scenario-5-simple-customization"></a>方案5：简单自定义  
 <xref:System.Windows.Forms.DataGridView>控件提供多种方法来更改其基本外观和行为。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。  
  
### <a name="scenario-key-points"></a>方案关键点  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle> 通过对象，可以在多个级别和控件的单个元素上提供颜色、字体、格式设置和定位信息。  
  
- 单元格样式可由多个元素分层和共享，从而使你可以重复使用代码。  
  
## <a name="scenario-6-advanced-customization"></a>方案6：高级自定义  
 <xref:System.Windows.Forms.DataGridView>控件提供多种方法用于自定义其外观和行为。  
  
### <a name="scenario-key-points"></a>方案关键点  
  
- 可以提供自己的单元格绘制代码。 有关详细信息，请参阅 [如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md)。  
  
- 可以提供自己的行绘制。 这很有用，例如，创建包含跨多个列的内容的行。 有关详细信息，请参阅 [如何：自定义 Windows 窗体 DataGridView 控件中的行的外观](customize-the-appearance-of-rows-in-the-datagrid.md)。  
  
- 您可以实现自己的单元格和列类，以自定义单元格的外观。 有关详细信息，请参阅 [如何：通过扩展控件的行为和外观自定义 Windows 窗体 DataGridView 控件中的单元格和列](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)。  
  
- 您可以实现自己的单元格和列类来承载除内置列类型提供的控件以外的其他控件。 有关详细信息，请参阅 [如何：在 Windows 窗体 DataGridView 单元格中承载控件](how-to-host-controls-in-windows-forms-datagridview-cells.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- [DataGridView 控件概述](datagridview-control-overview-windows-forms.md)
