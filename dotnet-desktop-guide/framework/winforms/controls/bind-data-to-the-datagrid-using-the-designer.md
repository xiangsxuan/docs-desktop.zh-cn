---
title: 使用设计器将数据绑定到 DataGridView 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
ms.openlocfilehash: 6a8ffdbf950eb0fcda7b4752e6e9dd73a6df3f6f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970719"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器将数据绑定到 Windows 窗体 DataGridView 控件

您可以使用设计器将控件连接 <xref:System.Windows.Forms.DataGridView> 到多种不同种类（包括数据库、业务对象或 Web 服务）的数据源。 使用设计器将控件绑定到数据源时，控件将自动绑定到 <xref:System.Windows.Forms.BindingSource> 表示数据源的组件。 此外，会在控件中自动生成列以匹配数据源提供的架构信息。

 生成列后，可根据需要对其进行修改。 例如，可删除或隐藏不不想显示的列、重新排列各列或修改列的类型。 有关修改列的详细信息，请参阅“另请参阅”部分中列出的主题。

 您还可以将多个 <xref:System.Windows.Forms.DataGridView> 控件绑定到相关表，以创建主/从关系。 在此配置中，一个控件显示父表，另一个控件只显示子表中与父表中的当前行相关的行。 有关详细信息，请参阅[如何：在 Windows 窗体应用程序中显示相关数据](/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))。

 下面的过程需要一个 **Windows 应用程序** 项目，该项目具有一个窗体，其中包含一个 <xref:System.Windows.Forms.DataGridView> 用于主/从关系的控件或两个控件。 有关启动此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

## <a name="to-bind-the-control-to-a-data-source"></a>将控件绑定到数据源

1. 单击 ![ ](./media/designer-actions-glyph.gif) 控件右上角) 的 "设计器操作" 标志符号 (小黑色箭头 <xref:System.Windows.Forms.DataGridView> 。

2. 单击“选择数据源”选项的下拉箭头。

3. 如果项目尚没有数据源，请单击“添加项目数据源”，按照向导指示的步骤进行操作。

     有关详细信息，请参阅[数据源配置向导](/previous-versions/visualstudio/visual-studio-2013/w4dd7z6t(v=vs.120))。 新数据源将显示在“选择数据源”下拉窗口中。 如果新数据源只包含一个成员（例如单个数据库表），控件将自动绑定到该成员。 否则，继续执行下一步。

4. 如果尚未展开，则展开“其他数据源”和“项目数据源”节点，然后选择绑定控件的数据源。

5. 如果您的数据源包含多个成员（例如，如果您创建了一个 <xref:System.Data.DataSet?displayProperty=nameWithType> 包含多个表的），则展开该数据源，然后选择要绑定到的特定成员。

6. 若要创建主/从关系，请在另一个控件的 " **选择数据源** " 下拉窗口中 <xref:System.Windows.Forms.DataGridView> ，展开 <xref:System.Windows.Forms.BindingSource> 为父表创建的，然后从显示的列表中选择相关的子表。

    > [!NOTE]
    > 如果项目已有数据源，还可以使用“数据源”窗口创建数据窗体。 有关详细信息，请参阅[数据源窗口](/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- [如何：连接到数据库中的数据](/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))
- [如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [如何：使用设计器更改 Windows 窗体 DataGridView 控件中列的顺序](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)
- [如何：使用设计器更改 Windows 窗体 DataGridView 列类型](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)
- [如何：使用设计器冻结 Windows 窗体 DataGridView 控件中的列](freeze-columns-in-the-datagrid-using-the-designer.md)
- [如何：使用设计器隐藏 Windows 窗体 DataGridView 控件中的列](hide-columns-in-the-datagrid-using-the-designer.md)
- [如何：使用设计器将 Windows 窗体 DataGridView 控件中的列设为只读](make-columns-read-only-in-the-datagrid-using-the-designer.md)
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
- [“数据源”窗口](/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
- [如何：在 Windows 窗体应用程序中显示相关数据](/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))
