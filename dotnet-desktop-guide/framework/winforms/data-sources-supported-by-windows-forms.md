---
title: 支持的数据源
ms.date: 03/30/2017
helpviewer_keywords:
- collections [Windows Forms], binding to
- OLE DB providers [Windows Forms], Windows Forms
- DataTable class [Windows Forms], binding and Windows Forms
- Windows Forms, data binding
- DataView class [Windows Forms], binding and Windows Forms
- DataViewManager class [Windows Forms], binding and Windows Forms
- Windows Forms, source data
- arrays [Windows Forms]
- data sources [Windows Forms]
- data providers [Windows Forms]
- DataSet class [Windows Forms], binding and Windows Forms
- data [Windows Forms], data providers
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
ms.openlocfilehash: b4c1c722790688ee638aa4de417664f697df3249
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971743"
---
# <a name="data-sources-supported-by-windows-forms"></a>Windows 窗体支持的数据源

通常，在应用程序中使用数据绑定来利用存储在数据库中的数据。 使用 Windows 窗体数据绑定，只要满足某些最低要求，你就可以访问数据库中的数据以及其他结构中的数据（如数组和集合）。  
  
## <a name="structures-to-bind-to"></a>要绑定到的结构  

 在 Windows 窗体中，可以绑定到各种结构，从简单的对象 (简单绑定) 到复杂列表，如 ADO.NET 数据表 (复杂绑定) 。 对于简单绑定，Windows 窗体支持绑定到简单对象上的公共属性。 Windows 窗体基于列表的绑定通常要求对象支持 <xref:System.Collections.IList> 接口或 <xref:System.ComponentModel.IListSource> 接口。 此外，如果通过组件进行绑定 <xref:System.Windows.Forms.BindingSource> ，则可以绑定到支持接口的对象 <xref:System.Collections.IEnumerable> 。 有关与数据绑定相关的接口的详细信息，请参阅与 [数据绑定相关的接口](interfaces-related-to-data-binding.md)。  
  
 以下列表显示了可以在 Windows 窗体中绑定到的结构。  
  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingSource>是最常见的 Windows 窗体数据源，它在数据源和 Windows 窗体控件之间使用代理。 常规 <xref:System.Windows.Forms.BindingSource> 用法模式是将控件绑定到 <xref:System.Windows.Forms.BindingSource> 数据源，并将绑定 <xref:System.Windows.Forms.BindingSource> 到数据源 (例如，ADO.NET 数据表或业务对象) 。 <xref:System.Windows.Forms.BindingSource>提供的服务可用于启用和提高数据绑定支持的级别。 例如，Windows 窗体基于列表的控件（如 <xref:System.Windows.Forms.DataGridView> 和） <xref:System.Windows.Forms.ComboBox> 不直接支持绑定到 <xref:System.Collections.IEnumerable> 数据源，但你可以通过绑定来启用此方案 <xref:System.Windows.Forms.BindingSource> 。 在这种情况下， <xref:System.Windows.Forms.BindingSource> 会将数据源转换为 <xref:System.Collections.IList> 。  
  
 简单对象  
 Windows 窗体使用类型对对象实例上的公共属性支持数据绑定控件属性 <xref:System.Windows.Forms.Binding> 。 Windows 窗体还支持绑定列表控件，如 <xref:System.Windows.Forms.ListControl> 使用时为对象实例的 <xref:System.Windows.Forms.BindingSource> 。  
  
 数组或集合  
 若要作为数据源，列表必须实现 <xref:System.Collections.IList> 接口; 一个示例是类的实例 <xref:System.Array> 。 有关数组的详细信息，请参阅 [如何：创建 (Visual Basic) 的对象数组 ](/previous-versions/visualstudio/visual-studio-2010/487y7874(v=vs.100))。  
  
 通常，您应在 <xref:System.ComponentModel.BindingList%601> 为数据绑定创建对象列表时使用。 <xref:System.ComponentModel.BindingList%601> 是接口的泛型版本 <xref:System.ComponentModel.IBindingList> 。 <xref:System.ComponentModel.IBindingList>接口 <xref:System.Collections.IList> 通过添加双向数据绑定所需的属性、方法和事件来扩展接口。  
  
 <xref:System.Collections.IEnumerable>  
 Windows 窗体控件可以绑定到仅支持接口的数据源（ <xref:System.Collections.IEnumerable> 如果这些控件通过组件绑定） <xref:System.Windows.Forms.BindingSource> 。  
  
 ADO.NET 数据对象  
 ADO.NET 提供了一些适合绑定到的数据结构。 每个变量的复杂程度和复杂性各不相同。  
  
- <xref:System.Data.DataColumn>. <xref:System.Data.DataColumn>是的基本构建基块，因为 <xref:System.Data.DataTable> 许多列都包含一个表。 每个 <xref:System.Data.DataColumn> 属性都有一个 <xref:System.Data.DataColumn.DataType%2A> 属性，该属性确定列包含的数据类型 (例如，表中的汽车) 描述汽车的情况。 您可以简单地将控件 (如 <xref:System.Windows.Forms.TextBox> 控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性) 绑定到数据表中的列。  
  
- <xref:System.Data.DataTable>. <xref:System.Data.DataTable>是 ADO.NET 中具有行和列的表的表示形式。 数据表包含两个集合： <xref:System.Data.DataColumn> ，表示给定表中的数据列 (最终确定可输入到该表中的数据类型) 和 <xref:System.Data.DataRow> ，表示给定表中的数据行。 您可以将控件复杂地绑定到数据表中包含的信息 (例如，将 <xref:System.Windows.Forms.DataGridView> 控件绑定到) 的数据表。 但是，当您绑定到时 <xref:System.Data.DataTable> ，实际上就是绑定到表的默认视图。  
  
- <xref:System.Data.DataView>. <xref:System.Data.DataView>是可进行筛选或排序的单个数据表的自定义视图。 数据视图是复杂绑定控件使用的数据 "快照"。 您可以简单绑定或复杂地绑定到数据视图中的数据，但请注意，您要绑定到数据的固定 "图片"，而不是清除、更新数据源。  
  
- <xref:System.Data.DataSet>. <xref:System.Data.DataSet>是数据库中数据的表、关系和约束的集合。 您可以简单地绑定或复杂绑定到数据集中的数据，但是请注意，您将绑定到 (的默认 <xref:System.Data.DataViewManager> <xref:System.Data.DataSet> 项目符号) 。  
  
- <xref:System.Data.DataViewManager>. <xref:System.Data.DataViewManager>是整个的自定义视图 <xref:System.Data.DataSet> ， <xref:System.Data.DataView> 与类似，但包含关系。 对于 <xref:System.Data.DataViewManager.DataViewSettings%2A> 集合，可以为具有给定表的任何视图设置默认筛选器和排序选项 <xref:System.Data.DataViewManager> 。  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体数据绑定中的更改通知](change-notification-in-windows-forms-data-binding.md)
- [数据绑定和 Windows 窗体](data-binding-and-windows-forms.md)
- [Windows 窗体数据绑定](windows-forms-data-binding.md)
