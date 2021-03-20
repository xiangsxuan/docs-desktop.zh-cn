---
title: 在 WPF 中承载 Windows 窗体复合控件
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: 0df41af90957a041554f63bd66e5c86757b11dee
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665183"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>演练：在 WPF 中托管 Windows 窗体复合控件

[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 提供了用于创建应用程序的丰富环境。 但是，当你对 Windows 窗体代码有大量投资时，在应用程序中重复使用至少一些代码， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 而不是从头重新编写它会更有效。 最常见的情况是现有 Windows 窗体控件。 在某些情况下，你甚至可能无法使用这些控件的源代码。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供在应用程序中承载此类控件的简单过程 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 例如，你可以将 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 用于大多数编程，同时承载专用 <xref:System.Windows.Forms.DataGridView> 控件。  
  
 本演练将指导你完成承载 Windows 窗体复合控件以在应用程序中执行数据输入的应用程序 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 复合控件打包在一个 DLL 中。 此常规步骤可扩展到更复杂的应用程序和控件。 本演练的设计与演练的外观和功能几乎完全相同 [：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)。 主要区别在于承载方案是相反的。  
  
 本演练分为两个部分。 第一部分简要介绍 Windows 窗体复合控件的实现。 第二部分详细讨论如何在应用程序中承载复合控件 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 、从控件接收事件以及访问控件的某些属性。  
  
 本演练涉及以下任务：  
  
- 实现 Windows 窗体复合控件。  
  
- 实现 WPF 主机应用程序。  
  
 有关本演练中阐释的任务的完整代码列表，请参阅 [在 WPF 中承载 Windows 窗体复合控件示例](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF)。  
  
## <a name="prerequisites"></a>必备条件  

若要完成本演练，必须具有 Visual Studio。
  
## <a name="implementing-the-windows-forms-composite-control"></a>实现 Windows 窗体复合控件  

 本示例中使用的 Windows 窗体复合控件是一个简单的数据输入窗体。 此窗体需要用户名和地址，然后使用自定义事件将该信息返回到主机。 下图显示呈现的控件。  

 下图显示了一个 Windows 窗体复合控件：  

 ![显示简单 Windows 窗体控件的屏幕截图。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a>创建项目  

 启动项目：  
  
1. 启动 Visual Studio，然后打开 " **新建项目** " 对话框。  
  
2. 在 "窗口" 类别中，选择 " **Windows 窗体控件库** " 模板。  
  
3. 将新项目命名为 `MyControls`。  
  
4. 对于 "位置"，指定一个便于命名的顶层文件夹，例如 `WpfHostingWindowsFormsControl` 。 随后，将主机应用程序放在此文件夹中。  
  
5. 单击“确定”以创建该项目  。 默认项目包含一个名为的控件 `UserControl1` 。  
  
6. 在解决方案资源管理器中， `UserControl1` 将重命名为 `MyControl1` 。  
  
 项目应具有对以下系统 DLL 的引用。 如果默认不包含其中任何 DLL，则将它们添加到项目中。  
  
- System  
  
- System.Data  
  
- System.Drawing  
  
- System.Windows.Forms  
  
- System.Xml  
  
### <a name="adding-controls-to-the-form"></a>将控件添加到窗体  

 向窗体添加控件：  
  
- `MyControl1`在设计器中打开。  
  
 在 <xref:System.Windows.Forms.Label> 窗体上，添加五个控件及其相应 <xref:System.Windows.Forms.TextBox> 的控件，并将其调整大小并按上图所示进行排列。 在此示例中， <xref:System.Windows.Forms.TextBox> 控件的名称为：  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 添加 <xref:System.Windows.Forms.Button> 标记为 **"确定" 和 "** **取消**" 的两个控件。 在此示例中，按钮名称 `btnOK` 分别为和 `btnCancel` 。  
  
### <a name="implementing-the-supporting-code"></a>实现支持代码  

 在代码视图中打开窗体。 控件通过引发自定义事件将收集的数据返回到其主机 `OnButtonClick` 。 数据包含在事件自变量对象中。 以下代码演示事件和委托声明。  
  
 将以下代码添加到 `MyControl1` 类。  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 `MyControlEventArgs`类包含要返回给主机的信息。

 将以下类添加到窗体中。

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 当用户单击 **"确定" 或 "** **取消** " 按钮时， <xref:System.Windows.Forms.Control.Click> 事件处理程序创建一个 `MyControlEventArgs` 包含数据的对象，并引发 `OnButtonClick` 事件。 这两个处理程序的唯一区别在于事件参数的 `IsOK` 属性。 此属性使主机可以确定单击的按钮。 对于 " `true` **确定"** 按钮，将设置为， `false` 为 " **取消** " 按钮设置。 以下代码演示两个按钮处理程序。

 将以下代码添加到 `MyControl1` 类。

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>赋予程序集强名称并生成程序集

 对于应用程序要引用此程序集 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，该程序集必须具有强名称。 若要创建强名称，请使用 Sn.exe 创建密钥文件并将其添加到你的项目中。

1. 打开 Visual Studio 命令提示。 为此，请单击 " **开始** " 菜单，然后选择 " **所有程序/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio 命令提示**"。 这将启动包含自定义环境变量的控制台窗口。

2. 在命令提示符下，使用 `cd` 命令来打开项目文件夹。

3. 通过运行以下命令生成名为 MyControls.snk 的密钥文件。

    ```console
    Sn.exe -k MyControls.snk
    ```

4. 若要在项目中包含密钥文件，请在解决方案资源管理器中右键单击项目名称，然后单击 " **属性**"。 在 "项目设计器" 中，单击 " **签名** " 选项卡，选中 "为 **程序集签名** " 复选框，然后浏览到密钥文件。

5. 生成解决方案。 生成将产生一个名为 MyControls.dll 的 DLL。

## <a name="implementing-the-wpf-host-application"></a>实现 WPF 主机应用程序

 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]宿主应用程序使用 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件进行宿主 `MyControl1` 。 应用程序处理 `OnButtonClick` 事件以接收来自控件的数据。 它还包含一个选项按钮集合，使你能够从应用程序更改控件的某些属性 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 下图显示已完成的应用程序。

下图显示了完整的应用程序，包括嵌入在 WPF 应用程序中的控件：

 ![显示嵌入在 WPF 页中的控件的屏幕截图。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a>创建项目

 启动项目：

1. 打开 Visual Studio，然后选择 " **新建项目**"。

2. 在 "窗口" 类别中，选择 " **WPF 应用程序** " 模板。

3. 将新项目命名为 `WpfHost`。

4. 对于位置，指定包含 MyControls 项目的同一顶层文件夹。

5. 单击“确定”以创建该项目  。

 还需要添加对包含 `MyControl1` 和其他程序集的 DLL 的引用。

1. 在解决方案资源管理器中右键单击项目名称，然后选择 " **添加引用**"。

2. 单击 " **浏览** " 选项卡，然后浏览到包含 MyControls.dll 的文件夹。 在本演练中，此文件夹位于 MyControls\bin\Debug。

3. 选择 "MyControls.dll"，然后单击 **"确定"**。

4. 添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration.dll。

### <a name="implementing-the-basic-layout"></a>实现基本布局

 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)]主机应用程序的是在 mainwindow.xaml 中实现的。 此文件包含 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 用于定义布局的标记，并承载 Windows 窗体控件。 该应用程序分为三个区域：

