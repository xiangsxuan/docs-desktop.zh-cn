---
title: DataGridView 控件中的单元格样式
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: fe56033a5adbe7719c64695c8f9ebc4f3644fc65
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971556"
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的单元格样式
控件中的每个单元格都 <xref:System.Windows.Forms.DataGridView> 可以有自己的样式，如文本格式、背景色、前景色和字体。 不过，通常情况下，多个单元格将共享特定的样式特征。  
  
 共享样式的单元格组可以包含特定行或列中的所有单元格、包含特定值的所有单元格或控件中的所有单元格。 由于这些组重叠，因此每个单元格可能会从多个位置获取其样式信息。 例如，您可能想要控件中的每个单元格都 <xref:System.Windows.Forms.DataGridView> 使用同一字体，但只有货币列中的单元格使用货币格式，而只有包含负数的货币单元格才能使用红色前景色。  
  
## <a name="the-datagridviewcellstyle-class"></a>DataGridViewCellStyle 类  
 <xref:System.Windows.Forms.DataGridViewCellStyle>类包含以下与视觉样式相关的属性：  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> 和 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> 和 <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 此类还包含以下与格式设置相关的属性：  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 和 <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> 和 <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 有关这些属性以及其他单元格样式属性的详细信息，请参阅 <xref:System.Windows.Forms.DataGridViewCellStyle> 下面的 "另请参阅" 部分中列出的参考文档和主题。  
  
## <a name="using-datagridviewcellstyle-objects"></a>使用 DataGridViewCellStyle 对象  
 可以 <xref:System.Windows.Forms.DataGridViewCellStyle> 从 <xref:System.Windows.Forms.DataGridView> 、 <xref:System.Windows.Forms.DataGridViewColumn> 、 <xref:System.Windows.Forms.DataGridViewRow> 和 <xref:System.Windows.Forms.DataGridViewCell> 类及其派生类的各种属性中检索对象。 如果尚未设置这些属性中的一个，则检索其值会创建一个新的 <xref:System.Windows.Forms.DataGridViewCellStyle> 对象。 你还可以实例化你自己的 <xref:System.Windows.Forms.DataGridViewCellStyle> 对象并将其分配给这些属性。  
  
 通过在 <xref:System.Windows.Forms.DataGridViewCellStyle> 多个元素之间共享对象，可以避免不必要地重复样式信息 <xref:System.Windows.Forms.DataGridView> 。 由于在控件、列和行级别设置的样式会向下筛选每个级别到单元格级别，因此还可以通过仅设置每个级别上不同于上述级别的样式属性来避免样式重复。 下面的 "样式继承" 部分对此进行了详细介绍。  
  
 下表列出了获取或设置对象的主要属性 <xref:System.Windows.Forms.DataGridViewCellStyle> 。  
  
|属性|类|描述|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>、 <xref:System.Windows.Forms.DataGridViewColumn> 、 <xref:System.Windows.Forms.DataGridViewRow> 和派生类|获取或设置整个控件中所有单元格使用的默认样式 (包括标题单元) 、列或行。|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|获取或设置控件中的所有行使用的默认单元格样式。 这不包括标头单元格。|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|获取或设置控件中的交替行使用的默认单元格样式。 用于创建类似帐目型的效果。|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|获取或设置控件的行标题使用的默认单元格样式。 如果启用了视觉样式，则由当前主题重写。|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|获取或设置控件的列标题使用的默认单元格样式。 如果启用了视觉样式，则由当前主题重写。|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> 和派生类|获取或设置在单元格级别指定的样式。 这些样式会重写从更高级别继承的样式。|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>、 <xref:System.Windows.Forms.DataGridViewRow> 、 <xref:System.Windows.Forms.DataGridViewColumn> 和派生类|获取当前应用于单元格、行或列的所有样式，包括从更高级别的继承的样式。|  
  
 如上所述， <xref:System.Windows.Forms.DataGridViewCellStyle> 如果以前尚未设置属性，则获取样式属性的值会自动实例化新的对象。 若要避免不必要地创建这些对象，则行和列类具有一个 <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> 属性，你可以对其进行检查以确定是否已 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> 设置该属性。 同样，cell 类具有一个 <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> 属性，该属性指示是否已 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 设置属性。  
  
 每个样式属性在控件上都有一个对应的 *PropertyName* `Changed` 事件 <xref:System.Windows.Forms.DataGridView> 。 对于行、列和单元属性，事件的名称以 " `Row` "、" `Column` " 或 " `Cell` " 开头 (例如 <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>) 。 当相应的样式属性设置为另一对象时，将发生这些事件中的每一个 <xref:System.Windows.Forms.DataGridViewCellStyle> 。 <xref:System.Windows.Forms.DataGridViewCellStyle>从样式属性检索对象并修改其属性值时，不会发生这些事件。 若要对单元格样式对象本身的更改做出响应，请处理 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> 事件。  
  
