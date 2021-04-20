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
# <a name="overview-of-wpf-windows-wpf-net"></a><span data-ttu-id="c55f8-104">WPF 窗口概述 (WPF .NET)</span><span class="sxs-lookup"><span data-stu-id="c55f8-104">Overview of WPF windows (WPF .NET)</span></span>

<span data-ttu-id="c55f8-105">用户通过窗口与 Windows Presentation Foundation (WPF) 应用程序交互。</span><span class="sxs-lookup"><span data-stu-id="c55f8-105">Users interact with Windows Presentation Foundation (WPF) applications through windows.</span></span> <span data-ttu-id="c55f8-106">窗口的主要用途是托管使数据可视化并使用户能够与数据交互的内容。</span><span class="sxs-lookup"><span data-stu-id="c55f8-106">The primary purpose of a window is to host content that visualizes data and enables users to interact with data.</span></span> <span data-ttu-id="c55f8-107">WPF 应用程序使用 <xref:System.Windows.Window> 类提供自己的窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-107">WPF applications provide their own windows by using the <xref:System.Windows.Window> class.</span></span> <span data-ttu-id="c55f8-108">本文先介绍 <xref:System.Windows.Window>，然后讲述在应用程序中创建和管理窗口的基础知识。</span><span class="sxs-lookup"><span data-stu-id="c55f8-108">This article introduces <xref:System.Windows.Window> before covering the fundamentals of creating and managing windows in applications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c55f8-109">本文使用从 C# 项目生成的 XAML。</span><span class="sxs-lookup"><span data-stu-id="c55f8-109">This article uses XAML generated from a **C#** project.</span></span> <span data-ttu-id="c55f8-110">如果使用 Visual Basic，则 XAML 看上去可能有不同。</span><span class="sxs-lookup"><span data-stu-id="c55f8-110">If you're using **Visual Basic**, the XAML may look slightly different.</span></span> <span data-ttu-id="c55f8-111">这些差异通常出现在 `x:Class` 属性值上。</span><span class="sxs-lookup"><span data-stu-id="c55f8-111">These differences are typically present on `x:Class` attribute values.</span></span> <span data-ttu-id="c55f8-112">C# 包括项目的根命名空间，而 Visual Basic 不包括。</span><span class="sxs-lookup"><span data-stu-id="c55f8-112">C# includes the root namespace for the project while Visual Basic doesn't.</span></span>
>
> <span data-ttu-id="c55f8-113">C# 的项目模板创建了一个 `App` 类型，包含在 _app.xaml_ 文件中。</span><span class="sxs-lookup"><span data-stu-id="c55f8-113">The project templates for C# create an `App` type contained in the _app.xaml_ file.</span></span> <span data-ttu-id="c55f8-114">在 Visual Basic 中，该类型名为 `Application`，该文件名为 `Application.xaml`。</span><span class="sxs-lookup"><span data-stu-id="c55f8-114">In Visual Basic, the type is named `Application` and the file is named `Application.xaml`.</span></span>

## <a name="the-window-class"></a><span data-ttu-id="c55f8-115">窗口类</span><span class="sxs-lookup"><span data-stu-id="c55f8-115">The Window class</span></span>

<span data-ttu-id="c55f8-116">在 WPF 中，窗口由用于执行以下操作的 <xref:System.Windows.Window> 类封装：</span><span class="sxs-lookup"><span data-stu-id="c55f8-116">In WPF, a window is encapsulated by the <xref:System.Windows.Window> class that you use to do the following:</span></span>

- <span data-ttu-id="c55f8-117">显示窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-117">Display a window.</span></span>
- <span data-ttu-id="c55f8-118">配置窗口的大小、位置和外观。</span><span class="sxs-lookup"><span data-stu-id="c55f8-118">Configure the size, position, and appearance of a window.</span></span>
- <span data-ttu-id="c55f8-119">托管特定于应用程序的内容。</span><span class="sxs-lookup"><span data-stu-id="c55f8-119">Host application-specific content.</span></span>
- <span data-ttu-id="c55f8-120">管理窗口的生存期。</span><span class="sxs-lookup"><span data-stu-id="c55f8-120">Manage the lifetime of a window.</span></span>

<span data-ttu-id="c55f8-121">下图展示了窗口的构成部分：</span><span class="sxs-lookup"><span data-stu-id="c55f8-121">The following figure illustrates the constituent parts of a window:</span></span>

:::image type="content" source="./media/index/window-parts.png" alt-text="显示 WPF 窗口各部分的屏幕截图。":::

<span data-ttu-id="c55f8-123">窗口分为两个区域：非工作区和工作区。</span><span class="sxs-lookup"><span data-stu-id="c55f8-123">A window is divided into two areas: the non-client area and client area.</span></span>

<span data-ttu-id="c55f8-124">窗口的非工作区由 WPF实现，它包括大多数窗口所共有的窗口部分，包括：</span><span class="sxs-lookup"><span data-stu-id="c55f8-124">The *non-client area* of a window is implemented by WPF and includes the parts of a window that are common to most windows, including the following:</span></span>

- <span data-ttu-id="c55f8-125">标题栏 (1-5)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-125">A title bar (1-5).</span></span>
- <span data-ttu-id="c55f8-126">图标 (1)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-126">An icon (1).</span></span>
- <span data-ttu-id="c55f8-127">标题 (2)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-127">Title (2).</span></span>
- <span data-ttu-id="c55f8-128">最小化 (3)、最大化 (4) 和关闭 (5) 按钮。</span><span class="sxs-lookup"><span data-stu-id="c55f8-128">Minimize (3), Maximize (4), and Close (5) buttons.</span></span>
- <span data-ttu-id="c55f8-129">包含菜单项的系统菜单 (6)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-129">System menu (6) with menu items.</span></span> <span data-ttu-id="c55f8-130">单击图标 (1) 时出现。</span><span class="sxs-lookup"><span data-stu-id="c55f8-130">Appears when clicking on the icon (1).</span></span>
- <span data-ttu-id="c55f8-131">边框 (7)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-131">Border (7).</span></span>

<span data-ttu-id="c55f8-132">窗口的工作区是窗口的非工作区内部的区域，由开发人员用于添加特定于应用程序的内容，例如菜单栏、工具栏和控件。</span><span class="sxs-lookup"><span data-stu-id="c55f8-132">The *client area* of a window is the area within a window's non-client area and is used by developers to add application-specific content, such as menu bars, tool bars, and controls.</span></span>

- <span data-ttu-id="c55f8-133">工作区 (8)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-133">Client area (8).</span></span>
- <span data-ttu-id="c55f8-134">大小调整手柄 (9)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-134">Resize grip (9).</span></span> <span data-ttu-id="c55f8-135">这是添加到工作区 (8) 的控件。</span><span class="sxs-lookup"><span data-stu-id="c55f8-135">This is a control added to the Client area (8).</span></span>

## <a name="implementing-a-window"></a><span data-ttu-id="c55f8-136">实现窗口</span><span class="sxs-lookup"><span data-stu-id="c55f8-136">Implementing a window</span></span>

<span data-ttu-id="c55f8-137">典型窗口的实现既包括外观又包括行为，外观定义用户看到的窗口的样子，行为定义用户与之交互时窗口的运行方式。 </span><span class="sxs-lookup"><span data-stu-id="c55f8-137">The implementation of a typical window includes both appearance and behavior, where *appearance* defines how a window looks to users and *behavior* defines the way a window functions as users interact with it.</span></span> <span data-ttu-id="c55f8-138">在 WPF 中，可以使用代码或 XAML 标记实现窗口的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="c55f8-138">In WPF, you can implement the appearance and behavior of a window using either code or XAML markup.</span></span>

<span data-ttu-id="c55f8-139">但在一般情况下，窗口的外观使用 XAML 标记实现，行为使用代码隐藏实现，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="c55f8-139">In general, however, the appearance of a window is implemented using XAML markup, and its behavior is implemented using code-behind, as shown in the following example.</span></span>

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

<span data-ttu-id="c55f8-140">下面的代码是 XAML 的代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="c55f8-140">The following code is the code-behind for the XAML.</span></span>

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

<span data-ttu-id="c55f8-141">若要使 XAML 标记文件和代码隐藏文件配合工作，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="c55f8-141">To enable a XAML markup file and code-behind file to work together, the following are required:</span></span>

- <span data-ttu-id="c55f8-142">在标记中，`Window` 元素必须包含 `x:Class` 属性。</span><span class="sxs-lookup"><span data-stu-id="c55f8-142">In markup, the `Window` element must include the `x:Class` attribute.</span></span> <span data-ttu-id="c55f8-143">生成应用程序时，标记文件中存在 `x:Class` 会使 Microsoft 生成引擎 (MSBuild) 生成派生自 <xref:System.Windows.Window> 的 `partial` 类，其名称由 `x:Class` 属性指定。</span><span class="sxs-lookup"><span data-stu-id="c55f8-143">When the application is built, the existence of `x:Class` attribute causes Microsoft build engine (MSBuild) to generate a `partial` class that derives from <xref:System.Windows.Window> with the name that is specified by the `x:Class` attribute.</span></span> <span data-ttu-id="c55f8-144">这要求为 XAML 架构 (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`) 添加 XAML 命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="c55f8-144">This requires the addition of an XML namespace declaration for the XAML schema (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`).</span></span> <span data-ttu-id="c55f8-145">生成的 `partial` 类实现 `InitializeComponent` 方法，注册事件和设置在标记中实现的属性时将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="c55f8-145">The generated `partial` class implements the `InitializeComponent` method, which is called to register the events and set the properties that are implemented in markup.</span></span>

