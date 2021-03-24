---
title: 在 Windows 窗体中承载 WPF 复合控件
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
ms.openlocfilehash: b0663dbf361502ab803b5f6ff16bc697decabbf4
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "105026698"
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>演练：在 Windows 窗体中承载 WPF 复合控件
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 提供了用于创建应用程序的丰富环境。 但是，当您对 Windows 窗体代码做了大量投资时，使用来扩展现有 Windows 窗体应用程序会更有效， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 而不是从头重新编写。 常见的一种情况是，当你想要在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Windows 窗体应用程序中嵌入一个或多个实现的控件。 有关自定义 WPF 控件的详细信息，请参阅 [控件自定义](../controls/control-customization.md)。  
  
 本演练将指导你完成承载 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 复合控件以在 Windows 窗体应用程序中执行数据输入的应用程序。 复合控件打包在一个 DLL 中。 此常规步骤可扩展到更复杂的应用程序和控件。 本演练的设计与演练的外观和功能几乎完全相同 [：在 WPF 中承载 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)。 主要区别在于承载方案是相反的。  
  
 本演练分为两个部分。 第一部分简要介绍了复合控件的实现 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 第二部分详细讨论如何在 Windows 窗体应用程序中承载复合控件、从控件接收事件以及访问控件的某些属性。  
  
 本演练涉及以下任务：  
  
- 实现 WPF 复合控件。  
  
- 实现 Windows 窗体主机应用程序。  
  
 有关本演练中阐释的任务的完整代码列表，请参阅 [在 Windows 窗体示例中承载 WPF 复合控件](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WindowsFormsHostingWpfControl)。  
  
## <a name="prerequisites"></a>先决条件  

若要完成本演练，必须具有 Visual Studio。  
  
## <a name="implementing-the-wpf-composite-control"></a>实现 WPF 复合控件  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]本示例中使用的复合控件是一个简单的数据输入窗体，该窗体采用用户的名称和地址。 当用户单击两个按钮的其中一个以指示任务已完成时，该控件会引发将该信息返回给主机的自定义事件。 下图显示呈现的控件。

 下图显示了一个 WPF 复合控件：

 ![显示一个简单的 WPF 控件的屏幕截图。](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-presentation-foundation-composite-control.png)  
  
### <a name="creating-the-project"></a>创建项目  
 启动项目：  
  
1. 启动 Visual Studio，然后打开 " **新建项目** " 对话框。  
  
2. 在 Visual c # 和 Windows 类别中，选择 " **WPF 用户控件库** " 模板。  
  
3. 将新项目命名为 `MyControls`。  
  
4. 对于 "位置"，指定一个便于命名的顶层文件夹，例如 `WindowsFormsHostingWpfControl` 。 随后，将主机应用程序放在此文件夹中。  
  
5. 单击“确定”以创建该项目  。 默认项目包含一个名为的控件 `UserControl1` 。  
  
6. 在解决方案资源管理器中， `UserControl1` 将重命名为 `MyControl1` 。  
  
 项目应具有对以下系统 DLL 的引用。 如果默认未包含其中任何 DLL，请将它们添加到项目中。  
  
- PresentationCore  
  
- PresentationFramework  
  
- System  
  
- WindowsBase  
  
### <a name="creating-the-user-interface"></a>创建用户界面  
 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)]复合控件的通过实现 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。 复合控件 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 由五个 <xref:System.Windows.Controls.TextBox> 元素组成。 每个 <xref:System.Windows.Controls.TextBox> 元素都有一个 <xref:System.Windows.Controls.TextBlock> 作为标签的关联的元素。 底部有两个 <xref:System.Windows.Controls.Button> 元素： **"确定" 和 "** **取消**"。 当用户单击任一按钮时，该控件会引发将信息返回给主机的自定义事件。  
  