- " **控件属性** " 面板，其中包含选项按钮的集合，您可以使用这些按钮来修改所承载控件的各种属性。

- " **控制面板** " 中的数据，其中包含多个 <xref:System.Windows.Controls.TextBlock> 显示从寄宿控件返回的数据的元素。

- 所承载控件本身。

 基本布局如下面的 XAML 中所示。 在此示例中省略了主机需要的标记 `MyControl1` ，稍后将对此进行讨论。

 将 MainWindow.xaml 中的 XAML 替换为以下内容。 如果使用 Visual Basic，请将类更改为 `x:Class="MainWindow"` 。

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 第一个 <xref:System.Windows.Controls.StackPanel> 元素包含多组 <xref:System.Windows.Controls.RadioButton> 控件，这些控件可用于修改所承载控件的各种默认属性。 后跟一个承载的 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素 `MyControl1` 。 最后一个 <xref:System.Windows.Controls.StackPanel> 元素包含多个 <xref:System.Windows.Controls.TextBlock> 元素，这些元素显示由寄宿控件返回的数据。 元素的顺序以及 <xref:System.Windows.Controls.DockPanel.Dock%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A> 特性设置将承载的控件嵌入窗口中，而不会出现空白或失真。

#### <a name="hosting-the-control"></a>承载控件

 下面的 XAML 的编辑版本重点介绍承载所需的元素 `MyControl1` 。

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 `xmlns`命名空间映射特性创建对 `MyControls` 包含所承载控件的命名空间的引用。 通过此映射，你可以将 `MyControl1` 中的表示 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 为 `<mcl:MyControl1>` 。

 XAML 中的两个元素处理承载：