- <span data-ttu-id="c55f8-146">在代码隐藏中，类必须是 `partial` 类、名称必须是标记中 `x:Class` 属性指定的相同名称，并且它必须派生自 <xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="c55f8-146">In code-behind, the class must be a `partial` class with the same name that is specified by the `x:Class` attribute in markup, and it must derive from <xref:System.Windows.Window>.</span></span> <span data-ttu-id="c55f8-147">这样，代码隐藏文件就与应用程序生成时为标记文件生成的 `partial` 类相关联（请参阅[编译 WPF 应用程序](../../../framework/wpf/app-development/building-a-wpf-application-wpf.md)以了解详细信息）。</span><span class="sxs-lookup"><span data-stu-id="c55f8-147">This allows the code-behind file to be associated with the `partial` class that is generated for the markup file when the application is built, for more information, see [Compile a WPF Application](../../../framework/wpf/app-development/building-a-wpf-application-wpf.md).</span></span>

- <span data-ttu-id="c55f8-148">在代码隐藏中，<xref:System.Windows.Window> 类必须实现调用 `InitializeComponent` 方法的构造函数。</span><span class="sxs-lookup"><span data-stu-id="c55f8-148">In code-behind, the <xref:System.Windows.Window> class must implement a constructor that calls the `InitializeComponent` method.</span></span> <span data-ttu-id="c55f8-149">`InitializeComponent` 由标记文件已生成的 `partial` 类实现，用以注册事件并设置标记中定义的属性。</span><span class="sxs-lookup"><span data-stu-id="c55f8-149">`InitializeComponent` is implemented by the markup file's generated `partial` class to register events and set properties that are defined in markup.</span></span>

> [!NOTE]
> <span data-ttu-id="c55f8-150">使用 Visual Studio 将新的 <xref:System.Windows.Window> 添加到项目时，<xref:System.Windows.Window> 通过同时使用标记和代码隐藏实现，并且包括必要的配置来创建此处所述的标记文件和代码隐藏文件之间的关联。</span><span class="sxs-lookup"><span data-stu-id="c55f8-150">When you add a new <xref:System.Windows.Window> to your project by using Visual Studio, the <xref:System.Windows.Window> is implemented using both markup and code-behind, and includes the necessary configuration to create the association between the markup and code-behind files as described here.</span></span>

<span data-ttu-id="c55f8-151">进行了此配置后，可以专注于在 XAML 标记中定义窗口的外观，并可在代码隐藏中实现窗口的行为。</span><span class="sxs-lookup"><span data-stu-id="c55f8-151">With this configuration in place, you can focus on defining the appearance of the window in XAML markup and implementing its behavior in code-behind.</span></span> <span data-ttu-id="c55f8-152">以下示例显示了一个窗口，该窗口中的一个按钮定义了 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c55f8-152">The following example shows a window with a button that defines an event handler for the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span> <span data-ttu-id="c55f8-153">这是在 XAML 中实现的，处理程序是在代码隐藏中实现的。</span><span class="sxs-lookup"><span data-stu-id="c55f8-153">This is implemented in the XAML and the handler is implemented in code-behind.</span></span>

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

<span data-ttu-id="c55f8-154">下面的代码是 XAML 的代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="c55f8-154">The following code is the code-behind for the XAML.</span></span>

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

### <a name="configuring-a-window-for-msbuild"></a><span data-ttu-id="c55f8-155">为 MSBuild 配置窗口</span><span class="sxs-lookup"><span data-stu-id="c55f8-155">Configuring a window for MSBuild</span></span>

<span data-ttu-id="c55f8-156">实现窗口的方式决定为 MSBuild 配置窗口的方式。</span><span class="sxs-lookup"><span data-stu-id="c55f8-156">How you implement your window determines how it's configured for MSBuild.</span></span> <span data-ttu-id="c55f8-157">对于使用 XAML 标记和代码隐藏定义的窗口：</span><span class="sxs-lookup"><span data-stu-id="c55f8-157">For a window that is defined using both XAML markup and code-behind:</span></span>

- <span data-ttu-id="c55f8-158">XAML 标记文件配置为 MSBuild `Page` 项。</span><span class="sxs-lookup"><span data-stu-id="c55f8-158">XAML markup files are configured as MSBuild `Page` items.</span></span>
- <span data-ttu-id="c55f8-159">代码隐藏文件配置为 MSBuild `Compile` 项。</span><span class="sxs-lookup"><span data-stu-id="c55f8-159">Code-behind files are configured as MSBuild `Compile` items.</span></span>

<span data-ttu-id="c55f8-160">.NET SDK 项目会自动导入正确的 `Page` 和 `Compile` 项，无需对其进行声明。</span><span class="sxs-lookup"><span data-stu-id="c55f8-160">.NET SDK projects automatically import the correct `Page` and `Compile` items for you and you don't need to do declare these.</span></span> <span data-ttu-id="c55f8-161">如果为 WPF 配置了项目，则会将 XAML 标记文件自动导入为 `Page`，并将相应的代码隐藏文件导入为 `Compile`。</span><span class="sxs-lookup"><span data-stu-id="c55f8-161">When the project is configured for WPF, the XAML markup files are automatically imported as `Page` items, and the corresponding code-behind file is imported as `Compile`.</span></span>

<span data-ttu-id="c55f8-162">MSBuild 项目不会自动导入类型，你必须自行声明它们：</span><span class="sxs-lookup"><span data-stu-id="c55f8-162">MSBuild projects won't automatically import the types and you must declare them yourself:</span></span>

```xml
<Project>
    ...
    <Page Include="MarkupAndCodeBehindWindow.xaml" />
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />
    ...
</Project>
```