#### <a name="basic-layout"></a>基本布局  
 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]元素中包含各种元素 <xref:System.Windows.Controls.Grid> 。 您可以使用 <xref:System.Windows.Controls.Grid> 来排列复合控件的内容，其方式与在 HTML 中使用元素的方式大致相同 `Table` 。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 还有一个 <xref:System.Windows.Documents.Table> 元素，但 <xref:System.Windows.Controls.Grid> 更轻量，更适合简单的布局任务。  
  
 以下 XAML 演示基本布局。 此 XAML 通过指定元素中的列数和行数来定义控件的整体结构 <xref:System.Windows.Controls.Grid> 。  
  
 在 MyControl1.xaml 中，将现有 XAML 替换为以下 XAML。  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>向 Grid 添加 TextBlock 和 TextBox 元素  
 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]通过将元素的 <xref:System.Windows.Controls.Grid.RowProperty> 和 <xref:System.Windows.Controls.Grid.ColumnProperty> 属性设置为相应的行号和列号，可以在网格中放置一个元素。 请记住行号和列号是从零开始的。 通过设置元素的属性，可以使元素跨多个列 <xref:System.Windows.Controls.Grid.ColumnSpanProperty> 。 有关元素的详细信息 <xref:System.Windows.Controls.Grid> ，请参阅 [创建网格元素](../controls/how-to-create-a-grid-element.md)。  
  
 下面的 XAML 演示了组合控件的 <xref:System.Windows.Controls.TextBox> 和 <xref:System.Windows.Controls.TextBlock> 元素及其 <xref:System.Windows.Controls.Grid.RowProperty> 和 <xref:System.Windows.Controls.Grid.ColumnProperty> 特性，它们设置为在网格中正确放置元素。  
  
 在 Mycontrol1.xaml 中，将以下 XAML 添加到元素中 <xref:System.Windows.Controls.Grid> 。  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>设置 UI 元素的样式  
 数据输入窗体上的许多元素外观相似，这意味着它们对于其若干属性具有相同的设置。 以前的 XAML 使用 <xref:System.Windows.Style> 元素来定义元素类的标准属性设置，而不是单独设置每个元素的属性。 这种方法可以降低控件的复杂性，并使你能够通过单个样式特性更改多个元素的外观。  
  
 <xref:System.Windows.Style>元素包含在 <xref:System.Windows.Controls.Grid> 元素的 <xref:System.Windows.FrameworkElement.Resources%2A> 属性中，因此控件中的所有元素都可以使用这些元素。 如果样式命名为，则通过将 <xref:System.Windows.Style> 元素集添加到样式的名称，将其应用于元素。 未命名的样式将成为该元素的默认样式。 有关样式的详细信息 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，请参阅样式 [设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)。  
  
 以下 XAML 显示了 <xref:System.Windows.Style> 复合控件的元素。 若要查看样式如何应用于元素，请参阅前一个 XAML。 例如，最后一个 <xref:System.Windows.Controls.TextBlock> 元素具有 `inlineText` 样式，最后一个 <xref:System.Windows.Controls.TextBox> 元素使用默认样式。  
  
 在 Mycontrol1.xaml 中，将以下 XAML 添加到 <xref:System.Windows.Controls.Grid> start 元素之后。  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>添加“确定”和“取消”按钮  
 复合控件上的最后一个元素是 **OK** 和 **Cancel** <xref:System.Windows.Controls.Button> 元素，它们占用最后一行的前两列 <xref:System.Windows.Controls.Grid> 。 这些元素使用公共事件处理程序、 `ButtonClicked` 和 <xref:System.Windows.Controls.Button> 在前面的 XAML 中定义的默认样式。  
  
 在 Mycontrol1.xaml 中，将以下 XAML 添加到最后一个 <xref:System.Windows.Controls.TextBox> 元素之后。 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]复合控件的部分现已完成。  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>实现代码隐藏文件  
 代码隐藏文件 Mycontrol1.xaml 实现了三个重要任务：
  
1. 处理用户单击其中一个按钮时发生的事件。  
  
2. 从元素中检索数据 <xref:System.Windows.Controls.TextBox> ，并将其打包到一个自定义事件参数对象中。  
  
