---
title: WPF 中的窗口概述
description: 了解窗口对象在 WPF 中的基本功能。 了解如何为 Windows Presentation Foundation (WPF) 应用创建和管理窗口。
ms.date: 03/11/2021
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], displaying content via
- XAML pages [WPF], displaying
- content [WPF], displaying via XAML
- window objects [WPF]
- hosting [WPF], applications
- managing windows [WPF]
- dialog boxes [WPF]
- Page object [WPF]
- NavigationWindow objects [WPF]
- applications [WPF], hosting
- content [WPF], displaying
- events [WPF]
- content [WPF], displaying via procedural code
- modal windows [WPF]
- procedural code [WPF], displaying content via
- displaying content via procedural code [WPF]
- window management [WPF]
- displaying content [WPF]
- window events [WPF]
- windows [WPF]
- modal dialog boxes [WPF]
- displaying XAML pages [WPF]
ms.openlocfilehash: cf103e4f574a71dd21b82eb5315fa08b905319be
ms.sourcegitcommit: 32616f61a7b001efcc8567fee5fdf01f83da76cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "107562009"
---
# <a name="overview-of-wpf-windows-wpf-net"></a>WPF 窗口概述 (WPF .NET)

用户通过窗口与 Windows Presentation Foundation (WPF) 应用程序交互。 窗口的主要用途是托管使数据可视化并使用户能够与数据交互的内容。 WPF 应用程序使用 <xref:System.Windows.Window> 类提供自己的窗口。 本文先介绍 <xref:System.Windows.Window>，然后讲述在应用程序中创建和管理窗口的基础知识。

> [!IMPORTANT]
> 本文使用从 C# 项目生成的 XAML。 如果使用 Visual Basic，则 XAML 看上去可能有不同。 这些差异通常出现在 `x:Class` 属性值上。 C# 包括项目的根命名空间，而 Visual Basic 不包括。
>
> C# 的项目模板创建了一个 `App` 类型，包含在 _app.xaml_ 文件中。 在 Visual Basic 中，该类型名为 `Application`，该文件名为 `Application.xaml`。

## <a name="the-window-class"></a>窗口类

在 WPF 中，窗口由用于执行以下操作的 <xref:System.Windows.Window> 类封装：

- 显示窗口。
- 配置窗口的大小、位置和外观。
- 托管特定于应用程序的内容。
- 管理窗口的生存期。

下图展示了窗口的构成部分：

:::image type="content" source="./media/index/window-parts.png" alt-text="显示 WPF 窗口各部分的屏幕截图。":::

窗口分为两个区域：非工作区和工作区。

窗口的非工作区由 WPF实现，它包括大多数窗口所共有的窗口部分，包括：

- 标题栏 (1-5)。
- 图标 (1)。
- 标题 (2)。
- 最小化 (3)、最大化 (4) 和关闭 (5) 按钮。
- 包含菜单项的系统菜单 (6)。 单击图标 (1) 时出现。
- 边框 (7)。

窗口的工作区是窗口的非工作区内部的区域，由开发人员用于添加特定于应用程序的内容，例如菜单栏、工具栏和控件。

- 工作区 (8)。
- 大小调整手柄 (9)。 这是添加到工作区 (8) 的控件。

## <a name="implementing-a-window"></a>实现窗口

典型窗口的实现既包括外观又包括行为，外观定义用户看到的窗口的样子，行为定义用户与之交互时窗口的运行方式。  在 WPF 中，可以使用代码或 XAML 标记实现窗口的外观和行为。

但在一般情况下，窗口的外观使用 XAML 标记实现，行为使用代码隐藏实现，如以下示例所示。

```xaml
<Window x:Class="WindowsOverview.Window1"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WindowsOverview"
        >

    <!-- Client area containing the content of the window -->
    
</Window>
```

下面的代码是 XAML 的代码隐藏。

```csharp
using System.Windows;

namespace WindowsOverview
{
    public partial class Window1 : Window
    {
        public Window1()
        {
            InitializeComponent();
        }
    }
}
```

```vb
Public Class Window1

End Class
```

若要使 XAML 标记文件和代码隐藏文件配合工作，需要满足以下要求：