<span data-ttu-id="c55f8-163">有关生成 WPF 应用程序的信息，请参阅[编译 WPF 应用程序](../../../framework/wpf/app-development/building-a-wpf-application-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-163">For information about building WPF applications, see [Compile a WPF Application](../../../framework/wpf/app-development/building-a-wpf-application-wpf.md).</span></span>

## <a name="window-lifetime"></a><span data-ttu-id="c55f8-164">窗口生存期</span><span class="sxs-lookup"><span data-stu-id="c55f8-164">Window lifetime</span></span>

<span data-ttu-id="c55f8-165">与所有类一样，窗口也有生存期，开始于首次实例化窗口，在这之后将打开、激活/停用直至最终关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-165">As with any class, a window has a lifetime that begins when it's first instantiated, after which it's opened, activated/deactivated, and eventually closed.</span></span>

### <a name="opening-a-window"></a><span data-ttu-id="c55f8-166">打开窗口</span><span class="sxs-lookup"><span data-stu-id="c55f8-166">Opening a window</span></span>

<span data-ttu-id="c55f8-167">若要打开窗口，首先要创建窗口实例，下面的示例演示此操作：</span><span class="sxs-lookup"><span data-stu-id="c55f8-167">To open a window, you first create an instance of it, which is demonstrated in the following example:</span></span>

:::code language="csharp" source="snippets/index_2/csharp/App.xaml.cs":::
:::code language="vb" source="snippets/index_2/vb/Application.xaml.vb":::

<span data-ttu-id="c55f8-168">在本示例中，`Window1` 在应用程序启动时实例化，此过程在引发 <xref:System.Windows.Application.Startup> 事件时发生。</span><span class="sxs-lookup"><span data-stu-id="c55f8-168">In this example `Window1` is instantiated when the application starts, which occurs when the <xref:System.Windows.Application.Startup> event is raised.</span></span> <span data-ttu-id="c55f8-169">有关“启动”窗口的详细信息，请参阅[如何获取或设置主应用程序窗口](how-to-get-set-main-application-window.md)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-169">For more information about the startup window, see [How to get or set the main application window](how-to-get-set-main-application-window.md).</span></span>

<span data-ttu-id="c55f8-170">实例化窗口后，对其的引用将自动添加到由 <xref:System.Windows.Application> 对象管理的[窗口列表](xref:System.Windows.Application.Windows%2A)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-170">When a window is instantiated, a reference to it's automatically added to a [list of windows](xref:System.Windows.Application.Windows%2A) that is managed by the <xref:System.Windows.Application> object.</span></span> <span data-ttu-id="c55f8-171"><xref:System.Windows.Application> 会将要实例化的第一个窗口自动设置为[主应用程序窗口](xref:System.Windows.Application.MainWindow%2A)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-171">The first window to be instantiated is automatically set by <xref:System.Windows.Application> as the [main application window](xref:System.Windows.Application.MainWindow%2A).</span></span>

<span data-ttu-id="c55f8-172">最后通过调用 <xref:System.Windows.Window.Show%2A> 方法打开窗口，如以下图像所示：</span><span class="sxs-lookup"><span data-stu-id="c55f8-172">The window is finally opened by calling the <xref:System.Windows.Window.Show%2A> method as shown in the following image:</span></span>

:::image type="content" source="./media/index/window-with-button.png" alt-text="内含单个按钮的 WPF 窗口。":::

<span data-ttu-id="c55f8-174">通过调用 <xref:System.Windows.Window.Show%2A> 打开的窗口是无模式窗口，应用程序不会阻止用户与该应用程序中的其他窗口交互。</span><span class="sxs-lookup"><span data-stu-id="c55f8-174">A window that is opened by calling <xref:System.Windows.Window.Show%2A> is a _modeless_ window, and the application doesn't prevent users from interacting with other windows in the application.</span></span> <span data-ttu-id="c55f8-175">通过 <xref:System.Windows.Window.ShowDialog%2A> 打开窗口时，会将窗口打开为模式，并限制用户与该窗口交互。</span><span class="sxs-lookup"><span data-stu-id="c55f8-175">Opening a window with <xref:System.Windows.Window.ShowDialog%2A> opens a window as _modal_ and restricts user interaction to the specific window.</span></span> <span data-ttu-id="c55f8-176">有关详细信息，请参阅[对话框概述](dialog-boxes-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-176">For more information, see [Dialog Boxes Overview](dialog-boxes-overview.md).</span></span>

<span data-ttu-id="c55f8-177">调用 <xref:System.Windows.Window.Show%2A>时，窗口先执行初始化工作，然后显示窗口以建立让窗口可以接收用户输入的基础结构。</span><span class="sxs-lookup"><span data-stu-id="c55f8-177">When <xref:System.Windows.Window.Show%2A> is called, a window does initialization work before it's shown to establish infrastructure that allows it to receive user input.</span></span> <span data-ttu-id="c55f8-178">初始化窗口时，将引发 <xref:System.Windows.Window.SourceInitialized> 事件并显示窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-178">When the window is initialized, the <xref:System.Windows.Window.SourceInitialized> event is raised and the window is shown.</span></span>

<span data-ttu-id="c55f8-179">有关详细信息，请参阅[如何打开窗口或对话框](how-to-open-window-dialog-box.md)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-179">For more information, see [How to open a window or dialog box](how-to-open-window-dialog-box.md).</span></span>

#### <a name="startup-window"></a><span data-ttu-id="c55f8-180">启动窗口</span><span class="sxs-lookup"><span data-stu-id="c55f8-180">Startup window</span></span>

<span data-ttu-id="c55f8-181">上一个示例使用了 `Startup` 事件来运行显示初始应用程序窗口的代码。</span><span class="sxs-lookup"><span data-stu-id="c55f8-181">The previous example used the `Startup` event to run code that displayed the initial application window.</span></span> <span data-ttu-id="c55f8-182">作为快捷方式，请改用 <xref:System.Windows.Application.StartupUri%2A> 来指定应用程序中 XAML 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="c55f8-182">As a shortcut, instead use <xref:System.Windows.Application.StartupUri%2A> to specify the path to a XAML file in your application.</span></span> <span data-ttu-id="c55f8-183">应用程序将自动创建并显示由该属性指定的窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-183">The application automatically creates and displays the window specified by that property.</span></span>

:::code language="xaml" source="snippets/index/csharp/App.xaml" highlight="5":::

#### <a name="window-ownership"></a><span data-ttu-id="c55f8-184">窗口所有权</span><span class="sxs-lookup"><span data-stu-id="c55f8-184">Window ownership</span></span>

<span data-ttu-id="c55f8-185">使用 <xref:System.Windows.Window.Show%2A> 方法打开的窗口与创建它的窗口不具有隐式关系。</span><span class="sxs-lookup"><span data-stu-id="c55f8-185">A window that is opened by using the <xref:System.Windows.Window.Show%2A> method doesn't have an implicit relationship with the window that created it.</span></span> <span data-ttu-id="c55f8-186">用户可以与其中任意一个窗口独立交互，这意味着这两个窗口都可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c55f8-186">Users can interact with either window independently of the other, which means that either window can do the following:</span></span>

- <span data-ttu-id="c55f8-187">覆盖另一个窗口（除非其中一个窗口的 <xref:System.Windows.Window.Topmost%2A> 属性设置为 `true`）。</span><span class="sxs-lookup"><span data-stu-id="c55f8-187">Cover the other (unless one of the windows has its <xref:System.Windows.Window.Topmost%2A> property set to `true`).</span></span>
- <span data-ttu-id="c55f8-188">在不影响另一个窗口的情况下最小化、最大化和还原。</span><span class="sxs-lookup"><span data-stu-id="c55f8-188">Be minimized, maximized, and restored without affecting the other.</span></span>

<span data-ttu-id="c55f8-189">某些窗口要求与打开它们的窗口保持某种关系。</span><span class="sxs-lookup"><span data-stu-id="c55f8-189">Some windows require a relationship with the window that opens them.</span></span> <span data-ttu-id="c55f8-190">例如，集成开发环境 (IDE) 应用程序可能打开属性窗口和工具窗口，这些窗口的典型行为是覆盖创建它们的窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-190">For example, an Integrated Development Environment (IDE) application may open property windows and tool windows whose typical behavior is to cover the window that creates them.</span></span> <span data-ttu-id="c55f8-191">此外，此类窗口应始终与创建它们的窗口一起关闭、最小化、最大化和还原。</span><span class="sxs-lookup"><span data-stu-id="c55f8-191">Furthermore, such windows should always close, minimize, maximize, and restore in concert with the window that created them.</span></span> <span data-ttu-id="c55f8-192">可以通过让一个窗口拥有另一个窗口来建立这种关系，通过使用对所有者窗口的引用设置被拥有窗口的 <xref:System.Windows.Window.Owner%2A>  属性来实现。</span><span class="sxs-lookup"><span data-stu-id="c55f8-192">Such a relationship can be established by making one window *own* another, and is achieved by setting the <xref:System.Windows.Window.Owner%2A> property of the *owned window* with a reference to the *owner window*.</span></span> <span data-ttu-id="c55f8-193">下面的示例说明了这一点。</span><span class="sxs-lookup"><span data-stu-id="c55f8-193">This is shown in the following example.</span></span>

:::code language="csharp" source="snippets/index/csharp/ChildWindow1.xaml.cs" range="12-18":::
:::code language="vb" source="snippets/index/vb/ChildWindow1.xaml.vb" range="2-7":::

<span data-ttu-id="c55f8-194">建立所有权后：</span><span class="sxs-lookup"><span data-stu-id="c55f8-194">After ownership is established:</span></span>

- <span data-ttu-id="c55f8-195">被拥有的窗口可以通过检查其 <xref:System.Windows.Window.Owner%2A> 属性的值来引用它的所有者窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-195">The owned window can reference its owner window by inspecting the value of its <xref:System.Windows.Window.Owner%2A> property.</span></span>
- <span data-ttu-id="c55f8-196">所有者窗口可以通过检查其 <xref:System.Windows.Window.OwnedWindows%2A> 属性的值来发现它拥有的所有窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-196">The owner window can discover all the windows it owns by inspecting the value of its <xref:System.Windows.Window.OwnedWindows%2A> property.</span></span>

### <a name="window-activation"></a><span data-ttu-id="c55f8-197">窗口激活</span><span class="sxs-lookup"><span data-stu-id="c55f8-197">Window activation</span></span>

<span data-ttu-id="c55f8-198">第一次打开窗口时，它即成为活动窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-198">When a window is first opened, it becomes the active window.</span></span> <span data-ttu-id="c55f8-199">活动窗口是当前捕获用户输入（例如击键和鼠标单击）的窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-199">The _active window_ is the window that is currently capturing user input, such as key strokes and mouse clicks.</span></span> <span data-ttu-id="c55f8-200">当窗口处于活动状态时，它会引发 <xref:System.Windows.Window.Activated> 事件。</span><span class="sxs-lookup"><span data-stu-id="c55f8-200">When a window becomes active, it raises the <xref:System.Windows.Window.Activated> event.</span></span>

> [!NOTE]
> <span data-ttu-id="c55f8-201">第一次打开窗口时，只有当引发 <xref:System.Windows.Window.Activated> 后才会引发 <xref:System.Windows.FrameworkElement.Loaded> 和 <xref:System.Windows.Window.ContentRendered> 事件。</span><span class="sxs-lookup"><span data-stu-id="c55f8-201">When a window is first opened, the <xref:System.Windows.FrameworkElement.Loaded> and <xref:System.Windows.Window.ContentRendered> events are raised only after the <xref:System.Windows.Window.Activated> event is raised.</span></span> <span data-ttu-id="c55f8-202">记住这一点，在引发 <xref:System.Windows.Window.ContentRendered> 时，实际上就可认为窗口已打开。</span><span class="sxs-lookup"><span data-stu-id="c55f8-202">With this in mind, a window can effectively be considered opened when <xref:System.Windows.Window.ContentRendered> is raised.</span></span>

<span data-ttu-id="c55f8-203">某个窗口成为活动窗口后，用户可以在同一应用程序内激活其他窗口，或者激活其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="c55f8-203">After a window becomes active, a user can activate another window in the same application, or activate another application.</span></span> <span data-ttu-id="c55f8-204">发生这种情况时，将停用当前的活动窗口，并引发 <xref:System.Windows.Window.Deactivated> 事件。</span><span class="sxs-lookup"><span data-stu-id="c55f8-204">When that happens, the currently active window becomes deactivated and raises the <xref:System.Windows.Window.Deactivated> event.</span></span> <span data-ttu-id="c55f8-205">同样，如果用户选择当前停用的窗口，该窗口将再次成为活动窗口，并引发 <xref:System.Windows.Window.Activated> 事件。</span><span class="sxs-lookup"><span data-stu-id="c55f8-205">Likewise, when the user selects a currently deactivated window, the window becomes active again and <xref:System.Windows.Window.Activated> is raised.</span></span>

<span data-ttu-id="c55f8-206">处理 <xref:System.Windows.Window.Activated> 和 <xref:System.Windows.Window.Deactivated> 的一个常见原因是为了启用和禁用仅在窗口处于活动状态时才能够运行的功能。</span><span class="sxs-lookup"><span data-stu-id="c55f8-206">One common reason to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> is to enable and disable functionality that can only run when a window is active.</span></span> <span data-ttu-id="c55f8-207">例如，一些窗口显示需要用户持续输入或关注的交互式内容，这些内容包括游戏和视频播放器。</span><span class="sxs-lookup"><span data-stu-id="c55f8-207">For example, some windows display interactive content that requires constant user input or attention, including games and video players.</span></span> <span data-ttu-id="c55f8-208">以下示例是简化的视频播放器，展示如何处理 <xref:System.Windows.Window.Activated> 和 <xref:System.Windows.Window.Deactivated> 以实现此行为。</span><span class="sxs-lookup"><span data-stu-id="c55f8-208">The following example is a simplified video player that demonstrates how to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> to implement this behavior.</span></span>

:::code language="xaml" source="snippets/index/csharp/CustomMediaPlayerWindow.xaml":::

<span data-ttu-id="c55f8-209">下面的代码是 XAML 的代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="c55f8-209">The following code is the code-behind for the XAML.</span></span>

:::code language="csharp" source="snippets/index/csharp/CustomMediaPlayerWindow.xaml.cs":::
:::code language="vb" source="snippets/index/vb/CustomMediaPlayerWindow.xaml.vb":::

<span data-ttu-id="c55f8-210">停用某个窗口后，其他类型的应用程序可能仍会在后台运行代码。</span><span class="sxs-lookup"><span data-stu-id="c55f8-210">Other types of applications may still run code in the background when a window is deactivated.</span></span> <span data-ttu-id="c55f8-211">例如，在用户使用其他应用程序时，邮件客户端可能会继续轮询邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="c55f8-211">For example, a mail client may continue polling the mail server while the user is using other applications.</span></span> <span data-ttu-id="c55f8-212">类似的应用程序在主窗口停用时，通常将提供不同的或额外的行为。</span><span class="sxs-lookup"><span data-stu-id="c55f8-212">Applications like these often provide different or extra behavior while the main window is deactivated.</span></span> <span data-ttu-id="c55f8-213">对于邮件程序，这可能意味着将新邮件项添加到收件箱和将通知图标添加到系统任务栏。</span><span class="sxs-lookup"><span data-stu-id="c55f8-213">For a mail program, this may mean both adding the new mail item to the inbox and adding a notification icon to the system tray.</span></span> <span data-ttu-id="c55f8-214">仅当邮件窗口不处于活动状态时才显示通知图标，活动状态是通过检查 <xref:System.Windows.Window.IsActive%2A> 属性来确定的。</span><span class="sxs-lookup"><span data-stu-id="c55f8-214">A notification icon need only be displayed when the mail window isn't active, which is determined by inspecting the <xref:System.Windows.Window.IsActive%2A> property.</span></span>

<span data-ttu-id="c55f8-215">完成某个后台任务后，窗口可能需要通过调用 <xref:System.Windows.Window.Activate%2A> 方法来更迫切地通知用户。</span><span class="sxs-lookup"><span data-stu-id="c55f8-215">If a background task completes, a window may want to notify the user more urgently by calling <xref:System.Windows.Window.Activate%2A> method.</span></span> <span data-ttu-id="c55f8-216">如果在调用 <xref:System.Windows.Window.Activate%2A> 时，用户正与其他激活的应用程序进行交互，窗口的任务栏按钮会闪烁。</span><span class="sxs-lookup"><span data-stu-id="c55f8-216">If the user is interacting with another application activated when <xref:System.Windows.Window.Activate%2A> is called, the window's taskbar button flashes.</span></span> <span data-ttu-id="c55f8-217">但是，如果用户正在与当前应用程序交互，则调用 <xref:System.Windows.Window.Activate%2A> 会将窗口置于前景。</span><span class="sxs-lookup"><span data-stu-id="c55f8-217">However, if a user is interacting with the current application, calling <xref:System.Windows.Window.Activate%2A> will bring the window to the foreground.</span></span>

> [!NOTE]
> <span data-ttu-id="c55f8-218">可以使用 <xref:System.Windows.Application.Activated?displayProperty=nameWithType> 和 <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> 事件处理应用程序范围的激活。</span><span class="sxs-lookup"><span data-stu-id="c55f8-218">You can handle application-scope activation using the <xref:System.Windows.Application.Activated?displayProperty=nameWithType> and <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> events.</span></span>

#### <a name="preventing-window-activation"></a><span data-ttu-id="c55f8-219">防止窗口激活</span><span class="sxs-lookup"><span data-stu-id="c55f8-219">Preventing window activation</span></span>

<span data-ttu-id="c55f8-220">在一些情况下，不应在显示窗口时将其激活，例如聊天应用程序的对话窗口或电子邮件应用程序的通知窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-220">There are scenarios where windows shouldn't be activated when shown, such as conversation windows of a chat application or notification windows of an email application.</span></span>

<span data-ttu-id="c55f8-221">如果应用程序的窗口在显示时不应激活，可以在首次调用 <xref:System.Windows.Window.Show%2A> 方法之前，先将其 <xref:System.Windows.Window.ShowActivated%2A> 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c55f8-221">If your application has a window that shouldn't be activated when shown, you can set its <xref:System.Windows.Window.ShowActivated%2A> property to `false` before calling the <xref:System.Windows.Window.Show%2A> method for the first time.</span></span> <span data-ttu-id="c55f8-222">结果是：</span><span class="sxs-lookup"><span data-stu-id="c55f8-222">As a consequence:</span></span>

- <span data-ttu-id="c55f8-223">此窗口未激活。</span><span class="sxs-lookup"><span data-stu-id="c55f8-223">The window isn't activated.</span></span>
- <span data-ttu-id="c55f8-224">未引发窗口的 <xref:System.Windows.Window.Activated> 事件。</span><span class="sxs-lookup"><span data-stu-id="c55f8-224">The window's <xref:System.Windows.Window.Activated> event isn't raised.</span></span>
- <span data-ttu-id="c55f8-225">当前激活的窗口保持激活状态。</span><span class="sxs-lookup"><span data-stu-id="c55f8-225">The currently activated window remains activated.</span></span>

 <span data-ttu-id="c55f8-226">但是，只要用户通过单击工作区或非工作区激活了窗口，窗口就会变为激活状态。</span><span class="sxs-lookup"><span data-stu-id="c55f8-226">The window will become activated, however, as soon as the user activates it by clicking either the client or non-client area.</span></span> <span data-ttu-id="c55f8-227">在这种情况下：</span><span class="sxs-lookup"><span data-stu-id="c55f8-227">In this case:</span></span>

- <span data-ttu-id="c55f8-228">已激活窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-228">The window is activated.</span></span>
- <span data-ttu-id="c55f8-229">已引发窗口的 <xref:System.Windows.Window.Activated> 事件。</span><span class="sxs-lookup"><span data-stu-id="c55f8-229">The window's <xref:System.Windows.Window.Activated> event is raised.</span></span>
- <span data-ttu-id="c55f8-230">停用之前激活的窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-230">The previously activated window is deactivated.</span></span>
- <span data-ttu-id="c55f8-231">然后按照预期，响应用户操作引发窗口的 <xref:System.Windows.Window.Deactivated> 和 <xref:System.Windows.Window.Activated> 事件。</span><span class="sxs-lookup"><span data-stu-id="c55f8-231">The window's <xref:System.Windows.Window.Deactivated> and <xref:System.Windows.Window.Activated> events are then raised as expected in response to user actions.</span></span>

### <a name="closing-a-window"></a><span data-ttu-id="c55f8-232">关闭窗口</span><span class="sxs-lookup"><span data-stu-id="c55f8-232">Closing a window</span></span>

<span data-ttu-id="c55f8-233">窗口的生存期在用户关闭它时终止。</span><span class="sxs-lookup"><span data-stu-id="c55f8-233">The life of a window starts coming to an end when a user closes it.</span></span> <span data-ttu-id="c55f8-234">窗口关闭后，就不能再重新打开它。</span><span class="sxs-lookup"><span data-stu-id="c55f8-234">Once a window is closed, it can't be reopened.</span></span> <span data-ttu-id="c55f8-235">可以使用非工作区中的元素关闭窗口，这些元素包括：</span><span class="sxs-lookup"><span data-stu-id="c55f8-235">A window can be closed by using elements in the non-client area, including the following:</span></span>

- <span data-ttu-id="c55f8-236">“系统”菜单的“关闭”项。 </span><span class="sxs-lookup"><span data-stu-id="c55f8-236">The **Close** item of the **System** menu.</span></span>
- <span data-ttu-id="c55f8-237">按 <kbd>ALT+F4</kbd>。</span><span class="sxs-lookup"><span data-stu-id="c55f8-237">Pressing <kbd>ALT + F4</kbd>.</span></span>
- <span data-ttu-id="c55f8-238">按“关闭”按钮。</span><span class="sxs-lookup"><span data-stu-id="c55f8-238">Pressing the **Close** button.</span></span>
- <span data-ttu-id="c55f8-239">在模式窗口上，当按钮的 <xref:System.Windows.Controls.Button.IsCancel%2A> 属性设置为 `true` 时，按 <kbd>ESC</kbd>。</span><span class="sxs-lookup"><span data-stu-id="c55f8-239">Pressing <kbd>ESC</kbd> when a button has the <xref:System.Windows.Controls.Button.IsCancel%2A> property set to `true` on a modal window.</span></span>

 <span data-ttu-id="c55f8-240">可以向工作区提供关闭窗口的更多机制，较为常见的机制包括：</span><span class="sxs-lookup"><span data-stu-id="c55f8-240">You can provide more mechanisms to the client area to close a window, the more common of which include the following:</span></span>

- <span data-ttu-id="c55f8-241">“文件”菜单中的“退出”项，通常用于主应用程序窗口。 </span><span class="sxs-lookup"><span data-stu-id="c55f8-241">An **Exit** item in the **File** menu, typically for main application windows.</span></span>
- <span data-ttu-id="c55f8-242">“文件”菜单中的“关闭”项，通常位于辅助应用程序窗口中。 </span><span class="sxs-lookup"><span data-stu-id="c55f8-242">A **Close** item in the **File** menu, typically on a secondary application window.</span></span>
- <span data-ttu-id="c55f8-243">“取消”按钮，通常位于模式对话框中。</span><span class="sxs-lookup"><span data-stu-id="c55f8-243">A **Cancel** button, typically on a modal dialog box.</span></span>
- <span data-ttu-id="c55f8-244">“关闭”按钮，通常位于非模式对话框中。</span><span class="sxs-lookup"><span data-stu-id="c55f8-244">A **Close** button, typically on a modeless dialog box.</span></span>

<span data-ttu-id="c55f8-245">若要为响应其中一种自定义机制而关闭窗口，需要调用 <xref:System.Windows.Window.Close%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="c55f8-245">To close a window in response to one of these custom mechanisms, you need to call the <xref:System.Windows.Window.Close%2A> method.</span></span> <span data-ttu-id="c55f8-246">以下示例通过选择“文件”菜单上的“退出”来实现关闭窗口的功能。 </span><span class="sxs-lookup"><span data-stu-id="c55f8-246">The following example implements the ability to close a window by choosing **Exit** from a **File** menu.</span></span>

:::code language="xaml" source="snippets/index/csharp/ClosingWindow.xaml":::

<span data-ttu-id="c55f8-247">下面的代码是 XAML 的代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="c55f8-247">The following code is the code-behind for the XAML.</span></span>

:::code language="csharp" source="snippets/index/csharp/ClosingWindow.xaml.cs":::
:::code language="vb" source="snippets/index/vb/ClosingWindow.xaml.vb":::

> [!NOTE]
> <span data-ttu-id="c55f8-248">可将应用程序配置为在出现以下情况时自动关闭：主应用程序窗口关闭（请参阅 <xref:System.Windows.Application.MainWindow%2A>）或最后一个窗口关闭。</span><span class="sxs-lookup"><span data-stu-id="c55f8-248">An application can be configured to shut down automatically when either the main application window closes (see <xref:System.Windows.Application.MainWindow%2A>) or the last window closes.</span></span> <span data-ttu-id="c55f8-249">有关详细信息，请参阅 <xref:System.Windows.Application.ShutdownMode%2A>。</span><span class="sxs-lookup"><span data-stu-id="c55f8-249">For more information, see <xref:System.Windows.Application.ShutdownMode%2A>.</span></span>

<span data-ttu-id="c55f8-250">虽然窗口可通过非工作区和工作区中提供的机制显式关闭，但它也可能因为应用程序或 Windows 的其他部分中的行为而隐式关闭，行为包括：</span><span class="sxs-lookup"><span data-stu-id="c55f8-250">While a window can be explicitly closed through mechanisms provided in the non-client and client areas, a window can also be implicitly closed as a result of behavior in other parts of the application or Windows, including the following:</span></span>

- <span data-ttu-id="c55f8-251">用户注销或关闭 Windows。</span><span class="sxs-lookup"><span data-stu-id="c55f8-251">A user logs off or shuts down Windows.</span></span>
- <span data-ttu-id="c55f8-252">窗口的 <xref:System.Windows.Window.Owner%2A> 关闭。</span><span class="sxs-lookup"><span data-stu-id="c55f8-252">A window's <xref:System.Windows.Window.Owner%2A> closes.</span></span>
- <span data-ttu-id="c55f8-253">主应用程序窗口关闭且 <xref:System.Windows.Application.ShutdownMode%2A> 为 <xref:System.Windows.ShutdownMode.OnMainWindowClose>。</span><span class="sxs-lookup"><span data-stu-id="c55f8-253">The main application window is closed and <xref:System.Windows.Application.ShutdownMode%2A> is <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span></span>
- <span data-ttu-id="c55f8-254">调用 <xref:System.Windows.Application.Shutdown%2A>。</span><span class="sxs-lookup"><span data-stu-id="c55f8-254"><xref:System.Windows.Application.Shutdown%2A> is called.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c55f8-255">窗口在关闭后无法重新打开。</span><span class="sxs-lookup"><span data-stu-id="c55f8-255">A window can't be reopened after it's closed.</span></span>

#### <a name="cancel-window-closure"></a><span data-ttu-id="c55f8-256">取消关闭窗口</span><span class="sxs-lookup"><span data-stu-id="c55f8-256">Cancel window closure</span></span>

<span data-ttu-id="c55f8-257">窗口关闭时，会引发两个事件：<xref:System.Windows.Window.Closing> 和 <xref:System.Windows.Window.Closed>。</span><span class="sxs-lookup"><span data-stu-id="c55f8-257">When a window closes, it raises two events: <xref:System.Windows.Window.Closing> and <xref:System.Windows.Window.Closed>.</span></span>

<span data-ttu-id="c55f8-258"><xref:System.Windows.Window.Closing> 在窗口关闭前引发，并提供一种可以阻止窗口关闭的机制。</span><span class="sxs-lookup"><span data-stu-id="c55f8-258"><xref:System.Windows.Window.Closing> is raised before the window closes, and it provides a mechanism by which window closure can be prevented.</span></span> <span data-ttu-id="c55f8-259">阻止窗口关闭的一个常见原因是窗口内容包含修改的数据。</span><span class="sxs-lookup"><span data-stu-id="c55f8-259">One common reason to prevent window closure is if window content contains modified data.</span></span> <span data-ttu-id="c55f8-260">在这种情况下，处理 <xref:System.Windows.Window.Closing> 事件可以确定数据是否为已更新，如果已更新，询问用户是在不保存数据的情况下继续关闭窗口，还是取消关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-260">In this situation, the <xref:System.Windows.Window.Closing> event can be handled to determine whether data is dirty and, if so, to ask the user whether to either continue closing the window without saving the data or to cancel window closure.</span></span> <span data-ttu-id="c55f8-261">以下示例演示了处理 <xref:System.Windows.Window.Closing> 的关键方面。</span><span class="sxs-lookup"><span data-stu-id="c55f8-261">The following example shows the key aspects of handling <xref:System.Windows.Window.Closing>.</span></span>

:::code language="xaml" source="snippets/index/csharp/DataWindow.xaml":::

<span data-ttu-id="c55f8-262">下面的代码是 XAML 的代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="c55f8-262">The following code is the code-behind for the XAML.</span></span>

:::code language="csharp" source="snippets/index/csharp/DataWindow.xaml.cs":::
:::code language="vb" source="snippets/index/vb/DataWindow.xaml.vb":::

<span data-ttu-id="c55f8-263">向 <xref:System.Windows.Window.Closing> 事件处理程序传递 <xref:System.ComponentModel.CancelEventArgs>，它会实现 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 属性，将该属性设置为 `true` 以防止窗口关闭。</span><span class="sxs-lookup"><span data-stu-id="c55f8-263">The <xref:System.Windows.Window.Closing> event handler is passed a <xref:System.ComponentModel.CancelEventArgs>, which implements the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property that you set to `true` to prevent a window from closing.</span></span>

<span data-ttu-id="c55f8-264">如果未处理 <xref:System.Windows.Window.Closing>，或者已处理但未取消，窗口将关闭。</span><span class="sxs-lookup"><span data-stu-id="c55f8-264">If <xref:System.Windows.Window.Closing> isn't handled, or it's handled but not canceled, the window will close.</span></span> <span data-ttu-id="c55f8-265">在窗口真正关闭前，将引发 <xref:System.Windows.Window.Closed>。</span><span class="sxs-lookup"><span data-stu-id="c55f8-265">Just before a window actually closes, <xref:System.Windows.Window.Closed> is raised.</span></span> <span data-ttu-id="c55f8-266">此时，无法阻止窗口关闭。</span><span class="sxs-lookup"><span data-stu-id="c55f8-266">At this point, a window can't be prevented from closing.</span></span>

### <a name="window-lifetime-events"></a><span data-ttu-id="c55f8-267">窗口生存期事件</span><span class="sxs-lookup"><span data-stu-id="c55f8-267">Window lifetime events</span></span>

<span data-ttu-id="c55f8-268">下图显示窗口生存期中的主体事件的顺序：</span><span class="sxs-lookup"><span data-stu-id="c55f8-268">The following illustration shows the sequence of the principal events in the lifetime of a window:</span></span>

:::image type="content" source="./media/index/window-lifetime-events.png" alt-text="此图显示了窗口生存期内的事件。":::

<span data-ttu-id="c55f8-270">下图显示窗口（显示时没有激活）生存期中的主体事件的顺序（显示窗口之前将 <xref:System.Windows.Window.ShowActivated%2A> 设置为 `false`）：</span><span class="sxs-lookup"><span data-stu-id="c55f8-270">The following illustration shows the sequence of the principal events in the lifetime of a window that is shown without activation (<xref:System.Windows.Window.ShowActivated%2A> is set to `false` before the window is shown):</span></span>

:::image type="content" source="./media/index/window-lifetime-no-activation.png" alt-text="此图显示了不激活的情况下窗口生存期中的事件。":::

## <a name="window-location"></a><span data-ttu-id="c55f8-272">窗口位置</span><span class="sxs-lookup"><span data-stu-id="c55f8-272">Window location</span></span>

<span data-ttu-id="c55f8-273">当窗口打开时，它在相对于桌面的 x 和 y 维度中有一个位置。</span><span class="sxs-lookup"><span data-stu-id="c55f8-273">While a window is open, it has a location in the x and y dimensions relative to the desktop.</span></span> <span data-ttu-id="c55f8-274">可以通过检查 <xref:System.Windows.Window.Left%2A> 和 <xref:System.Windows.Window.Top%2A> 来确定此位置。</span><span class="sxs-lookup"><span data-stu-id="c55f8-274">This location can be determined by inspecting the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties, respectively.</span></span> <span data-ttu-id="c55f8-275">设置这些属性以更改窗口的位置。</span><span class="sxs-lookup"><span data-stu-id="c55f8-275">Set these properties to change the location of the window.</span></span>

<span data-ttu-id="c55f8-276">还可通过使用以下任一 <xref:System.Windows.WindowStartupLocation> 枚举值来设置 <xref:System.Windows.Window.WindowStartupLocation%2A> 属性，从而指定 <xref:System.Windows.Window> 首次出现时的初始位置：</span><span class="sxs-lookup"><span data-stu-id="c55f8-276">You can also specify the initial location of a <xref:System.Windows.Window> when it first appears by setting the <xref:System.Windows.Window.WindowStartupLocation%2A> property with one of the following <xref:System.Windows.WindowStartupLocation> enumeration values:</span></span>

- <span data-ttu-id="c55f8-277"><xref:System.Windows.WindowStartupLocation.CenterOwner>（默认值）</span><span class="sxs-lookup"><span data-stu-id="c55f8-277"><xref:System.Windows.WindowStartupLocation.CenterOwner> (default)</span></span>
- <xref:System.Windows.WindowStartupLocation.CenterScreen>
- <xref:System.Windows.WindowStartupLocation.Manual>

<span data-ttu-id="c55f8-278">如果将启动位置指定为 <xref:System.Windows.WindowStartupLocation.Manual>，并且未设置 <xref:System.Windows.Window.Left%2A> 和 <xref:System.Windows.Window.Top%2A> 属性，<xref:System.Windows.Window> 将要求操作系统指定其显示位置。</span><span class="sxs-lookup"><span data-stu-id="c55f8-278">If the startup location is specified as <xref:System.Windows.WindowStartupLocation.Manual>, and the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties have not been set, <xref:System.Windows.Window> will ask the operating system for a location to appear in.</span></span>

### <a name="topmost-windows-and-z-order"></a><span data-ttu-id="c55f8-279">最顶层窗口和 z 顺序</span><span class="sxs-lookup"><span data-stu-id="c55f8-279">Topmost windows and z-order</span></span>

<span data-ttu-id="c55f8-280">除了有 x 和 y 位置外，窗口还在 z 维度中有一个位置，该位置确定窗口相对于其他窗口的垂直位置。</span><span class="sxs-lookup"><span data-stu-id="c55f8-280">Besides having an x and y location, a window also has a location in the z dimension, which determines its vertical position with respect to other windows.</span></span> <span data-ttu-id="c55f8-281">它称为窗口的 z 顺序，并且有两种类型：正常 z 顺序和最顶层 z 顺序。 </span><span class="sxs-lookup"><span data-stu-id="c55f8-281">This is known as the window's z-order, and there are two types: **normal** z-order and **topmost** z-order.</span></span> <span data-ttu-id="c55f8-282">*正常 z 顺序* 中的窗口位置取决于窗口当前是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="c55f8-282">The location of a window in the *normal z-order* is determined by whether it's currently active or not.</span></span> <span data-ttu-id="c55f8-283">默认情况下，窗口位于正常 z 顺序中。</span><span class="sxs-lookup"><span data-stu-id="c55f8-283">By default, a window is located in the normal z-order.</span></span> <span data-ttu-id="c55f8-284">*最顶层 z 顺序* 中的窗口位置也取决于它当前是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="c55f8-284">The location of a window in the *topmost z-order* is also determined by whether it's currently active or not.</span></span> <span data-ttu-id="c55f8-285">此外，最顶层 z 顺序中的窗口始终位于正常 z 顺序中的窗口之上。</span><span class="sxs-lookup"><span data-stu-id="c55f8-285">Furthermore, windows in the topmost z-order are always located above windows in the normal z-order.</span></span> <span data-ttu-id="c55f8-286">窗口通过将其 <xref:System.Windows.Window.Topmost%2A> 属性设置为 `true` 来采用最顶层 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="c55f8-286">A window is located in the topmost z-order by setting its <xref:System.Windows.Window.Topmost%2A> property to `true`.</span></span>

<span data-ttu-id="c55f8-287">在每种 z 顺序类型中，当前的活动窗口显示在同一 z 顺序中所有其他窗口之上。</span><span class="sxs-lookup"><span data-stu-id="c55f8-287">Within each z-order type, the currently active window appears above all other windows in the same z-order.</span></span>

## <a name="window-size"></a><span data-ttu-id="c55f8-288">窗口大小</span><span class="sxs-lookup"><span data-stu-id="c55f8-288">Window size</span></span>

<span data-ttu-id="c55f8-289">除了拥有桌面位置外，窗口还有大小，大小由多个属性确定，包括各种宽度和高度属性以及 <xref:System.Windows.Window.SizeToContent%2A>。</span><span class="sxs-lookup"><span data-stu-id="c55f8-289">Besides having a desktop location, a window has a size that is determined by several properties, including the various width and height properties and <xref:System.Windows.Window.SizeToContent%2A>.</span></span>

<span data-ttu-id="c55f8-290"><xref:System.Windows.FrameworkElement.MinWidth%2A>、<xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 用于管理窗口在其生存期内可以具有的宽度范围。</span><span class="sxs-lookup"><span data-stu-id="c55f8-290"><xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.MaxWidth%2A> are used to manage the range of widths that a window can have during its lifetime.</span></span>

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    MinWidth="300" Width="400" MaxWidth="500">
</Window>
```

<span data-ttu-id="c55f8-291">窗口高度由 <xref:System.Windows.FrameworkElement.MinHeight%2A>、<xref:System.Windows.FrameworkElement.Height%2A> 和 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 管理。</span><span class="sxs-lookup"><span data-stu-id="c55f8-291">Window height is managed by <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, and <xref:System.Windows.FrameworkElement.MaxHeight%2A>.</span></span>

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    MinHeight="300" Height="400" MaxHeight="500">
</Window>
```

<span data-ttu-id="c55f8-292">由于各种宽度值和高度值各自指定了一个范围，所以大小可调整大小的窗口的宽度和高度可以是相应维度中指定范围内的任何值。</span><span class="sxs-lookup"><span data-stu-id="c55f8-292">Because the various width values and height values each specify a range, it's possible for the width and height of a resizable window to be anywhere within the specified range for the respective dimension.</span></span> <span data-ttu-id="c55f8-293">若要检测其当前的宽度和高度，请分别检查 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 和 <xref:System.Windows.FrameworkElement.ActualHeight%2A>。</span><span class="sxs-lookup"><span data-stu-id="c55f8-293">To detect its current width and height, inspect <xref:System.Windows.FrameworkElement.ActualWidth%2A> and <xref:System.Windows.FrameworkElement.ActualHeight%2A>, respectively.</span></span>

 <span data-ttu-id="c55f8-294">如果希望窗口的宽度和高度适应窗口内容的大小，可以使用 <xref:System.Windows.Window.SizeToContent%2A> 属性，它具有以下值：</span><span class="sxs-lookup"><span data-stu-id="c55f8-294">If you'd like the width and height of your window to have a size that fits to the size of the window's content, you can use the <xref:System.Windows.Window.SizeToContent%2A> property, which has the following values:</span></span>

- <span data-ttu-id="c55f8-295">[SizeToContent.Manual](xref:System.Windows.SizeToContent.Manual)</span><span class="sxs-lookup"><span data-stu-id="c55f8-295">[SizeToContent.Manual](xref:System.Windows.SizeToContent.Manual)</span></span>\
<span data-ttu-id="c55f8-296">不起作用（默认值）。</span><span class="sxs-lookup"><span data-stu-id="c55f8-296">No effect (default).</span></span>
- <span data-ttu-id="c55f8-297">[SizeToContent.Width](xref:System.Windows.SizeToContent.Width)</span><span class="sxs-lookup"><span data-stu-id="c55f8-297">[SizeToContent.Width](xref:System.Windows.SizeToContent.Width)</span></span>\
<span data-ttu-id="c55f8-298">适应内容宽度，与将 <xref:System.Windows.FrameworkElement.MinWidth%2A> 和 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 都设置为内容的宽度效果相同。</span><span class="sxs-lookup"><span data-stu-id="c55f8-298">Fit to content width, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>
- <span data-ttu-id="c55f8-299">[SizeToContent.Height](xref:System.Windows.SizeToContent.Height)</span><span class="sxs-lookup"><span data-stu-id="c55f8-299">[SizeToContent.Height](xref:System.Windows.SizeToContent.Height)</span></span>\
<span data-ttu-id="c55f8-300">适应内容高度，与将 <xref:System.Windows.FrameworkElement.MinHeight%2A> 和 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 都设置为内容的高度效果相同。</span><span class="sxs-lookup"><span data-stu-id="c55f8-300">Fit to content height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content.</span></span>
- <span data-ttu-id="c55f8-301">[SizeToContent.WidthAndHeight](xref:System.Windows.SizeToContent.WidthAndHeight)</span><span class="sxs-lookup"><span data-stu-id="c55f8-301">[SizeToContent.WidthAndHeight](xref:System.Windows.SizeToContent.WidthAndHeight)</span></span>\
<span data-ttu-id="c55f8-302">适应内容宽度和高度，与将 <xref:System.Windows.FrameworkElement.MinHeight%2A> 和 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 都设置为内容的高度，并将 <xref:System.Windows.FrameworkElement.MinWidth%2A> 和 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 都设置为内容的宽度效果相同。</span><span class="sxs-lookup"><span data-stu-id="c55f8-302">Fit to content width and height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content, and setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>

<span data-ttu-id="c55f8-303">以下示例显示了一个窗口，它在第一次显示时即自动调整垂直方向和水平方向上的大小以适应内容。</span><span class="sxs-lookup"><span data-stu-id="c55f8-303">The following example shows a window that automatically sizes to fit its content, both vertically and horizontally, when first shown.</span></span>

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
    SizeToContent="WidthAndHeight">
</Window>
```

<span data-ttu-id="c55f8-304">以下示例显示如何在代码中设置 <xref:System.Windows.Window.SizeToContent%2A> 属性以指定重设窗口大小使其适应内容的方式。</span><span class="sxs-lookup"><span data-stu-id="c55f8-304">The following example shows how to set the <xref:System.Windows.Window.SizeToContent%2A> property in code to specify how a window resizes to fit its content    .</span></span>

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

## <a name="order-of-precedence-for-sizing-properties"></a><span data-ttu-id="c55f8-305">大小调整属性的优先级顺序</span><span class="sxs-lookup"><span data-stu-id="c55f8-305">Order of precedence for sizing properties</span></span>

<span data-ttu-id="c55f8-306">从根本上说，窗口的各种大小属性可以结合使用，以定义可调整大小的窗口的宽度和高度范围。</span><span class="sxs-lookup"><span data-stu-id="c55f8-306">Essentially, the various sizes properties of a window combine to define the range of width and height for a resizable window.</span></span> <span data-ttu-id="c55f8-307">为了确保保持有效的范围，<xref:System.Windows.Window> 将使用以下优先级顺序计算大小属性的值。</span><span class="sxs-lookup"><span data-stu-id="c55f8-307">To ensure a valid range is maintained, <xref:System.Windows.Window> evaluates the values of the size properties using the following orders of precedence.</span></span>

<span data-ttu-id="c55f8-308">**对于高度属性：**</span><span class="sxs-lookup"><span data-stu-id="c55f8-308">**For Height Properties:**</span></span>

01. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
01. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
01. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType> / <xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
01. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>

<span data-ttu-id="c55f8-309">**对于宽度属性：**</span><span class="sxs-lookup"><span data-stu-id="c55f8-309">**For Width Properties:**</span></span>

01. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
01. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
01. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType> / <xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
01. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>

<span data-ttu-id="c55f8-310">优先级顺序还可以确定窗口在最大化时的大小，此时的窗口大小由 <xref:System.Windows.Window.WindowState%2A> 属性管理。</span><span class="sxs-lookup"><span data-stu-id="c55f8-310">The order of precedence can also determine the size of a window when it's maximized, which is managed with the <xref:System.Windows.Window.WindowState%2A> property.</span></span>

## <a name="window-state"></a><span data-ttu-id="c55f8-311">窗口状态</span><span class="sxs-lookup"><span data-stu-id="c55f8-311">Window state</span></span>

<span data-ttu-id="c55f8-312">可调整大小的窗口在生存期中拥有三种状态：正常、最小化和最大化。</span><span class="sxs-lookup"><span data-stu-id="c55f8-312">During the lifetime of a resizable window, it can have three states: normal, minimized, and maximized.</span></span> <span data-ttu-id="c55f8-313">_正常_ 是窗口的默认状态。</span><span class="sxs-lookup"><span data-stu-id="c55f8-313">A window with a _normal_ state is the default state of a window.</span></span> <span data-ttu-id="c55f8-314">这种状态下的窗口允许用户使用重设大小手柄或边框移动窗口和重设其大小（前提是大小可以重设）。</span><span class="sxs-lookup"><span data-stu-id="c55f8-314">A window with this state allows a user to move and resize it by using a resize grip or the border, if it's resizable.</span></span>

<span data-ttu-id="c55f8-315">如果 <xref:System.Windows.Window.ShowInTaskbar%2A> 设置为 `true`，则最小化状态下的窗口将折叠到任务栏按钮；否则，它将尽可能折叠到最小大小，并将自己移动到桌面的左下角。</span><span class="sxs-lookup"><span data-stu-id="c55f8-315">A window with a *minimized* state collapses to its task bar button if <xref:System.Windows.Window.ShowInTaskbar%2A> is set to `true`; otherwise, it collapses to the smallest possible size it can be and moves itself to the bottom-left corner of the desktop.</span></span> <span data-ttu-id="c55f8-316">虽然不在任务栏显示的最小化窗口可以在桌面上四处拖动，但这两种类型的最小化窗口都不可以使用边框或重设大小手柄重设窗口大小。</span><span class="sxs-lookup"><span data-stu-id="c55f8-316">Neither type of minimized window can be resized using a border or resize grip, although a minimized window that isn't shown in the task bar can be dragged around the desktop.</span></span>

<span data-ttu-id="c55f8-317">具有最大化状态的窗口会扩展到它能具有的最大大小，这不能超过 <xref:System.Windows.FrameworkElement.MaxWidth%2A>、<xref:System.Windows.FrameworkElement.MaxHeight%2A> 和 <xref:System.Windows.Window.SizeToContent%2A> 属性指定的大小。</span><span class="sxs-lookup"><span data-stu-id="c55f8-317">A window with a *maximized* state expands to the maximum size it can be, which will only be as large as its <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.Window.SizeToContent%2A> properties dictate.</span></span> <span data-ttu-id="c55f8-318">与最小化窗口一样，最大化窗口无法使用重设大小手柄或通过拖动边框来重设大小。</span><span class="sxs-lookup"><span data-stu-id="c55f8-318">Like a minimized window, a maximized window can't be resized by using a resize grip or by dragging the border.</span></span>

> [!NOTE]
> <span data-ttu-id="c55f8-319">即使窗口当前已最大化或最小化，窗口的 <xref:System.Windows.Window.Top%2A>、<xref:System.Windows.Window.Left%2A>、<xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A> 属性的值也始终表示正常状态的值。</span><span class="sxs-lookup"><span data-stu-id="c55f8-319">The values of the <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.Height%2A> properties of a window always represent the values for the normal state, even when the window is currently maximized or minimized.</span></span>

 <span data-ttu-id="c55f8-320">可以通过设置 <xref:System.Windows.Window.WindowState%2A> 属性来配置窗口的状态，该属性可以具有以下 <xref:System.Windows.WindowState> 枚举值之一：</span><span class="sxs-lookup"><span data-stu-id="c55f8-320">The state of a window can be configured by setting its <xref:System.Windows.Window.WindowState%2A> property, which can have one of the following <xref:System.Windows.WindowState> enumeration values:</span></span>

- <span data-ttu-id="c55f8-321"><xref:System.Windows.WindowState.Normal>（默认值）</span><span class="sxs-lookup"><span data-stu-id="c55f8-321"><xref:System.Windows.WindowState.Normal> (default)</span></span>
- <xref:System.Windows.WindowState.Maximized>
- <xref:System.Windows.WindowState.Minimized>

<span data-ttu-id="c55f8-322">以下示例显示如何创建在打开时最大化显示的窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-322">The following example shows how to create a window that is shown as maximized when it opens.</span></span>

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    WindowState="Maximized">
</Window>
```

<span data-ttu-id="c55f8-323">通常，应设置 <xref:System.Windows.Window.WindowState%2A> 以配置窗口的初始状态。</span><span class="sxs-lookup"><span data-stu-id="c55f8-323">In general, you should set <xref:System.Windows.Window.WindowState%2A> to configure the initial state of a window.</span></span> <span data-ttu-id="c55f8-324">显示可调整大小的窗口后，用户可以按窗口标题栏上的“最小化”、“最大化”和“还原”按钮来更改窗口状态。</span><span class="sxs-lookup"><span data-stu-id="c55f8-324">Once a _resizable_ window is shown, users can press the minimize, maximize, and restore buttons on the window's title bar to change the window state.</span></span>

## <a name="window-appearance"></a><span data-ttu-id="c55f8-325">窗口外观</span><span class="sxs-lookup"><span data-stu-id="c55f8-325">Window appearance</span></span>

<span data-ttu-id="c55f8-326">通过将特定于窗口的内容（例如按钮、标签和文本框）添加到窗口的工作区可以更改它的外观。</span><span class="sxs-lookup"><span data-stu-id="c55f8-326">You change the appearance of the client area of a window by adding window-specific content to it, such as buttons, labels, and text boxes.</span></span> <span data-ttu-id="c55f8-327">为配置非工作区，<xref:System.Windows.Window> 提供几个属性，包括用于设置窗口图标的 <xref:System.Windows.Window.Icon%2A> 和用于设置其标题的 <xref:System.Windows.Window.Title%2A>。</span><span class="sxs-lookup"><span data-stu-id="c55f8-327">To configure the non-client area, <xref:System.Windows.Window> provides several properties, which include <xref:System.Windows.Window.Icon%2A> to set a window's icon and <xref:System.Windows.Window.Title%2A> to set its title.</span></span>

<span data-ttu-id="c55f8-328">还可以通过配置窗口的重设大小模式、窗口样式，以及窗口是否显示为桌面任务栏中的按钮，更改非工作区边框的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="c55f8-328">You can also change the appearance and behavior of non-client area border by configuring a window's resize mode, window style, and whether it appears as a button in the desktop task bar.</span></span>

### <a name="resize-mode"></a><span data-ttu-id="c55f8-329">重设大小模式</span><span class="sxs-lookup"><span data-stu-id="c55f8-329">Resize mode</span></span>

<span data-ttu-id="c55f8-330">根据 <xref:System.Windows.Window.WindowStyle%2A> 属性，你可以控制用户是否可以重设窗口的大小，以及如何重设。</span><span class="sxs-lookup"><span data-stu-id="c55f8-330">Depending on the <xref:System.Windows.Window.WindowStyle%2A> property, you can control if, and how, users resize the window.</span></span> <span data-ttu-id="c55f8-331">窗口样式影响以下各项：</span><span class="sxs-lookup"><span data-stu-id="c55f8-331">The window style affects the following:</span></span>

- <span data-ttu-id="c55f8-332">允许或禁止使用鼠标拖动窗口边框来调整大小。</span><span class="sxs-lookup"><span data-stu-id="c55f8-332">Allow or disallow resizing by dragging the window border with the mouse.</span></span>
- <span data-ttu-id="c55f8-333">非工作区是否显示“最小化”、“最大化”和“关闭”按钮。  </span><span class="sxs-lookup"><span data-stu-id="c55f8-333">Whether the **Minimize**, **Maximize**, and **Close** buttons appear on the non-client area.</span></span>
- <span data-ttu-id="c55f8-334">是否启用了“最小化”、“最大化”和“关闭”按钮。  </span><span class="sxs-lookup"><span data-stu-id="c55f8-334">Whether the **Minimize**, **Maximize**, and **Close** buttons are enabled.</span></span>

<span data-ttu-id="c55f8-335">可以通过设置窗口的 <xref:System.Windows.Window.ResizeMode%2A> 属性来配置重设窗口大小的方式，该属性可以是下列 <xref:System.Windows.ResizeMode> 枚举值之一：</span><span class="sxs-lookup"><span data-stu-id="c55f8-335">You can configure how a window resizes by setting its <xref:System.Windows.Window.ResizeMode%2A> property, which can be one of the following <xref:System.Windows.ResizeMode> enumeration values:</span></span>

- <xref:System.Windows.ResizeMode.NoResize>
- <xref:System.Windows.ResizeMode.CanMinimize>
- <span data-ttu-id="c55f8-336"><xref:System.Windows.ResizeMode.CanResize>（默认值）</span><span class="sxs-lookup"><span data-stu-id="c55f8-336"><xref:System.Windows.ResizeMode.CanResize> (default)</span></span>
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>

<span data-ttu-id="c55f8-337">与 <xref:System.Windows.Window.WindowStyle%2A> 一样，窗口的重设大小模式在生存期中不太可能更改，这意味着它最有可能在 XAML 标记中进行设置。</span><span class="sxs-lookup"><span data-stu-id="c55f8-337">As with <xref:System.Windows.Window.WindowStyle%2A>, the resize mode of a window is unlikely to change during its lifetime, which means that you'll most likely set it from XAML markup.</span></span>

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    ResizeMode="CanResizeWithGrip">
</Window>
```

<span data-ttu-id="c55f8-338">请注意，可以通过检查 <xref:System.Windows.Window.WindowState%2A> 属性来检测是否已最大化、最小化或还原窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-338">Note that you can detect whether a window is maximized, minimized, or restored by inspecting the <xref:System.Windows.Window.WindowState%2A> property.</span></span>

### <a name="window-style"></a><span data-ttu-id="c55f8-339">窗口样式</span><span class="sxs-lookup"><span data-stu-id="c55f8-339">Window style</span></span>

<span data-ttu-id="c55f8-340">从窗口非工作区公开的边框适用于大多数应用程序。</span><span class="sxs-lookup"><span data-stu-id="c55f8-340">The border that is exposed from the non-client area of a window is suitable for most applications.</span></span> <span data-ttu-id="c55f8-341">但是，有时候会需要不同类型的边框，或者根本不需要边框，具体取决于窗口类型。</span><span class="sxs-lookup"><span data-stu-id="c55f8-341">However, there are circumstances where different types of borders are needed, or no borders are needed at all, depending on the type of window.</span></span>

<span data-ttu-id="c55f8-342">若要控制窗口的边框类型，请将其 <xref:System.Windows.Window.WindowStyle%2A> 属性设置为以下 <xref:System.Windows.WindowStyle> 枚举值之一：</span><span class="sxs-lookup"><span data-stu-id="c55f8-342">To control what type of border a window gets, you set its <xref:System.Windows.Window.WindowStyle%2A> property with one of the following values of the <xref:System.Windows.WindowStyle> enumeration:</span></span>

- <xref:System.Windows.WindowStyle.None>
- <span data-ttu-id="c55f8-343"><xref:System.Windows.WindowStyle.SingleBorderWindow>（默认值）</span><span class="sxs-lookup"><span data-stu-id="c55f8-343"><xref:System.Windows.WindowStyle.SingleBorderWindow> (default)</span></span>
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>
- <xref:System.Windows.WindowStyle.ToolWindow>

<span data-ttu-id="c55f8-344">应用窗口样式的效果如下图所示：</span><span class="sxs-lookup"><span data-stu-id="c55f8-344">The effect of applying a window style is illustrated in the following image:</span></span>

:::image type="content" source="./media/index/window-styles.png" alt-text="此屏幕截图显示了 WindowStyle 如何影响 WPF 中的窗口。":::

<span data-ttu-id="c55f8-346">请注意，上图未显示 `SingleBorderWindow` 与 `ThreeDBorderWindow` 之间的任何明显差异。</span><span class="sxs-lookup"><span data-stu-id="c55f8-346">Notice that the image above doesn't show any noticeable difference between `SingleBorderWindow` and `ThreeDBorderWindow`.</span></span> <span data-ttu-id="c55f8-347">回到 Windows XP 中，`ThreeDBorderWindow` 确实会影响窗口的绘制方式，将三维边框添加到工作区。</span><span class="sxs-lookup"><span data-stu-id="c55f8-347">Back in Windows XP, `ThreeDBorderWindow` did affect how the window was drawn, adding a 3D border to the client area.</span></span> <span data-ttu-id="c55f8-348">从 Windows 7 开始，这两种样式之间的差异很小。</span><span class="sxs-lookup"><span data-stu-id="c55f8-348">Starting with Windows 7, the differences between the two styles are minimal.</span></span>

<span data-ttu-id="c55f8-349">可以使用 XAML 标记或代码设置 <xref:System.Windows.Window.WindowStyle%2A>。</span><span class="sxs-lookup"><span data-stu-id="c55f8-349">You can set <xref:System.Windows.Window.WindowStyle%2A> using either XAML markup or code.</span></span> <span data-ttu-id="c55f8-350">由于在窗口生存期内不太可能发生更改，因此你最有可能使用 XAML 标记对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="c55f8-350">Because it's unlikely to change during the lifetime of a window, you'll most likely configure it using XAML markup.</span></span>

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    WindowStyle="ToolWindow">
</Window>
```

#### <a name="non-rectangular-window-style"></a><span data-ttu-id="c55f8-351">非矩形窗口样式</span><span class="sxs-lookup"><span data-stu-id="c55f8-351">Non-rectangular window style</span></span>

<span data-ttu-id="c55f8-352">在另外一些情况下，<xref:System.Windows.Window.WindowStyle%2A> 提供的边框样式不能满足需要。</span><span class="sxs-lookup"><span data-stu-id="c55f8-352">There are also situations where the border styles that <xref:System.Windows.Window.WindowStyle%2A> allows you to have aren't sufficient.</span></span> <span data-ttu-id="c55f8-353">例如，可能希望创建一个带有非矩形边框（如 Windows Media Player 所使用的边框）的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c55f8-353">For example, you may want to create an application with a non-rectangular border, like Microsoft Windows Media Player uses.</span></span>

<span data-ttu-id="c55f8-354">下图中显示的对话气泡框就是一个例子：</span><span class="sxs-lookup"><span data-stu-id="c55f8-354">For example, consider the speech bubble window shown in the following image:</span></span>

:::image type="content" source="./media/index/window-transparent.png" alt-text="WPF 窗口的屏幕截图，其中包含已剪裁的区域和自定义形状。":::

<span data-ttu-id="c55f8-356">可以通过将 <xref:System.Windows.Window.WindowStyle%2A> 属性设置为 <xref:System.Windows.WindowStyle.None>，并使用 <xref:System.Windows.Window> 为透明度提供的特殊支持，来创建这种类型的窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-356">This type of window can be created by setting the <xref:System.Windows.Window.WindowStyle%2A> property to <xref:System.Windows.WindowStyle.None>, and by using special support that <xref:System.Windows.Window> has for transparency.</span></span>

:::code language="xaml" source="snippets/index/csharp/ClippedWindow.xaml":::

<span data-ttu-id="c55f8-357">多个值组合起来可以指示窗口呈现透明的效果。</span><span class="sxs-lookup"><span data-stu-id="c55f8-357">This combination of values instructs the window to render transparent.</span></span> <span data-ttu-id="c55f8-358">在此状态下，不能使用窗口的非工作区修饰按钮，而需要提供你自己的修饰按钮。</span><span class="sxs-lookup"><span data-stu-id="c55f8-358">In this state, the window's non-client area adornment buttons can't be used and you need to provide your own.</span></span>

### <a name="task-bar-presence"></a><span data-ttu-id="c55f8-359">任务栏显示</span><span class="sxs-lookup"><span data-stu-id="c55f8-359">Task bar presence</span></span>

<span data-ttu-id="c55f8-360">窗口的默认外观包含一个任务栏按钮。</span><span class="sxs-lookup"><span data-stu-id="c55f8-360">The default appearance of a window includes a taskbar button.</span></span> <span data-ttu-id="c55f8-361">某些类型的窗口没有任务栏按钮，如消息框、[对话框](dialog-boxes-overview.md)或 <xref:System.Windows.Window.WindowStyle%2A> 属性设置为 <xref:System.Windows.WindowStyle.ToolWindow> 的窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-361">Some types of windows don't have a task bar button, such as message boxes, [dialog boxes](dialog-boxes-overview.md), or windows with the <xref:System.Windows.Window.WindowStyle%2A> property set to <xref:System.Windows.WindowStyle.ToolWindow>.</span></span> <span data-ttu-id="c55f8-362">设置 <xref:System.Windows.Window.ShowInTaskbar%2A> 属性（默认为 `true`）可以控制是否显示窗口的任务栏按钮。</span><span class="sxs-lookup"><span data-stu-id="c55f8-362">You can control whether the task bar button for a window is shown by setting the <xref:System.Windows.Window.ShowInTaskbar%2A> property, which is `true` by default.</span></span>

```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    ShowInTaskbar="False">
</Window>
```

## <a name="other-types-of-windows"></a><span data-ttu-id="c55f8-363">其他类型的窗口</span><span class="sxs-lookup"><span data-stu-id="c55f8-363">Other types of windows</span></span>

<span data-ttu-id="c55f8-364"><xref:System.Windows.Navigation.NavigationWindow> 是设计用于托管可导航内容的窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-364"><xref:System.Windows.Navigation.NavigationWindow> is a window that is designed to host navigable content.</span></span><!-- For more information, see [Navigation Overview](navigation-overview.md)).-->

<span data-ttu-id="c55f8-365">对话框是通常用来收集用户信息以完成某项功能的窗口。</span><span class="sxs-lookup"><span data-stu-id="c55f8-365">Dialog boxes are windows that are often used to gather information from a user to complete a function.</span></span> <span data-ttu-id="c55f8-366">例如，用户需要打开某个文件时，应用程序会显示“打开文件”对话框，以从用户那里获取文件名。</span><span class="sxs-lookup"><span data-stu-id="c55f8-366">For example, when a user wants to open a file, the **Open File** dialog box is displayed by an application to get the file name from the user.</span></span> <span data-ttu-id="c55f8-367">有关详细信息，请参阅[对话框概述](dialog-boxes-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-367">For more information, see [Dialog Boxes Overview](dialog-boxes-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c55f8-368">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c55f8-368">See also</span></span>

- [<span data-ttu-id="c55f8-369">对话框概述</span><span class="sxs-lookup"><span data-stu-id="c55f8-369">Dialog boxes overview</span></span>](dialog-boxes-overview.md)
- [<span data-ttu-id="c55f8-370">如何打开窗口或对话框</span><span class="sxs-lookup"><span data-stu-id="c55f8-370">How to open a window or dialog box</span></span>](how-to-open-window-dialog-box.md)
- [<span data-ttu-id="c55f8-371">如何打开通用对话框</span><span class="sxs-lookup"><span data-stu-id="c55f8-371">How to open a common dialog box</span></span>](how-to-open-common-system-dialog-box.md)
- [<span data-ttu-id="c55f8-372">如何打开消息框</span><span class="sxs-lookup"><span data-stu-id="c55f8-372">How to open a message box</span></span>](how-to-open-message-box.md)
- [<span data-ttu-id="c55f8-373">如何关闭窗口或对话框</span><span class="sxs-lookup"><span data-stu-id="c55f8-373">How to close a window or dialog box</span></span>](how-to-close-window-dialog-box.md)
- <xref:System.Windows.Window?displayProperty=fullName>
- <xref:System.Windows.MessageBox?displayProperty=fullName>
- <xref:System.Windows.Navigation.NavigationWindow?displayProperty=fullName>
- <xref:System.Windows.Application?displayProperty=fullName>