3. 引发自定义 `OnButtonClick` 事件，该事件通知宿主用户已完成，并将数据传递回主机。  
  
 该控件还公开多个可用来更改外观的颜色和字体属性。 与 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 用于承载 Windows 窗体控件的类不同， <xref:System.Windows.Forms.Integration.ElementHost> 类只公开控件的 <xref:System.Windows.Controls.Panel.Background%2A> 属性。 为了保持此代码示例与 [演练：在 WPF 中承载 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)中讨论的示例之间的相似性，控件直接公开了其余属性。  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>代码隐藏文件的基本结构  
 代码隐藏文件包含一个命名空间，该命名空间 `MyControls` 将包含两个类 `MyControl1` 和 `MyControlEventArgs` 。  
  
```csharp  
namespace MyControls  
{  
  public partial class MyControl1 : Grid  
  {  
    //...  
  }  
  public class MyControlEventArgs : EventArgs  
  {  
    //...  
  }  
}  
```  
  
 第一个类 `MyControl1` 是分部类，它包含实现 mycontrol1.xaml 中定义的功能的代码 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 。 分析 Mycontrol1.xaml 时，会将转换为 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 同一个分部类，并合并两个分部类，以形成编译的控件。 出于此原因，代码隐藏文件中的类名必须与分配给 MyControl1.xaml 的类名相匹配，并且它必须继承自控件的根元素。 第二个类 `MyControlEventArgs` 是一个事件参数类，用于将数据发送回主机。  
  
 打开 MyControl1.xaml.cs。 更改现有的类声明，使其具有以下名称并继承自 <xref:System.Windows.Controls.Grid> 。  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>初始化控件  
 下面的代码实现几个基本任务：  
  
- 声明一个私有事件 `OnButtonClick` 及其关联的委托 `MyControlEventHandler` 。  
  
- 创建几个存储用户数据的私有全局变量。 此数据通过相应的属性公开。  
  
- `Init`为控件的事件实现处理程序 <xref:System.Windows.FrameworkElement.Loaded> 。 此处理程序通过向全局变量分配 MyControl1.xaml 中定义的值来对它们进行初始化。 为此，它使用 <xref:System.Windows.FrameworkElement.Name%2A> 分配给典型的元素来 <xref:System.Windows.Controls.TextBlock> `nameLabel` 访问该元素的属性设置。  
  
 删除现有构造函数并将以下代码添加到你的 `MyControl1` 类。  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>处理按钮的单击事件  
 用户通过单击 **"确定"** 按钮或 " **取消** " 按钮来指示数据输入任务已完成。 这两个按钮都使用同一 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件处理程序 `ButtonClicked` 。 这两个按钮都有名称 `btnOK` 或 `btnCancel` ，这使处理程序能够通过检查参数的值来确定单击了哪个按钮 `sender` 。 该处理程序执行以下任务：  
  
- 创建一个 `MyControlEventArgs` 对象，该对象包含元素中的数据 <xref:System.Windows.Controls.TextBox> 。  
  
- 如果用户单击 " **取消** " 按钮，则将 `MyControlEventArgs` 对象的 `IsOK` 属性设置为 `false` 。  
  
- 引发 `OnButtonClick` 事件以向宿主指示用户已完成，并传递回收集的数据。  
  
 在 `MyControl1` 方法后面的类中添加以下代码 `Init` 。  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>创建属性  
 类的其余部分只是公开对应于前面所述的全局变量的属性。 当属性更改时，set 访问器会通过更改对应的元素属性并更新基础全局变量来修改控件的外观。  
  
 将以下代码添加到你的 `MyControl1` 类。  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>将数据发送回主机  
 文件中的最后一个组件是 `MyControlEventArgs` 类，该类用于将收集的数据发送回主机。  
  
 将以下代码添加到 `MyControls` 命名空间。 该实现非常简单明了，因而不再进一步讨论。  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 生成解决方案。 生成将产生一个名为 MyControls.dll 的 DLL。  
  
<a name="winforms_host_section"></a>
## <a name="implementing-the-windows-forms-host-application"></a>实现 Windows 窗体主机应用程序  
 Windows 窗体主机应用程序使用 <xref:System.Windows.Forms.Integration.ElementHost> 对象承载 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 复合控件。 应用程序处理 `OnButtonClick` 事件以从复合控件接收数据。 应用程序还具有一组选项按钮，可用于修改控件的外观。 下图显示应用程序。  

