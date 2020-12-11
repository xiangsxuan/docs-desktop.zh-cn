---
title: 使用设计器将 DataGrid 控件绑定到数据源
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: 67e1e99f404875b9945d934ef54dea3449ef6b26
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970715"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a>如何：使用设计器将 Windows 窗体 DataGrid 控件绑定到数据源

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。

 Windows 窗体 <xref:System.Windows.Forms.DataGrid> 控件专门用于显示数据源中的信息。 您可以通过设置和属性在设计时绑定 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 控件 <xref:System.Windows.Forms.DataGrid.DataMember%2A> ，或在运行时通过调用方法来绑定控件 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 。 尽管可以显示来自多种数据源的数据，但最常见的数据源是数据集和数据视图。

 如果数据源在设计时可用（例如，如果窗体包含数据集或数据视图的实例），则可以在设计时将网格绑定到数据源。 然后，可以在网格中预览数据的外观。

 你还可以在运行时以编程方式绑定网格。 如果要基于在运行时获取的信息设置数据源，此方法非常有用。 例如，应用程序可能会让用户指定要查看的表的名称。 在设计时不存在数据源的情况下，也是必需的。 这包括数据源（如数组、集合、非类型化数据集和数据读取器）。

 下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.DataGrid> 。 有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。 在 Visual Studio 2005 中， <xref:System.Windows.Forms.DataGrid> 默认情况下控件不在 **工具箱** 中。 有关添加它的信息，请参阅 [如何：向工具箱添加项](/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))。 此外，在 Visual Studio 2005 中，可以使用 " **数据源** " 窗口进行设计时数据绑定。 有关详细信息，请参阅 [在 Visual Studio 中将控件绑定到数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)。

## <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a>将 DataGrid 控件数据绑定到设计器中的单个表

1. 将控件的 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 属性设置为包含要绑定到的数据项的对象。

2. 如果数据源是一个数据集，则将 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 属性设置为要绑定到的表的名称。

3. 如果数据源是基于数据集表的数据集或数据视图，请将代码添加到窗体中以填充数据集。

     你使用的确切代码取决于数据集获取数据的位置。 如果直接从数据库填充数据集，则通常调用 `Fill` 数据适配器的方法，如以下代码示例所示，该示例将填充名为的数据集 `DsCategories1` ：

    ```vb
    sqlDataAdapter1.Fill(DsCategories1)
    ```

    ```csharp
    sqlDataAdapter1.Fill(DsCategories1);
    ```

    ```cpp
    sqlDataAdapter1->Fill(dsCategories1);
    ```

4.  (可选) 将相应的表样式和列样式添加到网格。

     如果没有表样式，您将看到该表，但其格式设置和所有列都可见。

## <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a>在设计器中将 DataGrid 控件数据绑定到数据集中的多个表

1. 将控件的 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 属性设置为包含要绑定到的数据项的对象。

2. 如果数据集包含相关表 (也就是说，如果它包含关系对象) ，则将属性设置 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 为父表的名称。

3. 编写代码以填充数据集。

## <a name="see-also"></a>另请参阅

- [DataGrid 控件概述](datagrid-control-overview-windows-forms.md)
- [如何：向 Windows 窗体 DataGrid 控件添加表和列](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [DataGrid 控件](datagrid-control-windows-forms.md)
- [Windows 窗体数据绑定](../windows-forms-data-binding.md)
- [在 Visual Studio 中访问数据](/visualstudio/data-tools/accessing-data-in-visual-studio)
