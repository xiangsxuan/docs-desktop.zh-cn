---
title: DataGridView 控件技术摘要
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: 1b620cabb756fadb8468fc75879025131e4bffd8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970114"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>DataGridView 控件技术摘要（Windows 窗体）

本主题概述了 `DataGridView` 控件及支持其使用的类的相关信息。  
  
 以表格格式显示数据是您可能经常要执行的任务。 `DataGridView`控件设计为在网格中显示数据的完整解决方案。  
  
## <a name="keywords"></a>关键字  

 DataGridView、BindingSource、表、单元格、数据绑定、虚拟模式  
  
## <a name="namespaces"></a>命名空间  

 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>相关技术  

 `BindingSource`  
  
## <a name="background"></a>背景  

 用户界面 (UI) 设计器经常发现向用户显示表格数据是必要的。 .NET Framework 提供了几种在表或网格中显示数据的方式。 `DataGridView`控件表示此技术对 Windows 窗体应用程序的最新演变。  
  
 `DataGridView`控件可以显示数据存储中的数据行。 支持多种类型的数据存储。 数据存储可以保存简单的非类型化数据（如一维数组），也可以保存类型化数据，如 <xref:System.Data.DataSet> 。 有关详细信息，请参阅 [如何：将数据绑定到 Windows 窗体 DataGridView 控件](how-to-bind-data-to-the-windows-forms-datagridview-control.md)。  
  
 `DataGridView` 控件提供一种以表格格式显示数据的功能强大且灵活的方法。 可以使用控件显示小型到非常大的数据集的只读或可编辑视图。  
  
 你可以 `DataGridView` 通过多种方式扩展该控件，以将自定义行为构建到你的应用程序中。 例如，可以以编程方式指定自己的排序算法，并且可以创建自己的单元格类型。 可以通过在多个属性之间进行选择来轻松地自定义 `DataGridView` 控件的外观。 许多类型的数据存储区都可以用作数据源，也可以在 `DataGridView` 没有绑定数据源的情况下操作控件。  
  
## <a name="implementing-datagridview-classes"></a>实现 DataGridView 类  

 可以通过多种方式利用 `DataGridView` 控件的扩展性功能。 您可以通过事件和属性来自定义控件的许多方面，但某些自定义要求您创建从现有类派生的新类 `DataGridView` 。  
  
 最常使用的基类有 `DataGridViewCell` 和 `DataGridViewColumn` 。 你可以从 `DataGridViewCell` 或其任意子类派生你自己的单元格类。 虽然您可以向任何列添加任何单元格类型，但在默认情况下，您通常还会从 `DataGridViewColumn` 该自定义单元格类型的单元格派生一个伴随列类。  
  
 您可以 `IDataGridViewEditingCell` 在派生的 cell 类中实现接口，以创建具有编辑功能但未在编辑模式下承载控件的单元类型。 若要创建可在编辑模式中承载的控件，可以在派生自的类中实现该 `IDataGridViewEditingControl` 接口 <xref:System.Windows.Forms.Control> 。  
  
 有关详细信息，请参阅 [如何：自定义 Windows 窗体 DataGridView 控件中的单元格和列，方法是扩展其行为和外观](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) ，以及 [如何：在 Windows 窗体 DataGridView 单元格中承载控件](how-to-host-controls-in-windows-forms-datagridview-cells.md)。  
  
## <a name="datagridview-classes-at-a-glance"></a>DataGridView 类一览  

 <xref:System.Windows.Forms>  
  
|技术范围|类/接口/配置元素|  
|---------------------|-------------------------------------------------|  
|数据绑定|<xref:System.Windows.Forms.BindingSource>|  
|数据显示|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> 和派生类<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> 和派生类<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> 和派生类<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView> 扩展性|<xref:System.Windows.Forms.DataGridViewCell> 和派生类<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> 和派生类<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>新增功能  

 <xref:System.Windows.Forms.DataGridView>控件旨在作为使用 Windows 窗体显示表格数据的完整解决方案。 在 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGrid> 创作新应用程序时，应考虑在其他解决方案（例如）上使用控件。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 <xref:System.Windows.Forms.DataGridView>控件可以与组件紧密配合工作 <xref:System.Windows.Forms.BindingSource> 。 此组件设计为窗体的主数据源。 它可以管理 <xref:System.Windows.Forms.DataGridView> 控件与其数据源之间的交互，而不考虑数据源类型。  
  
## <a name="see-also"></a>另请参阅

- [DataGridView 控件概述](datagridview-control-overview-windows-forms.md)
- [DataGridView 控件体系结构](datagridview-control-architecture-windows-forms.md)
- [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)
