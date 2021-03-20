---
title: 演练：在混合应用程序中绑定到数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: 4da9cd950564a5349cb7881c1f25d518e712fb1e
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667247"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>演练：在混合应用程序中绑定到数据

无论你使用 Windows 窗体还是，将数据源绑定到控件对于向用户提供对基础数据的访问至关重要。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 本演练演示如何在包含 Windows 窗体和控件的混合应用程序中使用数据绑定 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。

本演练涉及以下任务：

- 创建项目。

- 定义数据模板。

- 指定窗体布局。

- 指定数据绑定。

- 使用互操作功能显示数据。

- 向项目添加数据源。

- 绑定到数据源。

有关本演练中所述任务的完整代码列表，请参阅 [混合应用程序中的数据绑定示例](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFWithWFAndDatabinding)。

完成本演练后，你将对混合应用程序中的数据绑定功能有所了解。

## <a name="prerequisites"></a>先决条件

您需要满足以下条件才能完成本演练：

- Visual Studio。

- 访问 Microsoft SQL Server 上运行的 Northwind 示例数据库。

## <a name="creating-the-project"></a>创建项目

### <a name="to-create-and-set-up-the-project"></a>创建并设置项目

1. 创建一个名为的 WPF 应用程序项目 `WPFWithWFAndDatabinding` 。

2. 在解决方案资源管理器中，添加对下列程序集的引用。

    - WindowsFormsIntegration

    - System.Windows.Forms

3. 在 WPF 设计器中打开 Mainwindow.xaml。

4. 在 <xref:System.Windows.Window> 元素中，添加以下 Windows 窗体命名空间映射。

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <xref:System.Windows.Controls.Grid> `mainGrid` 通过分配属性来命名默认元素 <xref:System.Windows.FrameworkElement.Name%2A> 。

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a>定义数据模板

客户的主列表显示在 <xref:System.Windows.Controls.ListBox> 控件中。 下面的代码示例定义一个 <xref:System.Windows.DataTemplate> 名为 `ListItemsTemplate` 的对象，该对象控制控件的可视化树 <xref:System.Windows.Controls.ListBox> 。 这 <xref:System.Windows.DataTemplate> 会分配给 <xref:System.Windows.Controls.ListBox> 控件的 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 属性。

### <a name="to-define-the-data-template"></a>定义数据模板

- 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素的声明中。

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a>指定窗体布局

窗体的布局由一个三行三列的网格来定义。 <xref:System.Windows.Controls.Label> 提供了用于标识 Customers 表中每一列的控件。

### <a name="to-set-up-the-grid-layout"></a>设置网格布局

- 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素的声明中。

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a>设置 Label 控件

- 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素的声明中。

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a>指定数据绑定

客户的主列表显示在 <xref:System.Windows.Controls.ListBox> 控件中。 附加的将 `ListItemsTemplate` <xref:System.Windows.Controls.TextBlock> 控件绑定到 `ContactName` 数据库中的字段。

每个客户记录的详细信息显示在多个 <xref:System.Windows.Controls.TextBox> 控件中。

### <a name="to-specify-data-bindings"></a>指定数据绑定

- 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素的声明中。

     <xref:System.Windows.Data.Binding>类将这些 <xref:System.Windows.Controls.TextBox> 控件绑定到数据库中的相应字段。

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a>使用互操作功能显示数据

对应于所选客户的订单将显示在一个 <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> 名为的控件中 `dataGridView1` 。 `dataGridView1`控件绑定到代码隐藏文件中的数据源。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>控件是此 Windows 窗体控件的父级。

### <a name="to-display-data-in-the-datagridview-control"></a>在 DataGridView 控件中显示数据

- 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素的声明中。

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a>向项目添加数据源

使用 Visual Studio，可以轻松地将数据源添加到项目。 此过程将向项目添加强类型数据集。 还添加了其他支持类，例如每个所选表适用的表适配器。

### <a name="to-add-the-data-source"></a>添加数据源

1. 从 " **数据** " 菜单中，选择 " **添加新数据源**"。

2. 在 " **数据源配置向导**" 中，使用数据集创建到 Northwind 数据库的连接。 有关详细信息，请参阅 [How to: Connect to Data in a Database](/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))。

3. 当您通过 " **数据源配置向导**" 提示您时，请将连接字符串保存为 `NorthwindConnectionString` 。

4. 当系统提示您选择数据库对象时，选择 `Customers` 和 `Orders` 表，并将生成的数据集命名为 `NorthwindDataSet` 。

## <a name="binding-to-the-data-source"></a>绑定到数据源

<xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>组件提供应用程序数据源的统一接口。 绑定到数据源是在代码隐藏文件中实现的。

### <a name="to-bind-to-the-data-source"></a>绑定到数据源

1. 打开名为 MainWindow.xaml.vb 或 MainWindow.xaml.cs 的代码隐藏文件。

2. 将以下代码复制到 `MainWindow` 类定义中。

     此代码声明 <xref:System.Windows.Forms.BindingSource> 连接到数据库的组件和关联的帮助器类。

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. 将以下代码复制到构造函数中。

     此代码将创建并初始化该 <xref:System.Windows.Forms.BindingSource> 组件。

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. 打开 MainWindow.xaml。

5. 在设计视图或 XAML 视图中，选择 <xref:System.Windows.Window> 元素。

6. 在属性窗口中，单击 " **事件** " 选项卡。

7. 双击该 <xref:System.Windows.FrameworkElement.Loaded> 事件。

8. 将以下代码复制到 <xref:System.Windows.FrameworkElement.Loaded> 事件处理程序中。

     此代码会将 <xref:System.Windows.Forms.BindingSource> 组件分配为数据上下文，并填充 `Customers` 和 `Orders` 适配器对象。

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. 将以下代码复制到 `MainWindow` 类定义中。

     此方法处理 <xref:System.Windows.Data.CollectionView.CurrentChanged> 事件并更新数据绑定的当前项。

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. 按 F5 生成并运行应用程序。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [混合应用程序中的数据绑定示例](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFWithWFAndDatabinding)
- [演练：在 WPF 中托管 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [演练：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