## <a name="style-inheritance"></a>样式继承  
 每个 <xref:System.Windows.Forms.DataGridViewCell> 从其属性中获取其外观 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 。 <xref:System.Windows.Forms.DataGridViewCellStyle>此属性返回的对象从类型为的属性的层次结构继承其值 <xref:System.Windows.Forms.DataGridViewCellStyle> 。 下面列出了这些属性，这些属性的顺序如下： <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 非标头单元格获取其值的顺序。  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> 仅对具有奇数索引号的行中的单元格 ()   
  
4. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 对于行标题单元格和列标题单元格， <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 按给定顺序按下面的源属性列表中的值填充属性。  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> 或 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 下图演示了此过程。  
  
 ![类型 DataGridViewCellStyle 的属性](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-inheritance-diagram.gif "DataGridViewCells 继承关系图")  
  
 还可以访问特定行和列继承的样式。 列 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> 属性从以下属性继承其值。  
  
1. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Row <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> 属性从以下属性继承其值。  
  
1. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> 仅对具有奇数索引号的行中的单元格 ()   
  
3. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 对于属性返回的对象中的每个属性 <xref:System.Windows.Forms.DataGridViewCellStyle> `InheritedStyle` ，将从相应列表中的第一个单元格样式获取属性值，该列表中的相应属性设置为默认值以外的值 <xref:System.Windows.Forms.DataGridViewCellStyle> 。  
  
 下表说明了如何 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 从其包含列继承示例单元格的属性值。  
  
|类型的属性 `DataGridViewCellStyle`|`ForeColor`检索的对象的示例值|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 在这种情况下，该 <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> 单元格的行中的值是列表中的第一个实际值。 这将成为该 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 单元格的属性值 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 。  
  
 下图说明了不同 <xref:System.Windows.Forms.DataGridViewCellStyle> 属性如何从不同的位置继承其值。  
  
 ![DataGridView 属性&#45;值继承](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-value-inheritance-diagram.gif "DataGridViewCells 值继承关系图")  
  
 利用样式继承，可以为整个控件提供适当的样式，而不必在多个位置指定相同的信息。  
  
 尽管标头单元格参与到样式继承（如所述），但控件的和属性返回的对象 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> <xref:System.Windows.Forms.DataGridView> 具有初始属性值，这些值将重写属性返回的对象的属性值 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 。 如果要将属性返回的对象的属性设置 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 为应用于行标题和列标题，则必须将和属性返回的对象的相应属性设置为为 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 类指定的默认值 <xref:System.Windows.Forms.DataGridViewCellStyle> 。  
  
> [!NOTE]
> 如果启用了视觉样式，则除) 之外的行标题和列标题 (<xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A> 会自动按当前主题样式进行样式，并覆盖这些属性指定的任何样式。  
  
 <xref:System.Windows.Forms.DataGridViewButtonColumn>、 <xref:System.Windows.Forms.DataGridViewImageColumn> 和 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> 类型还初始化由列属性返回的对象的某些值 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 。 有关详细信息，请参阅这些类型的参考文档。  
  
## <a name="setting-styles-dynamically"></a>动态设置样式  
 若要自定义具有特定值的单元格样式，请实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 。 此事件的处理程序接收类型的参数 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> 。 此对象包含一些属性，这些属性使你可以确定要设置格式的单元格的值及其在控件中的位置 <xref:System.Windows.Forms.DataGridView> 。 此对象还包含一个 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> 属性，该属性被初始化为 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 正在格式化的单元格的属性值。 您可以修改单元样式属性以指定适合单元值和位置的样式信息。  
  
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView.RowPrePaint>和 <xref:System.Windows.Forms.DataGridView.RowPostPaint> 事件也会接收到 <xref:System.Windows.Forms.DataGridViewCellStyle> 事件数据中的对象，但在这种情况下，它是行属性的副本 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> 以进行只读的，并且不会影响控件。  
  
 您还可以动态修改各个单元格的样式，以响应和事件之类的 <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> 事件 <xref:System.Windows.Forms.DataGridView.CellMouseLeave> 。 例如，在事件处理程序中 <xref:System.Windows.Forms.DataGridView.CellMouseEnter> ，您可以将单元格背景色 (的当前值存储 <xref:System.Windows.Forms.DataGridViewCell.Style%2A>) ，并将其设置为新的颜色，当鼠标悬停在该单元格上时，将突出显示该单元格。 在事件的处理程序中 <xref:System.Windows.Forms.DataGridView.CellMouseLeave> ，您可以将背景色还原为原始值。  
  
> [!NOTE]
> 不管是否设置了某个特定样式值，缓存存储在单元格中的值 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 都非常重要。 如果你暂时替换某个样式设置，则将其还原到其原始 "未设置" 状态可确保单元格返回到从较高级别继承样式设置。 如果需要确定单元的实际有效样式，而不管样式是否继承，请使用单元格的 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 属性。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [Windows 窗体 DataGridView 控件中的基本格式设置和样式设置](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的数据格式设置](data-formatting-in-the-windows-forms-datagridview-control.md)