- 在标记中，`Window` 元素必须包含 `x:Class` 属性。 生成应用程序时，标记文件中存在 `x:Class` 会使 Microsoft 生成引擎 (MSBuild) 生成派生自 <xref:System.Windows.Window> 的 `partial` 类，其名称由 `x:Class` 属性指定。 这要求为 XAML 架构 (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`) 添加 XAML 命名空间声明。 生成的 `partial` 类实现 `InitializeComponent` 方法，注册事件和设置在标记中实现的属性时将调用此方法。

- 在代码隐藏中，类必须是 `partial` 类、名称必须是标记中 `x:Class` 属性指定的相同名称，并且它必须派生自 <xref:System.Windows.Window>。 这样，代码隐藏文件就与应用程序生成时为标记文件生成的 `partial` 类相关联（请参阅[编译 WPF 应用程序](../../../framework/wpf/app-development/building-a-wpf-application-wpf.md)以了解详细信息）。

- 在代码隐藏中，<xref:System.Windows.Window> 类必须实现调用 `InitializeComponent` 方法的构造函数。 `InitializeComponent` 由标记文件已生成的 `partial` 类实现，用以注册事件并设置标记中定义的属性。

> [!NOTE]
> 使用 Visual Studio 将新的 <xref:System.Windows.Window> 添加到项目时，<xref:System.Windows.Window> 通过同时使用标记和代码隐藏实现，并且包括必要的配置来创建此处所述的标记文件和代码隐藏文件之间的关联。

进行了此配置后，可以专注于在 XAML 标记中定义窗口的外观，并可在代码隐藏中实现窗口的行为。 以下示例显示了一个窗口，该窗口中的一个按钮定义了 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件的事件处理程序。 这是在 XAML 中实现的，处理程序是在代码隐藏中实现的。

```xaml
<Window x:Class="WindowsOverview.Final"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WindowsOverview"
        >

    <!-- Client area containing the content of the window -->

    <Button Click="Button_Click">Click This Button</Button>
    
</Window>
```

下面的代码是 XAML 的代码隐藏。

```csharp
using System.Windows;

namespace WindowsOverview
{
    public partial class Window1 : Window
    {
        public Window1()
        {
            InitializeComponent();
        }

        private void Button_Click(object sender, RoutedEventArgs e)
        {
            MessageBox.Show("Button was clicked.");
        }
    }
}
```

```vb
Public Class Window1

    Private Sub Button_Click(sender As Object, e As RoutedEventArgs)
        MessageBox.Show("Button was clicked.")
    End Sub

End Class
```

### <a name="configuring-a-window-for-msbuild"></a>为 MSBuild 配置窗口

实现窗口的方式决定为 MSBuild 配置窗口的方式。 对于使用 XAML 标记和代码隐藏定义的窗口：

- XAML 标记文件配置为 MSBuild `Page` 项。
- 代码隐藏文件配置为 MSBuild `Compile` 项。

.NET SDK 项目会自动导入正确的 `Page` 和 `Compile` 项，无需对其进行声明。 如果为 WPF 配置了项目，则会将 XAML 标记文件自动导入为 `Page`，并将相应的代码隐藏文件导入为 `Compile`。

MSBuild 项目不会自动导入类型，你必须自行声明它们：

```xml
<Project>
    ...
    <Page Include="MarkupAndCodeBehindWindow.xaml" />
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />
    ...
</Project>
```

有关生成 WPF 应用程序的信息，请参阅[编译 WPF 应用程序](../../../framework/wpf/app-development/building-a-wpf-application-wpf.md)。

## <a name="window-lifetime"></a>窗口生存期

与所有类一样，窗口也有生存期，开始于首次实例化窗口，在这之后将打开、激活/停用直至最终关闭窗口。

### <a name="opening-a-window"></a>打开窗口

若要打开窗口，首先要创建窗口实例，下面的示例演示此操作：

:::code language="csharp" source="snippets/index_2/csharp/App.xaml.cs":::
:::code language="vb" source="snippets/index_2/vb/Application.xaml.vb":::

在本示例中，`Window1` 在应用程序启动时实例化，此过程在引发 <xref:System.Windows.Application.Startup> 事件时发生。 有关“启动”窗口的详细信息，请参阅[如何获取或设置主应用程序窗口](how-to-get-set-main-application-window.md)。

实例化窗口后，对其的引用将自动添加到由 <xref:System.Windows.Application> 对象管理的[窗口列表](xref:System.Windows.Application.Windows%2A)。 <xref:System.Windows.Application> 会将要实例化的第一个窗口自动设置为[主应用程序窗口](xref:System.Windows.Application.MainWindow%2A)。

最后通过调用 <xref:System.Windows.Window.Show%2A> 方法打开窗口，如以下图像所示：

:::image type="content" source="./media/index/window-with-button.png" alt-text="内含单个按钮的 WPF 窗口。":::

通过调用 <xref:System.Windows.Window.Show%2A> 打开的窗口是无模式窗口，应用程序不会阻止用户与该应用程序中的其他窗口交互。 通过 <xref:System.Windows.Window.ShowDialog%2A> 打开窗口时，会将窗口打开为模式，并限制用户与该窗口交互。 有关详细信息，请参阅[对话框概述](dialog-boxes-overview.md)。

调用 <xref:System.Windows.Window.Show%2A>时，窗口先执行初始化工作，然后显示窗口以建立让窗口可以接收用户输入的基础结构。 初始化窗口时，将引发 <xref:System.Windows.Window.SourceInitialized> 事件并显示窗口。

有关详细信息，请参阅[如何打开窗口或对话框](how-to-open-window-dialog-box.md)。

#### <a name="startup-window"></a>启动窗口

上一个示例使用了 `Startup` 事件来运行显示初始应用程序窗口的代码。 作为快捷方式，请改用 <xref:System.Windows.Application.StartupUri%2A> 来指定应用程序中 XAML 文件的路径。 应用程序将自动创建并显示由该属性指定的窗口。

:::code language="xaml" source="snippets/index/csharp/App.xaml" highlight="5":::

#### <a name="window-ownership"></a>窗口所有权

使用 <xref:System.Windows.Window.Show%2A> 方法打开的窗口与创建它的窗口不具有隐式关系。 用户可以与其中任意一个窗口独立交互，这意味着这两个窗口都可以执行以下操作：

- 覆盖另一个窗口（除非其中一个窗口的 <xref:System.Windows.Window.Topmost%2A> 属性设置为 `true`）。
- 在不影响另一个窗口的情况下最小化、最大化和还原。

某些窗口要求与打开它们的窗口保持某种关系。 例如，集成开发环境 (IDE) 应用程序可能打开属性窗口和工具窗口，这些窗口的典型行为是覆盖创建它们的窗口。 此外，此类窗口应始终与创建它们的窗口一起关闭、最小化、最大化和还原。 可以通过让一个窗口拥有另一个窗口来建立这种关系，通过使用对所有者窗口的引用设置被拥有窗口的 <xref:System.Windows.Window.Owner%2A>  属性来实现。 下面的示例说明了这一点。

:::code language="csharp" source="snippets/index/csharp/ChildWindow1.xaml.cs" range="12-18":::
:::code language="vb" source="snippets/index/vb/ChildWindow1.xaml.vb" range="2-7":::

建立所有权后：

- 被拥有的窗口可以通过检查其 <xref:System.Windows.Window.Owner%2A> 属性的值来引用它的所有者窗口。
- 所有者窗口可以通过检查其 <xref:System.Windows.Window.OwnedWindows%2A> 属性的值来发现它拥有的所有窗口。

### <a name="window-activation"></a>窗口激活

第一次打开窗口时，它即成为活动窗口。 活动窗口是当前捕获用户输入（例如击键和鼠标单击）的窗口。 当窗口处于活动状态时，它会引发 <xref:System.Windows.Window.Activated> 事件。

> [!NOTE]
> 第一次打开窗口时，只有当引发 <xref:System.Windows.Window.Activated> 后才会引发 <xref:System.Windows.FrameworkElement.Loaded> 和 <xref:System.Windows.Window.ContentRendered> 事件。 记住这一点，在引发 <xref:System.Windows.Window.ContentRendered> 时，实际上就可认为窗口已打开。

某个窗口成为活动窗口后，用户可以在同一应用程序内激活其他窗口，或者激活其他应用程序。 发生这种情况时，将停用当前的活动窗口，并引发 <xref:System.Windows.Window.Deactivated> 事件。 同样，如果用户选择当前停用的窗口，该窗口将再次成为活动窗口，并引发 <xref:System.Windows.Window.Activated> 事件。

处理 <xref:System.Windows.Window.Activated> 和 <xref:System.Windows.Window.Deactivated> 的一个常见原因是为了启用和禁用仅在窗口处于活动状态时才能够运行的功能。 例如，一些窗口显示需要用户持续输入或关注的交互式内容，这些内容包括游戏和视频播放器。 以下示例是简化的视频播放器，展示如何处理 <xref:System.Windows.Window.Activated> 和 <xref:System.Windows.Window.Deactivated> 以实现此行为。

:::code language="xaml" source="snippets/index/csharp/CustomMediaPlayerWindow.xaml":::

下面的代码是 XAML 的代码隐藏。

:::code language="csharp" source="snippets/index/csharp/CustomMediaPlayerWindow.xaml.cs":::
:::code language="vb" source="snippets/index/vb/CustomMediaPlayerWindow.xaml.vb":::

停用某个窗口后，其他类型的应用程序可能仍会在后台运行代码。 例如，在用户使用其他应用程序时，邮件客户端可能会继续轮询邮件服务器。 类似的应用程序在主窗口停用时，通常将提供不同的或额外的行为。 对于邮件程序，这可能意味着将新邮件项添加到收件箱和将通知图标添加到系统任务栏。 仅当邮件窗口不处于活动状态时才显示通知图标，活动状态是通过检查 <xref:System.Windows.Window.IsActive%2A> 属性来确定的。

完成某个后台任务后，窗口可能需要通过调用 <xref:System.Windows.Window.Activate%2A> 方法来更迫切地通知用户。 如果在调用 <xref:System.Windows.Window.Activate%2A> 时，用户正与其他激活的应用程序进行交互，窗口的任务栏按钮会闪烁。 但是，如果用户正在与当前应用程序交互，则调用 <xref:System.Windows.Window.Activate%2A> 会将窗口置于前景。

> [!NOTE]
> 可以使用 <xref:System.Windows.Application.Activated?displayProperty=nameWithType> 和 <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> 事件处理应用程序范围的激活。

#### <a name="preventing-window-activation"></a>防止窗口激活

在一些情况下，不应在显示窗口时将其激活，例如聊天应用程序的对话窗口或电子邮件应用程序的通知窗口。

如果应用程序的窗口在显示时不应激活，可以在首次调用 <xref:System.Windows.Window.Show%2A> 方法之前，先将其 <xref:System.Windows.Window.ShowActivated%2A> 属性设置为 `false`。 结果是：

- 此窗口未激活。
- 未引发窗口的 <xref:System.Windows.Window.Activated> 事件。
- 当前激活的窗口保持激活状态。

 但是，只要用户通过单击工作区或非工作区激活了窗口，窗口就会变为激活状态。 在这种情况下：

- 已激活窗口。
- 已引发窗口的 <xref:System.Windows.Window.Activated> 事件。
- 停用之前激活的窗口。
- 然后按照预期，响应用户操作引发窗口的 <xref:System.Windows.Window.Deactivated> 和 <xref:System.Windows.Window.Activated> 事件。

### <a name="closing-a-window"></a>关闭窗口

窗口的生存期在用户关闭它时终止。 窗口关闭后，就不能再重新打开它。 可以使用非工作区中的元素关闭窗口，这些元素包括：

- “系统”菜单的“关闭”项。 
- 按 <kbd>ALT+F4</kbd>。
- 按“关闭”按钮。
- 在模式窗口上，当按钮的 <xref:System.Windows.Controls.Button.IsCancel%2A> 属性设置为 `true` 时，按 <kbd>ESC</kbd>。

 可以向工作区提供关闭窗口的更多机制，较为常见的机制包括：

- “文件”菜单中的“退出”项，通常用于主应用程序窗口。 
- “文件”菜单中的“关闭”项，通常位于辅助应用程序窗口中。 
- “取消”按钮，通常位于模式对话框中。
- “关闭”按钮，通常位于非模式对话框中。

若要为响应其中一种自定义机制而关闭窗口，需要调用 <xref:System.Windows.Window.Close%2A> 方法。 以下示例通过选择“文件”菜单上的“退出”来实现关闭窗口的功能。 

:::code language="xaml" source="snippets/index/csharp/ClosingWindow.xaml":::

下面的代码是 XAML 的代码隐藏。

:::code language="csharp" source="snippets/index/csharp/ClosingWindow.xaml.cs":::
:::code language="vb" source="snippets/index/vb/ClosingWindow.xaml.vb":::

> [!NOTE]
> 可将应用程序配置为在出现以下情况时自动关闭：主应用程序窗口关闭（请参阅 <xref:System.Windows.Application.MainWindow%2A>）或最后一个窗口关闭。 有关详细信息，请参阅 <xref:System.Windows.Application.ShutdownMode%2A>。

虽然窗口可通过非工作区和工作区中提供的机制显式关闭，但它也可能因为应用程序或 Windows 的其他部分中的行为而隐式关闭，行为包括：

- 用户注销或关闭 Windows。
- 窗口的 <xref:System.Windows.Window.Owner%2A> 关闭。
- 主应用程序窗口关闭且 <xref:System.Windows.Application.ShutdownMode%2A> 为 <xref:System.Windows.ShutdownMode.OnMainWindowClose>。
- 调用 <xref:System.Windows.Application.Shutdown%2A>。

> [!IMPORTANT]
> 窗口在关闭后无法重新打开。

#### <a name="cancel-window-closure"></a>取消关闭窗口

窗口关闭时，会引发两个事件：<xref:System.Windows.Window.Closing> 和 <xref:System.Windows.Window.Closed>。

<xref:System.Windows.Window.Closing> 在窗口关闭前引发，并提供一种可以阻止窗口关闭的机制。 阻止窗口关闭的一个常见原因是窗口内容包含修改的数据。 在这种情况下，处理 <xref:System.Windows.Window.Closing> 事件可以确定数据是否为已更新，如果已更新，询问用户是在不保存数据的情况下继续关闭窗口，还是取消关闭窗口。 以下示例演示了处理 <xref:System.Windows.Window.Closing> 的关键方面。

:::code language="xaml" source="snippets/index/csharp/DataWindow.xaml":::

下面的代码是 XAML 的代码隐藏。

:::code language="csharp" source="snippets/index/csharp/DataWindow.xaml.cs":::
:::code language="vb" source="snippets/index/vb/DataWindow.xaml.vb":::

向 <xref:System.Windows.Window.Closing> 事件处理程序传递 <xref:System.ComponentModel.CancelEventArgs>，它会实现 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 属性，将该属性设置为 `true` 以防止窗口关闭。

如果未处理 <xref:System.Windows.Window.Closing>，或者已处理但未取消，窗口将关闭。 在窗口真正关闭前，将引发 <xref:System.Windows.Window.Closed>。 此时，无法阻止窗口关闭。

### <a name="window-lifetime-events"></a>窗口生存期事件

下图显示窗口生存期中的主体事件的顺序：

:::image type="content" source="./media/index/window-lifetime-events.png" alt-text="此图显示了窗口生存期内的事件。":::

下图显示窗口（显示时没有激活）生存期中的主体事件的顺序（显示窗口之前将 <xref:System.Windows.Window.ShowActivated%2A> 设置为 `false`）：

:::image type="content" source="./media/index/window-lifetime-no-activation.png" alt-text="此图显示了不激活的情况下窗口生存期中的事件。":::

## <a name="window-location"></a>窗口位置

当窗口打开时，它在相对于桌面的 x 和 y 维度中有一个位置。 可以通过检查 <xref:System.Windows.Window.Left%2A> 和 <xref:System.Windows.Window.Top%2A> 来确定此位置。 设置这些属性以更改窗口的位置。

还可通过使用以下任一 <xref:System.Windows.WindowStartupLocation> 枚举值来设置 <xref:System.Windows.Window.WindowStartupLocation%2A> 属性，从而指定 <xref:System.Windows.Window> 首次出现时的初始位置：

- <xref:System.Windows.WindowStartupLocation.CenterOwner>（默认值）
- <xref:System.Windows.WindowStartupLocation.CenterScreen>
- <xref:System.Windows.WindowStartupLocation.Manual>

如果将启动位置指定为 <xref:System.Windows.WindowStartupLocation.Manual>，并且未设置 <xref:System.Windows.Window.Left%2A> 和 <xref:System.Windows.Window.Top%2A> 属性，<xref:System.Windows.Window> 将要求操作系统指定其显示位置。

### <a name="topmost-windows-and-z-order"></a>最顶层窗口和 z 顺序

除了有 x 和 y 位置外，窗口还在 z 维度中有一个位置，该位置确定窗口相对于其他窗口的垂直位置。 它称为窗口的 z 顺序，并且有两种类型：正常 z 顺序和最顶层 z 顺序。  *正常 z 顺序* 中的窗口位置取决于窗口当前是否处于活动状态。 默认情况下，窗口位于正常 z 顺序中。 *最顶层 z 顺序* 中的窗口位置也取决于它当前是否处于活动状态。 此外，最顶层 z 顺序中的窗口始终位于正常 z 顺序中的窗口之上。 窗口通过将其 <xref:System.Windows.Window.Topmost%2A> 属性设置为 `true` 来采用最顶层 z 顺序。

在每种 z 顺序类型中，当前的活动窗口显示在同一 z 顺序中所有其他窗口之上。

## <a name="window-size"></a>窗口大小

除了拥有桌面位置外，窗口还有大小，大小由多个属性确定，包括各种宽度和高度属性以及 <xref:System.Windows.Window.SizeToContent%2A>。

<xref:System.Windows.FrameworkElement.MinWidth%2A>、<xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 用于管理窗口在其生存期内可以具有的宽度范围。

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    MinWidth="300" Width="400" MaxWidth="500">
</Window>
```

窗口高度由 <xref:System.Windows.FrameworkElement.MinHeight%2A>、<xref:System.Windows.FrameworkElement.Height%2A> 和 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 管理。

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    MinHeight="300" Height="400" MaxHeight="500">
</Window>
```

由于各种宽度值和高度值各自指定了一个范围，所以大小可调整大小的窗口的宽度和高度可以是相应维度中指定范围内的任何值。 若要检测其当前的宽度和高度，请分别检查 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 和 <xref:System.Windows.FrameworkElement.ActualHeight%2A>。

 如果希望窗口的宽度和高度适应窗口内容的大小，可以使用 <xref:System.Windows.Window.SizeToContent%2A> 属性，它具有以下值：

- [SizeToContent.Manual](xref:System.Windows.SizeToContent.Manual)\
不起作用（默认值）。
- [SizeToContent.Width](xref:System.Windows.SizeToContent.Width)\
适应内容宽度，与将 <xref:System.Windows.FrameworkElement.MinWidth%2A> 和 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 都设置为内容的宽度效果相同。
- [SizeToContent.Height](xref:System.Windows.SizeToContent.Height)\
适应内容高度，与将 <xref:System.Windows.FrameworkElement.MinHeight%2A> 和 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 都设置为内容的高度效果相同。
- [SizeToContent.WidthAndHeight](xref:System.Windows.SizeToContent.WidthAndHeight)\
适应内容宽度和高度，与将 <xref:System.Windows.FrameworkElement.MinHeight%2A> 和 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 都设置为内容的高度，并将 <xref:System.Windows.FrameworkElement.MinWidth%2A> 和 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 都设置为内容的宽度效果相同。

以下示例显示了一个窗口，它在第一次显示时即自动调整垂直方向和水平方向上的大小以适应内容。

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
    SizeToContent="WidthAndHeight">
</Window>
```

以下示例显示如何在代码中设置 <xref:System.Windows.Window.SizeToContent%2A> 属性以指定重设窗口大小使其适应内容的方式。

```csharp
// Manually alter window height and width
this.SizeToContent = SizeToContent.Manual;

// Automatically resize width relative to content
this.SizeToContent = SizeToContent.Width;

// Automatically resize height relative to content
this.SizeToContent = SizeToContent.Height;

// Automatically resize height and width relative to content
this.SizeToContent = SizeToContent.WidthAndHeight;
```

```vb
' Manually alter window height and width
Me.SizeToContent = SizeToContent.Manual

' Automatically resize width relative to content
Me.SizeToContent = SizeToContent.Width

' Automatically resize height relative to content
Me.SizeToContent = SizeToContent.Height

' Automatically resize height and width relative to content
Me.SizeToContent = SizeToContent.WidthAndHeight
```

## <a name="order-of-precedence-for-sizing-properties"></a>大小调整属性的优先级顺序

从根本上说，窗口的各种大小属性可以结合使用，以定义可调整大小的窗口的宽度和高度范围。 为了确保保持有效的范围，<xref:System.Windows.Window> 将使用以下优先级顺序计算大小属性的值。

**对于高度属性：**

01. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
01. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
01. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType> / <xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
01. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>

**对于宽度属性：**

01. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
01. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
01. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType> / <xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
01. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>

优先级顺序还可以确定窗口在最大化时的大小，此时的窗口大小由 <xref:System.Windows.Window.WindowState%2A> 属性管理。

## <a name="window-state"></a>窗口状态

可调整大小的窗口在生存期中拥有三种状态：正常、最小化和最大化。 _正常_ 是窗口的默认状态。 这种状态下的窗口允许用户使用重设大小手柄或边框移动窗口和重设其大小（前提是大小可以重设）。

如果 <xref:System.Windows.Window.ShowInTaskbar%2A> 设置为 `true`，则最小化状态下的窗口将折叠到任务栏按钮；否则，它将尽可能折叠到最小大小，并将自己移动到桌面的左下角。 虽然不在任务栏显示的最小化窗口可以在桌面上四处拖动，但这两种类型的最小化窗口都不可以使用边框或重设大小手柄重设窗口大小。

具有最大化状态的窗口会扩展到它能具有的最大大小，这不能超过 <xref:System.Windows.FrameworkElement.MaxWidth%2A>、<xref:System.Windows.FrameworkElement.MaxHeight%2A> 和 <xref:System.Windows.Window.SizeToContent%2A> 属性指定的大小。 与最小化窗口一样，最大化窗口无法使用重设大小手柄或通过拖动边框来重设大小。

> [!NOTE]
> 即使窗口当前已最大化或最小化，窗口的 <xref:System.Windows.Window.Top%2A>、<xref:System.Windows.Window.Left%2A>、<xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A> 属性的值也始终表示正常状态的值。

 可以通过设置 <xref:System.Windows.Window.WindowState%2A> 属性来配置窗口的状态，该属性可以具有以下 <xref:System.Windows.WindowState> 枚举值之一：

- <xref:System.Windows.WindowState.Normal>（默认值）
- <xref:System.Windows.WindowState.Maximized>
- <xref:System.Windows.WindowState.Minimized>

以下示例显示如何创建在打开时最大化显示的窗口。

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    WindowState="Maximized">
</Window>
```

通常，应设置 <xref:System.Windows.Window.WindowState%2A> 以配置窗口的初始状态。 显示可调整大小的窗口后，用户可以按窗口标题栏上的“最小化”、“最大化”和“还原”按钮来更改窗口状态。

## <a name="window-appearance"></a>窗口外观

通过将特定于窗口的内容（例如按钮、标签和文本框）添加到窗口的工作区可以更改它的外观。 为配置非工作区，<xref:System.Windows.Window> 提供几个属性，包括用于设置窗口图标的 <xref:System.Windows.Window.Icon%2A> 和用于设置其标题的 <xref:System.Windows.Window.Title%2A>。

还可以通过配置窗口的重设大小模式、窗口样式，以及窗口是否显示为桌面任务栏中的按钮，更改非工作区边框的外观和行为。

### <a name="resize-mode"></a>重设大小模式

根据 <xref:System.Windows.Window.WindowStyle%2A> 属性，你可以控制用户是否可以重设窗口的大小，以及如何重设。 窗口样式影响以下各项：

- 允许或禁止使用鼠标拖动窗口边框来调整大小。
- 非工作区是否显示“最小化”、“最大化”和“关闭”按钮。  
- 是否启用了“最小化”、“最大化”和“关闭”按钮。  

可以通过设置窗口的 <xref:System.Windows.Window.ResizeMode%2A> 属性来配置重设窗口大小的方式，该属性可以是下列 <xref:System.Windows.ResizeMode> 枚举值之一：

- <xref:System.Windows.ResizeMode.NoResize>
- <xref:System.Windows.ResizeMode.CanMinimize>
- <xref:System.Windows.ResizeMode.CanResize>（默认值）
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>

与 <xref:System.Windows.Window.WindowStyle%2A> 一样，窗口的重设大小模式在生存期中不太可能更改，这意味着它最有可能在 XAML 标记中进行设置。

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    ResizeMode="CanResizeWithGrip">
</Window>
```

请注意，可以通过检查 <xref:System.Windows.Window.WindowState%2A> 属性来检测是否已最大化、最小化或还原窗口。

### <a name="window-style"></a>窗口样式

从窗口非工作区公开的边框适用于大多数应用程序。 但是，有时候会需要不同类型的边框，或者根本不需要边框，具体取决于窗口类型。

若要控制窗口的边框类型，请将其 <xref:System.Windows.Window.WindowStyle%2A> 属性设置为以下 <xref:System.Windows.WindowStyle> 枚举值之一：

- <xref:System.Windows.WindowStyle.None>
- <xref:System.Windows.WindowStyle.SingleBorderWindow>（默认值）
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>
- <xref:System.Windows.WindowStyle.ToolWindow>

应用窗口样式的效果如下图所示：

:::image type="content" source="./media/index/window-styles.png" alt-text="此屏幕截图显示了 WindowStyle 如何影响 WPF 中的窗口。":::

请注意，上图未显示 `SingleBorderWindow` 与 `ThreeDBorderWindow` 之间的任何明显差异。 回到 Windows XP 中，`ThreeDBorderWindow` 确实会影响窗口的绘制方式，将三维边框添加到工作区。 从 Windows 7 开始，这两种样式之间的差异很小。

可以使用 XAML 标记或代码设置 <xref:System.Windows.Window.WindowStyle%2A>。 由于在窗口生存期内不太可能发生更改，因此你最有可能使用 XAML 标记对其进行配置。

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    WindowStyle="ToolWindow">
</Window>
```

#### <a name="non-rectangular-window-style"></a>非矩形窗口样式

在另外一些情况下，<xref:System.Windows.Window.WindowStyle%2A> 提供的边框样式不能满足需要。 例如，可能希望创建一个带有非矩形边框（如 Windows Media Player 所使用的边框）的应用程序。

下图中显示的对话气泡框就是一个例子：

:::image type="content" source="./media/index/window-transparent.png" alt-text="WPF 窗口的屏幕截图，其中包含已剪裁的区域和自定义形状。":::

可以通过将 <xref:System.Windows.Window.WindowStyle%2A> 属性设置为 <xref:System.Windows.WindowStyle.None>，并使用 <xref:System.Windows.Window> 为透明度提供的特殊支持，来创建这种类型的窗口。

:::code language="xaml" source="snippets/index/csharp/ClippedWindow.xaml":::

多个值组合起来可以指示窗口呈现透明的效果。 在此状态下，不能使用窗口的非工作区修饰按钮，而需要提供你自己的修饰按钮。

### <a name="task-bar-presence"></a>任务栏显示

窗口的默认外观包含一个任务栏按钮。 某些类型的窗口没有任务栏按钮，如消息框、[对话框](dialog-boxes-overview.md)或 <xref:System.Windows.Window.WindowStyle%2A> 属性设置为 <xref:System.Windows.WindowStyle.ToolWindow> 的窗口。 设置 <xref:System.Windows.Window.ShowInTaskbar%2A> 属性（默认为 `true`）可以控制是否显示窗口的任务栏按钮。

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    ShowInTaskbar="False">
</Window>
```

## <a name="other-types-of-windows"></a>其他类型的窗口

<xref:System.Windows.Navigation.NavigationWindow> 是设计用于托管可导航内容的窗口。<!-- For more information, see [Navigation Overview](navigation-overview.md)).-->

对话框是通常用来收集用户信息以完成某项功能的窗口。 例如，用户需要打开某个文件时，应用程序会显示“打开文件”对话框，以从用户那里获取文件名。 有关详细信息，请参阅[对话框概述](dialog-boxes-overview.md)。

## <a name="see-also"></a>另请参阅

- [对话框概述](dialog-boxes-overview.md)
- [如何打开窗口或对话框](how-to-open-window-dialog-box.md)
- [如何打开通用对话框](how-to-open-common-system-dialog-box.md)
- [如何打开消息框](how-to-open-message-box.md)
- [如何关闭窗口或对话框](how-to-close-window-dialog-box.md)
- <xref:System.Windows.Window?displayProperty=fullName>
- <xref:System.Windows.MessageBox?displayProperty=fullName>
- <xref:System.Windows.Navigation.NavigationWindow?displayProperty=fullName>
- <xref:System.Windows.Application?displayProperty=fullName>
