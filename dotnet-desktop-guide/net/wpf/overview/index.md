---
title: Windows Presentation Foundation 简介
description: 本文概述了 .NET Core 和 .NET 5 的 WPF。
ms.date: 01/14/2021
ms.topic: overview
dev_langs:
- csharp
- vb
ms.openlocfilehash: aec92678052453735ee3eaa0ff73eadf713a661a
ms.sourcegitcommit: 32616f61a7b001efcc8567fee5fdf01f83da76cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "107559976"
---
# <a name="desktop-guide-wpf-net"></a>桌面指南 (WPF .NET)

欢迎使用 Windows Presentation Foundation (WPF) 桌面指南，这是一个与分辨率无关的 UI 框架，使用基于矢量的呈现引擎，构建用于利用现代图形硬件。 WPF 提供一套完善的应用程序开发功能，这些功能包括 Extensible Application Markup Language (XAML)、控件、数据绑定、布局、二维和三维图形、动画、样式、模板、文档、媒体、文本和版式。 WPF 属于 .NET，因此可以生成整合 .NET API 其他元素的应用程序。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

WPF 有两种实现：

01. .Net 版本（本指南）：

    [GitHub](https://github.com/dotnet/wpf) 上托管的 WPF 开源实现，可在 .Net 5 或更高版本（包括 .Net Core 3.1）上运行。 适用于 XAML 设计器最低要求 [Visual Studio 2019 版本 16.8](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+wpf)。

    尽管 .NET 是一种跨平台技术，但 WPF 并不是，它仅在 Windows 上运行。

01. .NET Framework 4 版本：

    受 Visual Studio 2019 和 Visual Studio 2017 支持的 WPF 的 .NET Framework 实现。

    .NET Framework 4 是仅限 Windows 的 .NET 版本，被视为一个 Windows 操作系统组件。 此版本的 WPF 随 .NET Framework 一起分发。 有关 WPF 的 .NET Framework 版本的详细信息，请参阅[适用于 .NET Framework 的 WPF 简介](../../../framework/wpf/introduction-to-wpf.md?view=netframeworkdesktop-4.8&preserve-view=true)。

本概述适用于新用户，介绍了 WPF 的主要功能和概念。 若要了解如何创建 WPF 应用程序，请参阅[教程：创建新的 WPF 应用](../get-started/create-app-visual-studio.md)。

## <a name="why-migrate-from-net-framework"></a>为什么要从 .NET Framework 迁移

适用于 .NET 5.0 的 WPF 提供优于 .NET Framework 的新功能和增强功能。 要了解如何迁移应用，请参阅[如何将 WPF 桌面应用迁移到 .NET 5](../migration/convert-project-from-net-framework.md)。

## <a name="program-with-wpf"></a>使用 WPF 进行编程

WPF 作为 .NET 类型的一个子集存在，大部分位于 <xref:System.Windows> 命名空间中。 如果你曾经使用 ASP.NET 和 Windows 窗体等框架通过 .NET 构建应用程序，应该会熟悉基本的 WPF 编程体验：

- 实例化类
- 设置属性
- 调用方法
- 处理事件

WPF 还包括可增强属性和事件的其他编程构造：[依赖项属性](../../../framework/wpf/advanced/dependency-properties-overview.md)和[路由事件](../../../framework/wpf/advanced/routed-events-overview.md)。

## <a name="markup-and-code-behind"></a>标记和代码隐藏

通过 WPF，可以使用标记和代码隐藏开发应用程序，这是 ASP.NET 开发人员已经熟悉的体验。 通常使用 XAML 标记实现应用程序的外观，同时使用托管编程语言（代码隐藏）来实现其行为。 这种外观和行为的分离具有以下优点：

- 降低了开发和维护成本，因为特定于外观的标记与特定于行为的代码不紧密耦合。

- 开发效率更高，因为设计人员在实现应用程序外观的同时，开发人员可以实现应用程序的行为。

- WPF 应用程序的[全球化和本地化](../../../framework/wpf/advanced/wpf-globalization-and-localization-overview.md) 得以简化。

### <a name="markup"></a>标记

XAML 是一种基于 XML 的标记语言，以声明形式实现应用程序的外观。 通常用它定义窗口、对话框、页面和用户控件，并填充控件、形状和图形。

下面的示例使用 XAML 来实现包含一个按钮的窗口的外观：

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button">Click Me!</Button>

</Window>
```

具体而言，此 XAML 使用 `Window` 元素定义窗口，使用 `Button` 元素定义按钮。 每个元素均配置了特性（如 `Window` 元素的 `Title` 特性）来指定窗口的标题栏文本。 在运行时，WPF 会将标记中定义的元素和特性转换为 WPF 类的实例。 例如， `Window` 元素被转换为 <xref:System.Windows.Window> 类的实例，该类的 <xref:System.Windows.Window.Title%2A> 属性是 `Title` 特性的值。

下图显示上一个示例中的 XAML 定义的用户界面 (UI)：

:::image type="content" source="media/index/markup-window-button.png" alt-text="包含按钮的窗口":::

由于 XAML 是基于 XML 的，因此使用它编写的 UI 汇集在嵌套元素的层次结构中，称为[元素树](../../../framework/wpf/advanced/trees-in-wpf.md)。 元素树提供了一种直观的逻辑方式来创建和管理 UI。

### <a name="code-behind"></a>代码隐藏

应用程序的主要行为是实现响应用户交互的功能。 例如，单击菜单或按钮，以及在响应中调用业务逻辑和数据访问逻辑。 在 WPF 中，在与标记相关联的代码中实现此行为。 此类代码称为代码隐藏。 下面的示例演示上一个示例的更新标记和代码隐藏：

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.AWindow"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button" Click="button_Click">Click Me!</Button>

</Window>
```

更新的标记定义 `xmlns:x` 命名空间，并将其映射到为代码隐藏类型添加支持的架构。 `x:Class` 特性用于将代码隐藏类与此特定 XAML 标记相关联。 考虑此特性在 `<Window>` 元素上声明，代码隐藏类必须从 `Window` 类继承。

```csharp
using System.Windows;

namespace SDKSample
{
    public partial class AWindow : Window
    {
        public AWindow()
        {
            // InitializeComponent call is required to merge the UI
            // that is defined in markup with this class, including  
            // setting properties and registering event handlers
            InitializeComponent();
        }

        void button_Click(object sender, RoutedEventArgs e)
        {
            // Show message box when button is clicked.
            MessageBox.Show("Hello, Windows Presentation Foundation!");
        }
    }
}
```

```vb
Namespace SDKSample

    Partial Public Class AWindow
        Inherits System.Windows.Window

        Public Sub New()

            ' InitializeComponent call is required to merge the UI
            ' that is defined in markup with this class, including  
            ' setting properties and registering event handlers
            InitializeComponent()

        End Sub

        Private Sub button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)

            ' Show message box when button is clicked.
            MessageBox.Show("Hello, Windows Presentation Foundation!")

        End Sub

    End Class

End Namespace
```

从代码隐藏类的构造函数调用 `InitializeComponent`，以将标记中定义的 UI 与代码隐藏类合并在一起。 （生成应用程序时即会生成 `InitializeComponent`，因此不需要手动实现它。）`x:Class` 和 `InitializeComponent` 的组合可确保在创建实现时正确地对其进行初始化。

请注意，在标记中，`<Button>` 元素定义了 `Click` 属性的值 `button_click`。 将标记和代码隐藏初始化并使其一起工作后，按钮的 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件会自动映射到 `button_click` 方法。 单击该按钮时，将调用事件处理程序，并通过调用 <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> 方法显示一个消息框。

下图显示单击该按钮后的结果：

:::image type="content" source="media/index/markup-window-button-clicked.png" alt-text="消息框":::

## <a name="input-and-commands"></a>输入和命令

最常检测和响应用户输入的控件。 WPF 输入系统使用直接事件和路由事件来支持文本输入、焦点管理和鼠标定位。

应用程序通常具有复杂的输入要求。 WPF 提供了命令系统，用于将用户输入操作与对这些操作做出响应的代码分隔开来。 命令系统允许多个源调用相同的命令逻辑。 例如，进行由不同应用程序使用的常见编辑操作：复制、剪切和粘贴。   如果使用命令实现了这些操作，则它们可以由不同的用户操作调用。

## <a name="controls"></a>控制

应用程序模型带来的用户体验是构造的控件。 在 WPF 中，“控件”是一个概括性术语，适用于具有以下特征的 WPF 类类别：

- 托管在窗口或页面中。
- 拥有用户界面。
- 实现某些行为。

有关详细信息，请参阅 [控件](../../../framework/wpf/controls/index.md)。

### <a name="wpf-controls-by-function"></a>按功能分类的 WPF 控件

下面列出了内置的 WPF 控件：

- **按钮**： <xref:System.Windows.Controls.Button> 和 <xref:System.Windows.Controls.Primitives.RepeatButton>。

- **数据显示**：<xref:System.Windows.Controls.DataGrid>、<xref:System.Windows.Controls.ListView> 和 <xref:System.Windows.Controls.TreeView>。

- **日期显示和选项**： <xref:System.Windows.Controls.Calendar> 和 <xref:System.Windows.Controls.DatePicker>。

- **对话框**： <xref:Microsoft.Win32.OpenFileDialog>、 <xref:System.Windows.Controls.PrintDialog>和 <xref:Microsoft.Win32.SaveFileDialog>。

- **数字墨迹**： <xref:System.Windows.Controls.InkCanvas> 和 <xref:System.Windows.Controls.InkPresenter>。

- **文档**： <xref:System.Windows.Controls.DocumentViewer>、 <xref:System.Windows.Controls.FlowDocumentPageViewer>、 <xref:System.Windows.Controls.FlowDocumentReader>、 <xref:System.Windows.Controls.FlowDocumentScrollViewer>和 <xref:System.Windows.Controls.StickyNoteControl>。

- **输入**： <xref:System.Windows.Controls.TextBox>、 <xref:System.Windows.Controls.RichTextBox>和 <xref:System.Windows.Controls.PasswordBox>。

- **布局**： <xref:System.Windows.Controls.Border>、 <xref:System.Windows.Controls.Primitives.BulletDecorator>、 <xref:System.Windows.Controls.Canvas>、 <xref:System.Windows.Controls.DockPanel>、 <xref:System.Windows.Controls.Expander>、 <xref:System.Windows.Controls.Grid>、 <xref:System.Windows.Controls.GridView>、 <xref:System.Windows.Controls.GridSplitter>、 <xref:System.Windows.Controls.GroupBox>、 <xref:System.Windows.Controls.Panel>、 <xref:System.Windows.Controls.Primitives.ResizeGrip>、 <xref:System.Windows.Controls.Separator>、 <xref:System.Windows.Controls.Primitives.ScrollBar>、 <xref:System.Windows.Controls.ScrollViewer>、 <xref:System.Windows.Controls.StackPanel>、 <xref:System.Windows.Controls.Primitives.Thumb>、 <xref:System.Windows.Controls.Viewbox>、 <xref:System.Windows.Controls.VirtualizingStackPanel>、 <xref:System.Windows.Window>和 <xref:System.Windows.Controls.WrapPanel>。

- **媒体**： <xref:System.Windows.Controls.Image>、 <xref:System.Windows.Controls.MediaElement>和 <xref:System.Windows.Controls.SoundPlayerAction>。

- **菜单**： <xref:System.Windows.Controls.ContextMenu>、 <xref:System.Windows.Controls.Menu>和 <xref:System.Windows.Controls.ToolBar>。

- **导航**： <xref:System.Windows.Controls.Frame>、 <xref:System.Windows.Documents.Hyperlink>、 <xref:System.Windows.Controls.Page>、 <xref:System.Windows.Navigation.NavigationWindow>和 <xref:System.Windows.Controls.TabControl>。

- **选项**： <xref:System.Windows.Controls.CheckBox>、 <xref:System.Windows.Controls.ComboBox>、 <xref:System.Windows.Controls.ListBox>、 <xref:System.Windows.Controls.RadioButton>和 <xref:System.Windows.Controls.Slider>。

- **用户信息**： <xref:System.Windows.Controls.AccessText>、 <xref:System.Windows.Controls.Label>、 <xref:System.Windows.Controls.Primitives.Popup>、 <xref:System.Windows.Controls.ProgressBar>、 <xref:System.Windows.Controls.Primitives.StatusBar>、 <xref:System.Windows.Controls.TextBlock>和 <xref:System.Windows.Controls.ToolTip>。

## <a name="layout"></a>Layout

创建用户界面时，按照位置和大小排列控件以形成布局。 任何布局的一项关键要求都是适应窗口大小和显示设置的变化。 WPF 为你提供一流的可扩展布局系统，而不强制你编写代码以适应这些情况下的布局。

布局系统的基础是相对定位，这提高了适应不断变化的窗口和显示条件的能力。 该布局系统还可管理控件之间的协商以确定布局。 协商是一个两步过程：首先，控件将需要的位置和大小告知父级。 其次，父级将控件可以有的空间告知控件。

该布局系统通过基 WPF 类公开给子控件。 对于通用的布局（如网格、堆叠和停靠），WPF 包括若干布局控件：

- <xref:System.Windows.Controls.Canvas>：子控件提供其自己的布局。

- <xref:System.Windows.Controls.DockPanel>：子控件与面板的边缘对齐。

- <xref:System.Windows.Controls.Grid>：子控件由行和列定位。

- <xref:System.Windows.Controls.StackPanel>：子控件垂直或水平堆叠。

- <xref:System.Windows.Controls.VirtualizingStackPanel>：子控件在水平或垂直的行上虚拟化并排列。

- <xref:System.Windows.Controls.WrapPanel>：子控件按从左到右的顺序放置，在当前行上的空间不足时 换行到下一行。

下面的示例使用 <xref:System.Windows.Controls.DockPanel> 布置几个 <xref:System.Windows.Controls.TextBox> 控件：

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.LayoutWindow"
    Title="Layout with the DockPanel" Height="143" Width="319">
  
  <!--DockPanel to layout four text boxes--> 
  <DockPanel>
    <TextBox DockPanel.Dock="Top">Dock = "Top"</TextBox>
    <TextBox DockPanel.Dock="Bottom">Dock = "Bottom"</TextBox>
    <TextBox DockPanel.Dock="Left">Dock = "Left"</TextBox>
    <TextBox Background="White">This TextBox "fills" the remaining space.</TextBox>
  </DockPanel>

</Window>
```

<xref:System.Windows.Controls.DockPanel> 允许子 <xref:System.Windows.Controls.TextBox> 控件，以告诉它如何排列这些控件。 为了完成此操作，<xref:System.Windows.Controls.DockPanel> 实现 `Dock` 附加了属性，该属性公开给子控件，以允许每个子控件指定停靠样式。

> [!NOTE]
> 由父控件实现以便子控件使用的属性是 WPF 构造，称为[附加属性](../../../framework/wpf/advanced/attached-properties-overview.md)。

下图显示上一个示例中的 XAML 标记的结果：：

:::image type="content" source="media/index/dockpanel-page.png" alt-text="DockPanel 页":::

## <a name="data-binding"></a>数据绑定

大多数应用程序旨在为用户提供查看和编辑数据的方法。 对于 WPF 应用程序，存储和访问数据的工作已由许多不同的 .NET 数据访问库（例如 SQL 和 Entity Framework Core）提供。 访问数据并将数据加载到应用程序的托管对象后，WPF 应用程序的复杂工作开始。 从根本上来说，这涉及到两件事：

01. 将数据从托管对象复制到控件，在控件中可以显示和编辑数据。

01. 确保使用控件对数据所做的更改将复制回托管对象。

为了简化应用程序开发，WPF 提供了一个强大的数据绑定引擎来自动处理这些步骤。 数据绑定引擎的核心单元是 <xref:System.Windows.Data.Binding> 类，其工作是将控件（绑定目标）绑定到数据对象（绑定源）。 下图阐释了这种关系：

:::image type="content" source="media/index/databinding-basic-diagram.png" alt-text="基本数据绑定示意图":::

WPF 支持直接在 XAML 标记中声明绑定。 例如，下面的 XAML 代码使用“`{Binding ... }`”XAML 语法将 <xref:System.Windows.Controls.TextBox> 的 <xref:System.Windows.Controls.TextBox.Text%2A> 属性绑定到对象的 `Name` 属性。 这假设有一个数据对象设置为具有 `Name` 属性 `Window` 的 <xref:System.Windows.FrameworkElement.DataContext%2A> 属性。

```xaml
 <Window
     xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
     xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
     x:Class="SDKSample.DataBindingWindow">

   <!-- Bind the TextBox to the data source (TextBox.Text to Person.Name) -->
   <TextBox Name="personNameTextBox" Text="{Binding Path=Name}" />

 </Window>
```

WPF 数据绑定引擎不仅提供绑定，还提供验证、排序、筛选和分组。 此外，数据绑定支持使用数据模板来为数据绑定创建自定义的用户界面。

有关详细信息，请参阅[数据绑定概述](../data/index.md)。

## <a name="graphics--animation"></a>图形和动画

WPF 提供一组广泛且灵活的图形功能，具有以下优点：

- **图形与分辨率和设备均无关**。 WPF 图形系统中的基本度量单位是与设备无关的像素（即 1/96 英寸），为实现与分辨率和设备无关的呈现提供了基础。 每个与设备无关的像素都会自动缩放，以匹配呈现它的系统的每英寸点数 (dpi) 设置。

- **精度更高**。 WPF 坐标系统使用双精度浮点数字度量，而不是单精度数字。 转换和不透明度值也表示为双精度数字。 WPF 还支持广泛的颜色域 (scRGB)，并集成了对管理来自不同颜色空间的输入的支持。

- **高级图形和动画支持**。 WPF 通过为你管理动画场景简化了图形编程，你无需担心场景处理、呈现循环和双线性内插。 此外，WPF 还提供了点击测试支持和全面的 alpha 合成支持。

- **硬件加速**。 WPF 图形系统充分利用图形硬件来尽量降低 CPU 使用率。

### <a name="2d-graphics"></a>2D 图形

WPF 提供一个常用矢量绘制的二维形状库，例如矩形和椭圆。 形状不只是用于显示；还会实现许多你期望的控件功能，包括键盘和鼠标输入。

WPF 提供的二维形状包含基本形状的标准集。 但是，你可能需要创建自定义形状以辅助改进自定义用户界面的设计。 WPF 提供几何图形来创建可直接绘制、用作画笔或用于剪辑其他形状和控件的自定义形状。

有关详细信息，请参阅[几何图形概述](../../../framework/wpf/graphics-multimedia/geometry-overview.md)。

WPF 二维功能的子集包括视觉效果，如渐变、位图、绘图、用视频绘画、旋转、缩放和倾斜。 这些效果都是通过画笔实现的。 下图显示了一些示例：

:::image type="content" source="media/index/graphics-brushes.png" alt-text="不同画笔的图示":::

有关详细信息，请参阅 [WPF 画笔概述](../../../framework/wpf/graphics-multimedia/wpf-brushes-overview.md)。

### <a name="3d-rendering"></a>三维呈现

WPF 还包括三维呈现功能，这些功能与二维图形集成，以创建更精彩、更有趣的用户界面。 例如，下图显示呈现在三维形状上的二维图像：

:::image type="content" source="media/index/graphics-3d.png" alt-text="Visual3D 示例屏幕快照":::

有关详细信息，请参阅[三维图形概述](../../../framework/wpf/graphics-multimedia/3-d-graphics-overview.md)。

### <a name="animation"></a>动画

WPF 动画支持可以使控件变大、抖动、旋转和淡出，以形成有趣的页面过渡等。 你可以对大多数 WPF 类，甚至自定义类进行动画处理。 下图显示了运行中的一个简单动画：

:::image type="content" source="media/index/animation-cube.gif" alt-text="具有动画效果的立方体图":::

有关详细信息，请参阅[动画概述](../../../framework/wpf/graphics-multimedia/animation-overview.md)。

## <a name="text-and-typography"></a>文本和版式

WPF 提供以下功能以实现高质量的文本呈现：

- OpenType 字体支持。
- ClearType 增强功能。
- 利用硬件加速的高性能。
- 文本与媒体、图形和动画的集成。
- 国际字体支持和回退机制。

作为文本与图形集成的演示，下图显示了文本修饰的应用程序：

:::image type="content" source="media/index/text.png" alt-text="具有各种文本修饰的文本":::

有关详细信息，请参阅 [Windows Presentation Foundation 中的版式](../../../framework/wpf/advanced/typography-in-wpf.md)。

## <a name="customize-wpf-apps"></a>自定义 WPF 应用

到目前为止，你已经了解用于开发应用程序的核心 WPF 构建块：

- 你可以使用该应用程序模型来托管和交付应用程序内容，它主要由控件组成。
- 为简化用户界面中控件的安排，可使用 WPF 布局系统。
- 可以使用数据绑定来减少将用户界面与数据集成的工作。
- 若要增强你应用程序的可视化外观，可以使用 WPF 提供的综合图形、动画和媒体支持。

不过，在创建和管理真正独特且视觉效果非凡的用户体验时，基础知识通常是不够的。 标准的 WPF 控件可能无法与你所需的应用程序外观集成。 数据可能不会以最有效的方式显示。 你应用程序的整体用户体验可能不适合 Windows 主题的默认外观和感觉。

出于此原因，WPF 提供了各种机制来打造独特的用户体验。

### <a name="content-model"></a>内容模型

大多数 WPF 控件的主要用途是显示内容。 在 WPF 中，可以构成控件内容的项的类型和数目称为控件的 *内容模型*。 某些控件可以包含一种内容类型的一个项。 例如，<xref:System.Windows.Controls.TextBox> 的内容是分配给 <xref:System.Windows.Controls.TextBox.Text%2A> 属性的一个字符串值。

但是，其他控件可以包含不同内容类型的多个项；<xref:System.Windows.Controls.Button> 的内容（由 <xref:System.Windows.Controls.ContentControl.Content%2A> 属性指定）可以包含各种项，包括布局控件、文本、图像和形状。

有关各种控件支持的内容类型的详细信息，请参阅 [WPF 内容模型](../../../framework/wpf/controls/wpf-content-model.md)。

### <a name="triggers"></a>触发器

尽管 XAML 标记的主要用途是实现应用程序的外观，你也可以使用 XAML 来实现应用程序行为的某些方面。 其中一个示例是使用触发器来基于用户交互更改应用程序的外观。 有关详细信息，请参阅[样式和模板](../controls/styles-templates-overview.md)。

### <a name="templates"></a>模板

WPF 控件的默认用户界面通常是从其他控件和形状构造的。 例如， <xref:System.Windows.Controls.Button> 由 <xref:Microsoft.Windows.Themes.ButtonChrome> 和 <xref:System.Windows.Controls.ContentPresenter> 控件组成。 <xref:Microsoft.Windows.Themes.ButtonChrome> 提供了标准按钮外观，而 <xref:System.Windows.Controls.ContentPresenter> 显示按钮的内容，正如 <xref:System.Windows.Controls.ContentControl.Content%2A> 属性所指定。

有时，某个控件的默认外观可能与应用程序的整体外观冲突。 在这种情况下，可以使用 <xref:System.Windows.Controls.ControlTemplate> 更改控件的用户界面的外观，而不更改其内容和行为。

例如，单击 <xref:System.Windows.Controls.Button> 时会引发 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件。 通过更改按钮的模板来显示 <xref:System.Windows.Shapes.Ellipse> 形状，控件的可视方位发生了变化，但功能却没有。 你仍可以单击该控件的可视方位，将按预期引发 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件。

:::image type="content" source="media/index/template-button.png" alt-text="省略号按钮和第二个窗口":::

### <a name="data-templates"></a>数据模板

使用控件模板可以指定控件的外观，而使用数据模板则可以指定控件内容的外观。 数据模板经常用于改进绑定数据的显示方式。 下图显示 <xref:System.Windows.Controls.ListBox> 的默认外观，它绑定到 `Task` 对象的集合，其中每个任务都具有名称、描述和优先级：

:::image type="content" source="media/index/data-template-listbox-normal.png" alt-text="具有默认外观的列表框":::

默认外观是你对 <xref:System.Windows.Controls.ListBox>的期望。 但是，每个任务的默认外观仅包含任务名称。 若要显示任务名称、描述和优先级，必须使用 <xref:System.Windows.Controls.ListBox> 更改 <xref:System.Windows.DataTemplate>控件绑定列表项的默认外观。 下面是一个示例，说明如何应用为 `Task` 对象创建的数据模板。

:::image type="content" source="media/index/data-template-listbox-applied.png" alt-text="使用数据模板的列表框":::

<xref:System.Windows.Controls.ListBox> 会保留其行为和整体外观；只有列表框所显示内容的外观发生变化。

有关详细信息，请参阅[数据模板化概述](../../../framework/wpf/data/data-templating-overview.md)。

### <a name="styles"></a>样式

通过样式功能，开发人员和设计人员能够对其产品的特定外观进行标准化。 WPF 提供了一个强样式模型，其基础是 <xref:System.Windows.Style> 元素。 样式可以将属性值应用于类型。 引用样式时，可以根据类型将其自动应用于所有对象，或应用于单个对象。 下面的示例创建一个样式，该样式将窗口上的每个 <xref:System.Windows.Controls.Button> 的背景色设置为 `Orange`：

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.StyleWindow"
    Title="Styles">

    <Window.Resources>
        <!-- Style that will be applied to all buttons for this window -->
        <Style TargetType="{x:Type Button}">
            <Setter Property="Background" Value="Orange" />
            <Setter Property="BorderBrush" Value="Crimson" />
            <Setter Property="FontSize" Value="20" />
            <Setter Property="FontWeight" Value="Bold" />
            <Setter Property="Margin" Value="5" />
        </Style>
    </Window.Resources>
    <StackPanel>

        <!-- This button will have the style applied to it -->
        <Button>Click Me!</Button>

        <!-- This label will not have the style applied to it -->
        <Label>Don't Click Me!</Label>

        <!-- This button will have the style applied to it -->
        <Button>Click Me!</Button>
        
    </StackPanel>
</Window>
```

由于此样式针对所有 <xref:System.Windows.Controls.Button> 控件，因此将自动应用于窗口中的所有按钮，如下图所示：

:::image type="content" source="media/index/styles-buttons.png" alt-text="两个橙色按钮":::

有关详细信息，请参阅[样式和模板](../controls/styles-templates-overview.md)。

### <a name="resources"></a>资源

应用程序中的控件应共享相同的外观，它可以包括从字体和背景色到控件模板、数据模板和样式的所有内容。 你可以对用户界面资源使用 WPF 支持，以将这些资源封装在一个位置以便重复使用。

下面的示例定义 <xref:System.Windows.Controls.Button> 和 <xref:System.Windows.Controls.Label>共享的通用背景色：

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ResourcesWindow"
    Title="Resources Window">

  <!-- Define window-scoped background color resource -->
  <Window.Resources>
    <SolidColorBrush x:Key="defaultBackground" Color="Red" />
  </Window.Resources>

  <!-- Button background is defined by window-scoped resource -->
  <Button Background="{StaticResource defaultBackground}">One Button</Button>

  <!-- Label background is defined by window-scoped resource -->
  <Label Background="{StaticResource defaultBackground}">One Label</Label>
</Window>
```

有关详细信息，请参阅[如何定义和引用 WPF 资源](../systems/xaml-resources-how-to-define-and-reference.md)。

### <a name="custom-controls"></a>自定义控件

尽管 WPF 提供了大量自定义支持，但你仍可能会遇到现有 WPF 控件不满足你的应用程序或其用户的需求的情况。 出现这种情况的原因有：

- 不能通过自定义现有 WPF 实现的外观和感觉创建所需的用户界面。
- 现有 WPF 实现不支持（或很难支持）所需的行为。

但是，此时，你可以充分利用三个 WPF 模型中的一个来创建新的控件。 每个模型都针对一个特定的方案并要求你的自定义控件派生自特定 WPF 基类。 下面列出了这三个模型：

- **用户控件模型**\
自定义控件派生自 <xref:System.Windows.Controls.UserControl> 并由一个或多个其他控件组成。

- **控件模型** 自定义控件派生自 <xref:System.Windows.Controls.Control>，并用于生成使用模板将其行为与其外观分隔开来的实现，非常类似大多数 WPF 控件。 派生自 <xref:System.Windows.Controls.Control> 使得你可以更自由地创建自定义用户界面（相较用户控件），但它可能需要花费更多精力。

- **框架元素模型**。\
当其外观由自定义呈现逻辑（而不是模板）定义时，自定义控件派生自 <xref:System.Windows.FrameworkElement> 。

有关自定义控件的详细信息，请参阅[控件创作概述](../../../framework/wpf/controls/control-authoring-overview.md)。

## <a name="see-also"></a>另请参阅

- [教程：创建新的 WPF 应用](../get-started/create-app-visual-studio.md)
- [将 WPF 应用迁移到 .NET Core](../migration/convert-project-from-net-framework.md)
- [WPF 窗口概述](../windows/index.md)
- [数据绑定概述](../data/index.md)
- [XAML概述](../xaml/index.md)