下图显示了在 Windows 窗体应用程序中承载的 WPF 复合控件

 ![显示托管 Avalon 控件的 Windows 窗体的屏幕截图。](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-form-hosting-avalon-control.png)  
  
### <a name="creating-the-project"></a>创建项目  
 启动项目：  
  
1. 启动 Visual Studio，然后打开 " **新建项目** " 对话框。  
  
2. 在 Visual c # 和 Windows 类别中，选择 " **Windows 窗体应用程序** 模板。  
  
3. 将新项目命名为 `WFHost`。  
  
4. 对于位置，指定包含 MyControls 项目的同一顶层文件夹。  
  
5. 单击“确定”以创建该项目  。  
  
 还需要添加对包含 `MyControl1` 和其他程序集的 DLL 的引用。  
  
1. 在解决方案资源管理器中右键单击项目名称，然后选择 " **添加引用**"。  
  
2. 单击 " **浏览** " 选项卡，然后浏览到包含 MyControls.dll 的文件夹。 在本演练中，此文件夹位于 MyControls\bin\Debug。  
  
3. 选择 "MyControls.dll"，然后单击 **"确定"**。  
  
4. 添加对下列程序集的引用。  
  
    - PresentationCore  
  
    - PresentationFramework  
  
    - System.Xaml  
  
    - WindowsBase  
  
    - WindowsFormsIntegration  
  
### <a name="implementing-the-user-interface-for-the-application"></a>实现应用程序的用户界面  
 Windows 窗体应用程序的 UI 包含若干个与 WPF 复合控件进行交互的控件。  
  
1. 在 Windows 窗体设计器中打开 Form1。  
  
2. 放大窗体以适应控件。  
  
3. 在窗体的右上角，添加一个 <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> 控件来容纳 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 复合控件。  
  
4. 将以下 <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> 控件添加到窗体。  
  
    |名称|文本|  
    |----------|----------|  
    |groupBox1|背景色|  
    |groupBox2|前景色|  
    |groupBox3|字号|  
    |groupBox4|字体系列|  
    |groupBox5|字形|  
    |groupBox6|字体粗细|  
    |groupBox7|来自控件的数据|  
  
5. 将以下 <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> 控件添加到 <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> 控件。  
  
    |GroupBox|名称|文本|  
    |--------------|----------|----------|  
    |groupBox1|radioBackgroundOriginal|原始|  
    |groupBox1|radioBackgroundLightGreen|LightGreen|  
    |groupBox1|radioBackgroundLightSalmon|LightSalmon|  
    |groupBox2|radioForegroundOriginal|原始|  
    |groupBox2|radioForegroundRed|Red|  
    |groupBox2|radioForegroundYellow|Yellow|  
    |groupBox3|radioSizeOriginal|原始|  
    |groupBox3|radioSizeTen|10|  
    |groupBox3|radioSizeTwelve|12|  
    |groupBox4|radioFamilyOriginal|原始|  
    |groupBox4|radioFamilyTimes|Times New Roman|  
    |groupBox4|radioFamilyWingDings|WingDings|  
    |groupBox5|radioStyleOriginal|普通|  
    |groupBox5|radioStyleItalic|斜体|  
    |groupBox6|radioWeightOriginal|原始|  
    |groupBox6|radioWeightBold|加粗|  
  
6. 将以下 <xref:System.Windows.Forms.Label?displayProperty=nameWithType> 控件添加到最后一个 <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> 。 这些控件显示复合控件返回的数据 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
    |GroupBox|名称|文本|  
    |--------------|----------|----------|  
    |groupBox7|lblName|姓名：|  
    |groupBox7|lblAddress|街道地址:|  
    |groupBox7|lblCity|市/县:|  
    |groupBox7|lblState|状态：|  
    |groupBox7|lblZip|邮政编码:|  
  
