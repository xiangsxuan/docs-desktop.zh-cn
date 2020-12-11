---
title: DataGridView 控件体系结构
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970129"
---
# <a name="datagridview-control-architecture-windows-forms"></a>DataGridView 控件体系结构（Windows 窗体）
<xref:System.Windows.Forms.DataGridView>控件及其相关的类设计为用于显示和编辑表格数据的灵活、可扩展的系统。 这些类都包含在 <xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间中，它们都是用 "DataGridView" 前缀命名的。  
  
## <a name="architecture-elements"></a>体系结构元素  
 主 <xref:System.Windows.Forms.DataGridView> 伴生类派生自 <xref:System.Windows.Forms.DataGridViewElement> 。 以下对象模型说明了 <xref:System.Windows.Forms.DataGridViewElement> 继承层次结构。  
  
 ![显示 DataGridViewElement 对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <xref:System.Windows.Forms.DataGridViewElement>类提供对父控件的引用 <xref:System.Windows.Forms.DataGridView> 并具有 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 属性，该属性包含一个值，该值表示枚举中的值的组合 <xref:System.Windows.Forms.DataGridViewElementStates> 。  
  
 以下部分 <xref:System.Windows.Forms.DataGridView> 更详细地介绍了伴生类。  
  
### <a name="datagridviewelementstates"></a>DataGridViewElementStates  
 <xref:System.Windows.Forms.DataGridViewElementStates> 枚举包含以下值：  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 此枚举的值可以与按位逻辑运算符组合在一起，因此 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 属性可以同时表示多个状态。 例如， <xref:System.Windows.Forms.DataGridViewElement> 可以同时为 <xref:System.Windows.Forms.DataGridViewElementStates.Frozen> 、 <xref:System.Windows.Forms.DataGridViewElementStates.Selected> 和 <xref:System.Windows.Forms.DataGridViewElementStates.Visible> 。  
  
### <a name="cells-and-bands"></a>单元和带区  
 <xref:System.Windows.Forms.DataGridView>控件包含两种基本类型的对象：单元格和带区。 所有单元均派生自 <xref:System.Windows.Forms.DataGridViewCell> 基类。 两种类型的带区 <xref:System.Windows.Forms.DataGridViewColumn> 和 <xref:System.Windows.Forms.DataGridViewRow> 都派生自 <xref:System.Windows.Forms.DataGridViewBand> 基类。  
  
 <xref:System.Windows.Forms.DataGridView>控件与多个类互操作，但最常遇到的是 <xref:System.Windows.Forms.DataGridViewCell> 、 <xref:System.Windows.Forms.DataGridViewColumn> 和 <xref:System.Windows.Forms.DataGridViewRow> 。  
  
### <a name="datagridviewcell"></a>DataGridViewCell  
 单元是的交互的基本单位 <xref:System.Windows.Forms.DataGridView> 。 显示在单元格中居中，数据输入通常通过单元格执行。 您可以通过使用类的集合来访问单元 <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> <xref:System.Windows.Forms.DataGridViewRow> ，您可以通过使用控件的集合来访问所选单元 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> <xref:System.Windows.Forms.DataGridView> 。 以下对象模型说明了这种用法，并显示了 <xref:System.Windows.Forms.DataGridViewCell> 继承层次结构。  
  
 ![显示 DataGridViewCell 对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <xref:System.Windows.Forms.DataGridViewCell>类型是一个抽象基类，所有单元类型都派生自该基类。 <xref:System.Windows.Forms.DataGridViewCell> 及其派生类型不 Windows 窗体控件，而某些宿主 Windows 窗体控件。 单元支持的所有编辑功能通常由寄宿控件处理。  
  
 <xref:System.Windows.Forms.DataGridViewCell> 对象不以与 Windows 窗体控件相同的方式来控制其自身的外观和绘制功能。 相反， <xref:System.Windows.Forms.DataGridView> 负责其对象的外观 <xref:System.Windows.Forms.DataGridViewCell> 。 通过与 <xref:System.Windows.Forms.DataGridView> 控件的属性和事件交互，可以显著影响单元格的外观和行为。 如果对超出控件功能的自定义项有特殊要求 <xref:System.Windows.Forms.DataGridView> ，则可以实现自己的派生自 <xref:System.Windows.Forms.DataGridViewCell> 或其子类之一的类。  
  
 以下列表显示派生自的类 <xref:System.Windows.Forms.DataGridViewCell> ：  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- 自定义单元类型  
  
### <a name="datagridviewcolumn"></a>DataGridViewColumn  
 <xref:System.Windows.Forms.DataGridView>控件的附加数据存储的架构在 <xref:System.Windows.Forms.DataGridView> 控件的列中表示。 您可以 <xref:System.Windows.Forms.DataGridView> 通过使用集合来访问控件的列 <xref:System.Windows.Forms.DataGridView.Columns%2A> 。 您可以通过使用集合来访问所选列 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 。 以下对象模型说明了这种用法，并显示了 <xref:System.Windows.Forms.DataGridViewColumn> 继承层次结构。  
  
 ![显示 DataGridViewColumn 对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 某些键单元类型具有相应的列类型。 这些类派生自 <xref:System.Windows.Forms.DataGridViewColumn> 基类。  
  
 以下列表显示派生自的类 <xref:System.Windows.Forms.DataGridViewColumn> ：  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- 自定义列类型  
  
### <a name="datagridview-editing-controls"></a>DataGridView 编辑控件  
 支持高级编辑功能的单元通常使用派生自 Windows 窗体控件的托管控件。 这些控件还实现 <xref:System.Windows.Forms.IDataGridViewEditingControl> 接口。 以下对象模型说明了这些控件的用法。  
  
 ![显示 DataGridView 编辑控件对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 以下编辑控件与控件一起提供 <xref:System.Windows.Forms.DataGridView> ：  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 有关创建自己的编辑控件的信息，请参阅 [如何：在 Windows 窗体 DataGridView 单元格中承载控件](how-to-host-controls-in-windows-forms-datagridview-cells.md)。  
  
 下表说明了单元类型、列类型和编辑控件之间的关系。  
  
|单元类型|托管控件|列类型|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|不适用|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|不适用|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|不适用|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|不适用|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a>DataGridViewRow  
 <xref:System.Windows.Forms.DataGridViewRow>类显示控件所附加到的数据存储区中的记录的数据字段 <xref:System.Windows.Forms.DataGridView> 。 您可以 <xref:System.Windows.Forms.DataGridView> 通过使用集合来访问控件的行 <xref:System.Windows.Forms.DataGridView.Rows%2A> 。 您可以通过使用集合来访问所选行 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 。 以下对象模型说明了这种用法，并显示了 <xref:System.Windows.Forms.DataGridViewRow> 继承层次结构。  
  
 ![显示 DataGridViewRow 对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 你可以从类派生你自己的类型 <xref:System.Windows.Forms.DataGridViewRow> ，但通常不需要这样做。 <xref:System.Windows.Forms.DataGridView>控件具有几个与行相关的事件和属性，用于自定义其 <xref:System.Windows.Forms.DataGridViewRow> 对象的行为。  
  
 如果启用 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 属性，则添加新行的特殊行将显示为最后一行。 该行是集合的一部分 <xref:System.Windows.Forms.DataGridView.Rows%2A> ，但它具有可能需要注意的特殊功能。 有关详细信息，请参阅在 [Windows 窗体 DataGridView 控件中使用新记录行](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>另请参阅

- [DataGridView 控件概述](datagridview-control-overview-windows-forms.md)
- [自定义 Windows 窗体 DataGridView 控件](customizing-the-windows-forms-datagridview-control.md)
- [在 Windows 窗体 DataGridView 控件中使用新记录行](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