- `WindowsFormsHost` 表示 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 一个元素，该元素使您能够在应用程序中承载 Windows 窗体控件 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。

- `mcl:MyControl1`，它表示 `MyControl1` 将添加到 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的子集合。 因此，此 Windows 窗体控件将呈现为窗口的一部分 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，您可以从应用程序与控件进行通信。

### <a name="implementing-the-code-behind-file"></a>实现代码隐藏文件

 代码隐藏文件（Mainwindow.xaml 或 Mainwindow.xaml）包含实现上一部分所述的功能的过程代码，该代码可实现 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 。 主要任务有：

- 将事件处理程序附加到 `MyControl1` 的 `OnButtonClick` 事件。

- `MyControl1`根据设置选项按钮集合的方式修改的各种属性。

- 显示控件收集的数据。

#### <a name="initializing-the-application"></a>初始化应用程序

 初始化代码包含在窗口事件的事件处理程序中 <xref:System.Windows.FrameworkElement.Loaded> ，并将事件处理程序附加到控件的 `OnButtonClick` 事件。

 在 Mainwindow.xaml 或 Mainwindow.xaml 中，将以下代码添加到 `MainWindow` 类。

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 由于前面所述的是在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] `MyControl1` <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的子元素集合中添加的，因此可以强制转换该 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素，以获取对的 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> 引用 `MyControl1` 。 然后，可以使用该引用将事件处理程序附加到 `OnButtonClick` 。

 除了提供对控件本身的引用外，还 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 公开了许多控件属性，您可以从应用程序中操作。 初始化代码将这些值分配给私有全局变量，以供稍后在应用程序中使用。

 为了能够轻松地访问 DLL 中的类型 `MyControls` ，请将以下 `Imports` 或语句添加 `using` 到文件的顶部。

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a>处理 OnButtonClick 事件

 `MyControl1``OnButtonClick`当用户单击控件的任一按钮时，引发事件。

 将以下代码添加到 `MainWindow` 类。

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 文本框中的数据将打包到 `MyControlEventArgs` 对象中。 如果用户单击 **"确定"** 按钮，事件处理程序将提取数据并将其显示在下面的面板中 `MyControl1` 。

#### <a name="modifying-the-controls-properties"></a>修改控件属性

 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素公开几个托管控件的默认属性。 因此，可以更改空间外观，以更贴合应用程序的样式。 位于左侧面板中的选项按钮组使用户能够修改多个颜色和字体属性。 每组按钮都具有事件的处理程序 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> ，该处理程序检测用户的选项按钮选择并更改控件上的相应属性。

 将以下代码添加到 `MainWindow` 类。

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 生成并运行应用程序。 在 Windows 窗体复合控件中添加一些文本，然后单击 **"确定"**。 文本将显示在标签中。 单击不同的单选按钮查看在控件上的效果。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [演练：在 WPF 中承载 Windows 窗体控件](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [演练：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
