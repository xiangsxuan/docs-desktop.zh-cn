---
title: 使用设计器设置 DataGrid 控件的格式
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], DataGrid controls
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
ms.openlocfilehash: fa0584cd3c309fc6bd9144be6e3d4e1920290ac0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971175"
---
# <a name="how-to-format-the-windows-forms-datagrid-control-using-the-designer"></a>如何：使用设计器设置 Windows 窗体 DataGrid 控件的格式

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。

将不同的颜色应用于控件的各个部分， <xref:System.Windows.Forms.DataGrid> 有助于更轻松地读取和解释信息。 颜色可以应用于行和列。 还可以根据自己的意愿隐藏或显示行和列。

有三个基本方面的控件设置格式 <xref:System.Windows.Forms.DataGrid> ：

- 可以设置属性来建立显示数据的默认样式。

- 然后，你可以在运行时自定义某些表的显示方式。

- 最后，您可以修改在数据网格中显示的列，以及所显示的颜色和其他格式设置。

作为数据网格格式设置的初始步骤，您可以设置其自身的属性 <xref:System.Windows.Forms.DataGrid> 。 这些颜色和格式选项构成一个基础，您可以根据所显示的数据表和列进行更改。

下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.DataGrid> 。 有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。 在 Visual Studio 2005 中， <xref:System.Windows.Forms.DataGrid> 默认情况下控件不在 **工具箱** 中。 有关详细信息，请参阅 [如何：向工具箱添加项](/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))。

### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>为 DataGrid 控件建立默认样式

1. 选择 <xref:System.Windows.Forms.DataGrid> 控件。

2. 根据需要，在 " **属性** " 窗口中设置以下属性。

    |属性|描述|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|`BackColor`属性定义网格中偶数行的颜色。 如果将属性设置 <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 为其他颜色，则每个其他行都设置为此新颜色 (第1、3、5) 的行。|
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|网格中偶数行的背景色 (第0、2、4、6) 行。|
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<xref:System.Windows.Forms.DataGrid.BackColor%2A>和 <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 属性确定网格中的行的颜色，而 <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> 属性决定行区域外的区域的颜色，这仅在网格滚动到底部时可见，或在网格中只包含几行时可见。|
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|网格的边框样式，其中一个 <xref:System.Windows.Forms.BorderStyle> 枚举值。|
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|网格窗口标题紧上方显示的背景色。|
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|网格顶部的标题的字体。|
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|网格窗口标题的背景色。|
    |<xref:System.Windows.Forms.Control.Font%2A>|用于在网格中显示文本的字体。|
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|数据网格的行中的数据所显示的字体颜色。|
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|数据网格网格线的颜色。|
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|分隔网格中的单元格的行样式，是 <xref:System.Windows.Forms.DataGridLineStyle> 枚举值之一。|
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|行标题和列标题的背景色。|
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|列标题所用的字体。|
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|网格的列标题的前景色，包括列标题文本和加号 (+) 和减号 (-) 在显示多个相关表时展开和折叠行的标志符号。|
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|数据网格中所有链接的文本颜色，包括指向子表的链接、关系名称，等等。|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|在子表中，这是父行的背景色。|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|在子表中，这是父行的前景色。|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|通过枚举确定是否在父行中显示表和列的名称 <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> 。|
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|网格中列的默认宽度（以像素为单位）。 在重置和属性之前设置此属性 <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> (单独或通过 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 方法) ，否则属性将不起作用。<br /><br /> 不能将属性设置为小于0的值。|
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|网格中行的行高 (以像素为单位) 。 在重置和属性之前设置此属性 <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> (单独或通过 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 方法) ，否则属性将不起作用。<br /><br /> 不能将属性设置为小于0的值。|
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|网格行标题的宽度。|
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|选择行或单元格时，这是背景色。|
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|选择行或单元格时，这是前景色。|

    > [!NOTE]
    > 自定义控件的颜色时，可能会由于颜色选择不佳 (例如，红色和绿色) 导致控件不可访问。 使用 " **系统颜色** " 调色板中的可用颜色来避免此问题。

    下面的过程要求将 <xref:System.Windows.Forms.DataGrid> 控件绑定到数据表。 有关详细信息，请参阅 [如何：将 Windows 窗体 DataGrid 控件绑定到数据源](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)。

### <a name="to-set-the-table-and-column-style-of-a-data-table-at-design-time"></a>在设计时设置数据表的表和列样式

1. 选择 <xref:System.Windows.Forms.DataGrid> 窗体上的控件。

2. 在 "**属性**" 窗口中，选择 "属性"， <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 然后单击 **省略号** 按钮 (" ![) 属性窗口中的" ( ... ) "。 ](./media/visual-studio-ellipsis-button.png)

3. 在 " **DataGridTableStyle 集合编辑器** " 对话框中，单击 " **添加** " 将表样式添加到集合。

     通过 **DataGridTableStyle 集合编辑器**，您可以添加和删除表样式、设置显示和布局属性以及设置表样式的映射名称。

4. 将 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 属性设置为每个表样式的映射名称。

     映射名称用于指定应将哪个表样式与哪个表一起使用。

5. 在 **DataGridTableStyle 集合编辑器** 中，选择 " <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 属性"，然后单击省略号按钮 (![ 属性窗口的 "Visual) Studio" ( ... ) 。 ](./media/visual-studio-ellipsis-button.png)

6. 在 " **System.windows.forms.datagridcolumnstyle> 集合编辑器** " 对话框中，将列样式添加到所创建的表样式中。

     通过 **System.windows.forms.datagridcolumnstyle> 集合编辑器**，您可以添加和删除列样式、设置显示和布局属性以及为数据列设置映射名称和格式字符串。

    > [!NOTE]
    > 有关设置字符串格式的详细信息，请参阅 [格式设置类型](/dotnet/standard/base-types/formatting-types)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid 控件](datagrid-control-windows-forms.md)