### <a name="initializing-the-form"></a>初始化窗体  
 通常在窗体的事件处理程序中实现宿主代码 <xref:System.Windows.Forms.Form.Load> 。 下面的代码显示了 <xref:System.Windows.Forms.Form.Load> 事件处理程序、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 复合控件的事件的处理程序， <xref:System.Windows.FrameworkElement.Loaded> 以及以后使用的多个全局变量的声明。  
  
 在 Windows 窗体设计器中，双击窗体以创建 <xref:System.Windows.Forms.Form.Load> 事件处理程序。 在 Form1 的顶部，添加以下 `using` 语句。  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 将现有类的内容替换 `Form1` 为以下代码。  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 `Form1_Load`上述代码中的方法显示了承载控件的一般过程 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ：  
  
1. 创建新 <xref:System.Windows.Forms.Integration.ElementHost> 对象。  
  
2. 将控件的 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType> 。  
  
3. 将 <xref:System.Windows.Forms.Integration.ElementHost> 控件添加到 <xref:System.Windows.Forms.Panel> 控件的 <xref:System.Windows.Forms.Control.Controls%2A> 集合。  
  
4. 创建控件的实例 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
5. 通过将控件分配到控件的属性，在窗体上承载复合控件 <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 。  
  
 方法中的其余两行 `Form1_Load` 将处理程序附加到两个控件事件：  
  
- `OnButtonClick` 自定义事件，当用户单击 **"确定" 或 "** **取消** " 按钮时，该事件由复合控件激发。 处理该事件可获取用户的响应并收集用户指定的任何数据。  
  
- <xref:System.Windows.FrameworkElement.Loaded> 是 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件完全加载后由控件引发的标准事件。 此处使用该事件是因为本示例需要使用控件中的属性初始化几个全局变量。 在窗体 <xref:System.Windows.Forms.Form.Load> 事件发生时，控件未完全加载，这些值仍设置为 `null` 。 需要等到控件的事件发生之后，才能 <xref:System.Windows.FrameworkElement.Loaded> 访问这些属性。  
  
 <xref:System.Windows.FrameworkElement.Loaded>事件处理程序显示在前面的代码中。 `OnButtonClick`下一节将讨论处理程序。  
  
### <a name="handling-onbuttonclick"></a>处理 OnButtonClick  
 `OnButtonClick`当用户单击 **"确定" 或 "** **取消**" 按钮时发生此事件。  
  
 事件处理程序检查事件参数的 `IsOK` 字段以确定单击了哪个按钮。 `lbl`*数据* 变量对应于 <xref:System.Windows.Forms.Label> 前面讨论过的控件。 如果用户单击 **"确定"** 按钮，则控件的控件中的数据将被 <xref:System.Windows.Controls.TextBox> 分配给相应的 <xref:System.Windows.Forms.Label> 控件。 如果用户单击 " **取消**"，则这些 <xref:System.Windows.Forms.Label.Text%2A> 值将设置为默认字符串。  
  
 将以下按钮单击事件处理程序代码添加到 `Form1` 类。  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 生成并运行应用程序。 在 WPF 复合控件中添加一些文本，然后单击 **"确定"**。 文本将显示在标签中。 此时，尚未添加代码来处理单选按钮。  
  
### <a name="modifying-the-appearance-of-the-control"></a>修改控件的外观  
 <xref:System.Windows.Forms.RadioButton>窗体上的控件将使用户能够更改 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 复合控件的前景色和背景色以及多个字体属性。 背景色由 <xref:System.Windows.Forms.Integration.ElementHost> 对象公开。 其余属性作为控件的自定义属性公开。  
  
 双击 <xref:System.Windows.Forms.RadioButton> 窗体上的每个控件以创建 <xref:System.Windows.Forms.RadioButton.CheckedChanged> 事件处理程序。 将 <xref:System.Windows.Forms.RadioButton.CheckedChanged> 事件处理程序替换为下面的代码。  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 生成并运行应用程序。 单击不同的单选按钮来查看在 WPF 复合控件上的效果。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [演练：在 WPF 中托管 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [演练：在 Windows 窗体中承载三维 WPF 复合控件](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
