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
# <a name="desktop-guide-wpf-net"></a><span data-ttu-id="38ffb-103">桌面指南 (WPF .NET)</span><span class="sxs-lookup"><span data-stu-id="38ffb-103">Desktop Guide (WPF .NET)</span></span>

<span data-ttu-id="38ffb-104">欢迎使用 Windows Presentation Foundation (WPF) 桌面指南，这是一个与分辨率无关的 UI 框架，使用基于矢量的呈现引擎，构建用于利用现代图形硬件。</span><span class="sxs-lookup"><span data-stu-id="38ffb-104">Welcome to the Desktop Guide for Windows Presentation Foundation (WPF), a UI framework that is resolution-independent and uses a vector-based rendering engine, built to take advantage of modern graphics hardware.</span></span> <span data-ttu-id="38ffb-105">WPF 提供一套完善的应用程序开发功能，这些功能包括 Extensible Application Markup Language (XAML)、控件、数据绑定、布局、二维和三维图形、动画、样式、模板、文档、媒体、文本和版式。</span><span class="sxs-lookup"><span data-stu-id="38ffb-105">WPF provides a comprehensive set of application-development features that include Extensible Application Markup Language (XAML), controls, data binding, layout, 2D and 3D graphics, animation, styles, templates, documents, media, text, and typography.</span></span> <span data-ttu-id="38ffb-106">WPF 属于 .NET，因此可以生成整合 .NET API 其他元素的应用程序。</span><span class="sxs-lookup"><span data-stu-id="38ffb-106">WPF is part of .NET, so you can build applications that incorporate other elements of the .NET API.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="38ffb-107">WPF 有两种实现：</span><span class="sxs-lookup"><span data-stu-id="38ffb-107">There are two implementations of WPF:</span></span>

01. <span data-ttu-id="38ffb-108">.Net 版本（本指南）：</span><span class="sxs-lookup"><span data-stu-id="38ffb-108">**.NET** version (this guide):</span></span>

    <span data-ttu-id="38ffb-109">[GitHub](https://github.com/dotnet/wpf) 上托管的 WPF 开源实现，可在 .Net 5 或更高版本（包括 .Net Core 3.1）上运行。</span><span class="sxs-lookup"><span data-stu-id="38ffb-109">An open-source implementation of WPF hosted on [GitHub](https://github.com/dotnet/wpf), which runs on .NET 5 or higher (including .NET Core 3.1).</span></span> <span data-ttu-id="38ffb-110">适用于 XAML 设计器最低要求 [Visual Studio 2019 版本 16.8](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+wpf)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-110">The XAML designer requires, at a minimum, [Visual Studio 2019 version 16.8](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+wpf).</span></span>

    <span data-ttu-id="38ffb-111">尽管 .NET 是一种跨平台技术，但 WPF 并不是，它仅在 Windows 上运行。</span><span class="sxs-lookup"><span data-stu-id="38ffb-111">Even though .NET is a cross-platform technology, WPF isn't and only runs on Windows.</span></span>

01. <span data-ttu-id="38ffb-112">.NET Framework 4 版本：</span><span class="sxs-lookup"><span data-stu-id="38ffb-112">**.NET Framework 4** version:</span></span>

    <span data-ttu-id="38ffb-113">受 Visual Studio 2019 和 Visual Studio 2017 支持的 WPF 的 .NET Framework 实现。</span><span class="sxs-lookup"><span data-stu-id="38ffb-113">The .NET Framework implementation of WPF that's supported by Visual Studio 2019 and Visual Studio 2017.</span></span>

    <span data-ttu-id="38ffb-114">.NET Framework 4 是仅限 Windows 的 .NET 版本，被视为一个 Windows 操作系统组件。</span><span class="sxs-lookup"><span data-stu-id="38ffb-114">.NET Framework 4 is a Windows-only version of .NET and is considered a Windows Operating System component.</span></span> <span data-ttu-id="38ffb-115">此版本的 WPF 随 .NET Framework 一起分发。</span><span class="sxs-lookup"><span data-stu-id="38ffb-115">This version of WPF is distributed with .NET Framework.</span></span> <span data-ttu-id="38ffb-116">有关 WPF 的 .NET Framework 版本的详细信息，请参阅[适用于 .NET Framework 的 WPF 简介](../../../framework/wpf/introduction-to-wpf.md?view=netframeworkdesktop-4.8&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-116">For more information about the .NET Framework version of WPF, see [Introduction to WPF for .NET Framework](../../../framework/wpf/introduction-to-wpf.md?view=netframeworkdesktop-4.8&preserve-view=true).</span></span>

<span data-ttu-id="38ffb-117">本概述适用于新用户，介绍了 WPF 的主要功能和概念。</span><span class="sxs-lookup"><span data-stu-id="38ffb-117">This overview is intended for newcomers and covers the key capabilities and concepts of WPF.</span></span> <span data-ttu-id="38ffb-118">若要了解如何创建 WPF 应用程序，请参阅[教程：创建新的 WPF 应用](../get-started/create-app-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-118">To learn how to create a WPF app, see [Tutorial: Create a new WPF app](../get-started/create-app-visual-studio.md).</span></span>

## <a name="why-migrate-from-net-framework"></a><span data-ttu-id="38ffb-119">为什么要从 .NET Framework 迁移</span><span class="sxs-lookup"><span data-stu-id="38ffb-119">Why migrate from .NET Framework</span></span>

<span data-ttu-id="38ffb-120">适用于 .NET 5.0 的 WPF 提供优于 .NET Framework 的新功能和增强功能。</span><span class="sxs-lookup"><span data-stu-id="38ffb-120">WPF for .NET 5.0 provides new features and enhancements over .NET Framework.</span></span> <span data-ttu-id="38ffb-121">要了解如何迁移应用，请参阅[如何将 WPF 桌面应用迁移到 .NET 5](../migration/convert-project-from-net-framework.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-121">To learn how to migrate an app, see [How to migrate a WPF desktop app to .NET 5](../migration/convert-project-from-net-framework.md).</span></span>

## <a name="program-with-wpf"></a><span data-ttu-id="38ffb-122">使用 WPF 进行编程</span><span class="sxs-lookup"><span data-stu-id="38ffb-122">Program with WPF</span></span>

<span data-ttu-id="38ffb-123">WPF 作为 .NET 类型的一个子集存在，大部分位于 <xref:System.Windows> 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="38ffb-123">WPF exists as a subset of .NET types that are, mostly located in the <xref:System.Windows> namespace.</span></span> <span data-ttu-id="38ffb-124">如果你曾经使用 ASP.NET 和 Windows 窗体等框架通过 .NET 构建应用程序，应该会熟悉基本的 WPF 编程体验：</span><span class="sxs-lookup"><span data-stu-id="38ffb-124">If you have previously built applications with .NET with frameworks like ASP.NET and Windows Forms, the fundamental WPF programming experience should be familiar, you:</span></span>

- <span data-ttu-id="38ffb-125">实例化类</span><span class="sxs-lookup"><span data-stu-id="38ffb-125">Instantiate classes</span></span>
- <span data-ttu-id="38ffb-126">设置属性</span><span class="sxs-lookup"><span data-stu-id="38ffb-126">Set properties</span></span>
- <span data-ttu-id="38ffb-127">调用方法</span><span class="sxs-lookup"><span data-stu-id="38ffb-127">Call methods</span></span>
- <span data-ttu-id="38ffb-128">处理事件</span><span class="sxs-lookup"><span data-stu-id="38ffb-128">Handle events</span></span>

<span data-ttu-id="38ffb-129">WPF 还包括可增强属性和事件的其他编程构造：[依赖项属性](../../../framework/wpf/advanced/dependency-properties-overview.md)和[路由事件](../../../framework/wpf/advanced/routed-events-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-129">WPF includes more programming constructs that enhance properties and events: [dependency properties](../../../framework/wpf/advanced/dependency-properties-overview.md) and [routed events](../../../framework/wpf/advanced/routed-events-overview.md).</span></span>

## <a name="markup-and-code-behind"></a><span data-ttu-id="38ffb-130">标记和代码隐藏</span><span class="sxs-lookup"><span data-stu-id="38ffb-130">Markup and code-behind</span></span>

<span data-ttu-id="38ffb-131">通过 WPF，可以使用标记和代码隐藏开发应用程序，这是 ASP.NET 开发人员已经熟悉的体验。</span><span class="sxs-lookup"><span data-stu-id="38ffb-131">WPF lets you develop an application using both *markup* and *code-behind*, an experience with which ASP.NET developers should be familiar.</span></span> <span data-ttu-id="38ffb-132">通常使用 XAML 标记实现应用程序的外观，同时使用托管编程语言（代码隐藏）来实现其行为。</span><span class="sxs-lookup"><span data-stu-id="38ffb-132">You generally use XAML markup to implement the appearance of an application while using managed programming languages (code-behind) to implement its behavior.</span></span> <span data-ttu-id="38ffb-133">这种外观和行为的分离具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="38ffb-133">This separation of appearance and behavior has the following benefits:</span></span>

- <span data-ttu-id="38ffb-134">降低了开发和维护成本，因为特定于外观的标记与特定于行为的代码不紧密耦合。</span><span class="sxs-lookup"><span data-stu-id="38ffb-134">Development and maintenance costs are reduced because appearance-specific markup isn't tightly coupled with behavior-specific code.</span></span>

- <span data-ttu-id="38ffb-135">开发效率更高，因为设计人员在实现应用程序外观的同时，开发人员可以实现应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="38ffb-135">Development is more efficient because designers can implement an application's appearance simultaneously with developers who are implementing the application's behavior.</span></span>

- <span data-ttu-id="38ffb-136">WPF 应用程序的[全球化和本地化](../../../framework/wpf/advanced/wpf-globalization-and-localization-overview.md) 得以简化。</span><span class="sxs-lookup"><span data-stu-id="38ffb-136">[Globalization and localization](../../../framework/wpf/advanced/wpf-globalization-and-localization-overview.md) for WPF applications is simplified.</span></span>

### <a name="markup"></a><span data-ttu-id="38ffb-137">标记</span><span class="sxs-lookup"><span data-stu-id="38ffb-137">Markup</span></span>

<span data-ttu-id="38ffb-138">XAML 是一种基于 XML 的标记语言，以声明形式实现应用程序的外观。</span><span class="sxs-lookup"><span data-stu-id="38ffb-138">XAML is an XML-based markup language that implements an application's appearance declaratively.</span></span> <span data-ttu-id="38ffb-139">通常用它定义窗口、对话框、页面和用户控件，并填充控件、形状和图形。</span><span class="sxs-lookup"><span data-stu-id="38ffb-139">You typically use it to define windows, dialog boxes, pages, and user controls, and to fill them with controls, shapes, and graphics.</span></span>

<span data-ttu-id="38ffb-140">下面的示例使用 XAML 来实现包含一个按钮的窗口的外观：</span><span class="sxs-lookup"><span data-stu-id="38ffb-140">The following example uses XAML to implement the appearance of a window that contains a single button:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button">Click Me!</Button>

</Window>
```

<span data-ttu-id="38ffb-141">具体而言，此 XAML 使用 `Window` 元素定义窗口，使用 `Button` 元素定义按钮。</span><span class="sxs-lookup"><span data-stu-id="38ffb-141">Specifically, this XAML defines a window and a button by using the `Window` and `Button` elements.</span></span> <span data-ttu-id="38ffb-142">每个元素均配置了特性（如 `Window` 元素的 `Title` 特性）来指定窗口的标题栏文本。</span><span class="sxs-lookup"><span data-stu-id="38ffb-142">Each element is configured with attributes, such as the `Window` element's `Title` attribute to specify the window's title-bar text.</span></span> <span data-ttu-id="38ffb-143">在运行时，WPF 会将标记中定义的元素和特性转换为 WPF 类的实例。</span><span class="sxs-lookup"><span data-stu-id="38ffb-143">At run time, WPF converts the elements and attributes that are defined in markup to instances of WPF classes.</span></span> <span data-ttu-id="38ffb-144">例如， `Window` 元素被转换为 <xref:System.Windows.Window> 类的实例，该类的 <xref:System.Windows.Window.Title%2A> 属性是 `Title` 特性的值。</span><span class="sxs-lookup"><span data-stu-id="38ffb-144">For example, the `Window` element is converted to an instance of the <xref:System.Windows.Window> class whose <xref:System.Windows.Window.Title%2A> property is the value of the `Title` attribute.</span></span>

<span data-ttu-id="38ffb-145">下图显示上一个示例中的 XAML 定义的用户界面 (UI)：</span><span class="sxs-lookup"><span data-stu-id="38ffb-145">The following figure shows the user interface (UI) that is defined by the XAML in the previous example:</span></span>

:::image type="content" source="media/index/markup-window-button.png" alt-text="包含按钮的窗口":::

<span data-ttu-id="38ffb-147">由于 XAML 是基于 XML 的，因此使用它编写的 UI 汇集在嵌套元素的层次结构中，称为[元素树](../../../framework/wpf/advanced/trees-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-147">Since XAML is XML-based, the UI that you compose with it's assembled in a hierarchy of nested elements that is known as an [element tree](../../../framework/wpf/advanced/trees-in-wpf.md).</span></span> <span data-ttu-id="38ffb-148">元素树提供了一种直观的逻辑方式来创建和管理 UI。</span><span class="sxs-lookup"><span data-stu-id="38ffb-148">The element tree provides a logical and intuitive way to create and manage UIs.</span></span>

### <a name="code-behind"></a><span data-ttu-id="38ffb-149">代码隐藏</span><span class="sxs-lookup"><span data-stu-id="38ffb-149">Code-behind</span></span>

<span data-ttu-id="38ffb-150">应用程序的主要行为是实现响应用户交互的功能。</span><span class="sxs-lookup"><span data-stu-id="38ffb-150">The main behavior of an application is to implement the functionality that responds to user interactions.</span></span> <span data-ttu-id="38ffb-151">例如，单击菜单或按钮，以及在响应中调用业务逻辑和数据访问逻辑。</span><span class="sxs-lookup"><span data-stu-id="38ffb-151">For example clicking a menu or button, and calling business logic and data access logic in response.</span></span> <span data-ttu-id="38ffb-152">在 WPF 中，在与标记相关联的代码中实现此行为。</span><span class="sxs-lookup"><span data-stu-id="38ffb-152">In WPF, this behavior is implemented in code that is associated with markup.</span></span> <span data-ttu-id="38ffb-153">此类代码称为代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="38ffb-153">This type of code is known as code-behind.</span></span> <span data-ttu-id="38ffb-154">下面的示例演示上一个示例的更新标记和代码隐藏：</span><span class="sxs-lookup"><span data-stu-id="38ffb-154">The following example shows the updated markup from the previous example and the code-behind:</span></span>

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

<span data-ttu-id="38ffb-155">更新的标记定义 `xmlns:x` 命名空间，并将其映射到为代码隐藏类型添加支持的架构。</span><span class="sxs-lookup"><span data-stu-id="38ffb-155">The updated markup defines the `xmlns:x` namespace and maps it to the schema that adds support for the code-behind types.</span></span> <span data-ttu-id="38ffb-156">`x:Class` 特性用于将代码隐藏类与此特定 XAML 标记相关联。</span><span class="sxs-lookup"><span data-stu-id="38ffb-156">The `x:Class` attribute is used to associate a code-behind class to this specific XAML markup.</span></span> <span data-ttu-id="38ffb-157">考虑此特性在 `<Window>` 元素上声明，代码隐藏类必须从 `Window` 类继承。</span><span class="sxs-lookup"><span data-stu-id="38ffb-157">Considering this attribute is declared on the `<Window>` element, the code-behind class must inherit from the `Window` class.</span></span>

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

<span data-ttu-id="38ffb-158">从代码隐藏类的构造函数调用 `InitializeComponent`，以将标记中定义的 UI 与代码隐藏类合并在一起。</span><span class="sxs-lookup"><span data-stu-id="38ffb-158">`InitializeComponent` is called from the code-behind class's constructor to merge the UI that is defined in markup with the code-behind class.</span></span> <span data-ttu-id="38ffb-159">（生成应用程序时即会生成 `InitializeComponent`，因此不需要手动实现它。）`x:Class` 和 `InitializeComponent` 的组合可确保在创建实现时正确地对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="38ffb-159">(`InitializeComponent` is generated for you when your application is built, which is why you don't need to implement it manually.) The combination of `x:Class` and `InitializeComponent` ensure that your implementation is correctly initialized whenever it's created.</span></span>

<span data-ttu-id="38ffb-160">请注意，在标记中，`<Button>` 元素定义了 `Click` 属性的值 `button_click`。</span><span class="sxs-lookup"><span data-stu-id="38ffb-160">Notice that in the markup the `<Button>` element defined a value of `button_click` for the `Click` attribute.</span></span> <span data-ttu-id="38ffb-161">将标记和代码隐藏初始化并使其一起工作后，按钮的 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件会自动映射到 `button_click` 方法。</span><span class="sxs-lookup"><span data-stu-id="38ffb-161">With the markup and code-behind initialized and working together, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event for the button is automatically mapped to the `button_click` method.</span></span> <span data-ttu-id="38ffb-162">单击该按钮时，将调用事件处理程序，并通过调用 <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> 方法显示一个消息框。</span><span class="sxs-lookup"><span data-stu-id="38ffb-162">When the button is clicked, the event handler is invoked and a message box is displayed by calling the <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> method.</span></span>

<span data-ttu-id="38ffb-163">下图显示单击该按钮后的结果：</span><span class="sxs-lookup"><span data-stu-id="38ffb-163">The following figure shows the result when the button is clicked:</span></span>

:::image type="content" source="media/index/markup-window-button-clicked.png" alt-text="消息框":::

## <a name="input-and-commands"></a><span data-ttu-id="38ffb-165">输入和命令</span><span class="sxs-lookup"><span data-stu-id="38ffb-165">Input and commands</span></span>

<span data-ttu-id="38ffb-166">最常检测和响应用户输入的控件。</span><span class="sxs-lookup"><span data-stu-id="38ffb-166">Controls most often detect and respond to user input.</span></span> <span data-ttu-id="38ffb-167">WPF 输入系统使用直接事件和路由事件来支持文本输入、焦点管理和鼠标定位。</span><span class="sxs-lookup"><span data-stu-id="38ffb-167">The WPF input system uses both direct and routed events to support text input, focus management, and mouse positioning.</span></span>

<span data-ttu-id="38ffb-168">应用程序通常具有复杂的输入要求。</span><span class="sxs-lookup"><span data-stu-id="38ffb-168">Applications often have complex input requirements.</span></span> <span data-ttu-id="38ffb-169">WPF 提供了命令系统，用于将用户输入操作与对这些操作做出响应的代码分隔开来。</span><span class="sxs-lookup"><span data-stu-id="38ffb-169">WPF provides a command system that separates user-input actions from the code that responds to those actions.</span></span> <span data-ttu-id="38ffb-170">命令系统允许多个源调用相同的命令逻辑。</span><span class="sxs-lookup"><span data-stu-id="38ffb-170">The command system allows for multiple sources to invoke the same command logic.</span></span> <span data-ttu-id="38ffb-171">例如，进行由不同应用程序使用的常见编辑操作：复制、剪切和粘贴。  </span><span class="sxs-lookup"><span data-stu-id="38ffb-171">For example, take the common editing operations used by different applications: **Copy**, **Cut**, and **Paste**.</span></span> <span data-ttu-id="38ffb-172">如果使用命令实现了这些操作，则它们可以由不同的用户操作调用。</span><span class="sxs-lookup"><span data-stu-id="38ffb-172">These operations can be invoked by using different user actions if they're implemented by using commands.</span></span>

## <a name="controls"></a><span data-ttu-id="38ffb-173">控制</span><span class="sxs-lookup"><span data-stu-id="38ffb-173">Controls</span></span>

<span data-ttu-id="38ffb-174">应用程序模型带来的用户体验是构造的控件。</span><span class="sxs-lookup"><span data-stu-id="38ffb-174">The user experiences that are delivered by the application model are constructed controls.</span></span> <span data-ttu-id="38ffb-175">在 WPF 中，“控件”是一个概括性术语，适用于具有以下特征的 WPF 类类别：</span><span class="sxs-lookup"><span data-stu-id="38ffb-175">In WPF, *control* is an umbrella term that applies to a category of WPF classes that have the following characteristics:</span></span>

- <span data-ttu-id="38ffb-176">托管在窗口或页面中。</span><span class="sxs-lookup"><span data-stu-id="38ffb-176">Hosted in either a window or a page.</span></span>
- <span data-ttu-id="38ffb-177">拥有用户界面。</span><span class="sxs-lookup"><span data-stu-id="38ffb-177">Have a user interface.</span></span>
- <span data-ttu-id="38ffb-178">实现某些行为。</span><span class="sxs-lookup"><span data-stu-id="38ffb-178">Implement some behavior.</span></span>

<span data-ttu-id="38ffb-179">有关详细信息，请参阅 [控件](../../../framework/wpf/controls/index.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-179">For more information, see [Controls](../../../framework/wpf/controls/index.md).</span></span>

### <a name="wpf-controls-by-function"></a><span data-ttu-id="38ffb-180">按功能分类的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="38ffb-180">WPF controls by function</span></span>

<span data-ttu-id="38ffb-181">下面列出了内置的 WPF 控件：</span><span class="sxs-lookup"><span data-stu-id="38ffb-181">The built-in WPF controls are listed here:</span></span>

- <span data-ttu-id="38ffb-182">**按钮**： <xref:System.Windows.Controls.Button> 和 <xref:System.Windows.Controls.Primitives.RepeatButton>。</span><span class="sxs-lookup"><span data-stu-id="38ffb-182">**Buttons**: <xref:System.Windows.Controls.Button> and <xref:System.Windows.Controls.Primitives.RepeatButton>.</span></span>

- <span data-ttu-id="38ffb-183">**数据显示**：<xref:System.Windows.Controls.DataGrid>、<xref:System.Windows.Controls.ListView> 和 <xref:System.Windows.Controls.TreeView>。</span><span class="sxs-lookup"><span data-stu-id="38ffb-183">**Data Display**: <xref:System.Windows.Controls.DataGrid>, <xref:System.Windows.Controls.ListView>, and <xref:System.Windows.Controls.TreeView>.</span></span>

- <span data-ttu-id="38ffb-184">**日期显示和选项**： <xref:System.Windows.Controls.Calendar> 和 <xref:System.Windows.Controls.DatePicker>。</span><span class="sxs-lookup"><span data-stu-id="38ffb-184">**Date Display and Selection**: <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>.</span></span>

- <span data-ttu-id="38ffb-185">**对话框**： <xref:Microsoft.Win32.OpenFileDialog>、 <xref:System.Windows.Controls.PrintDialog>和 <xref:Microsoft.Win32.SaveFileDialog>。</span><span class="sxs-lookup"><span data-stu-id="38ffb-185">**Dialog Boxes**: <xref:Microsoft.Win32.OpenFileDialog>, <xref:System.Windows.Controls.PrintDialog>, and <xref:Microsoft.Win32.SaveFileDialog>.</span></span>

- <span data-ttu-id="38ffb-186">**数字墨迹**： <xref:System.Windows.Controls.InkCanvas> 和 <xref:System.Windows.Controls.InkPresenter>。</span><span class="sxs-lookup"><span data-stu-id="38ffb-186">**Digital Ink**: <xref:System.Windows.Controls.InkCanvas> and <xref:System.Windows.Controls.InkPresenter>.</span></span>

- <span data-ttu-id="38ffb-187">**文档**： <xref:System.Windows.Controls.DocumentViewer>、 <xref:System.Windows.Controls.FlowDocumentPageViewer>、 <xref:System.Windows.Controls.FlowDocumentReader>、 <xref:System.Windows.Controls.FlowDocumentScrollViewer>和 <xref:System.Windows.Controls.StickyNoteControl>。</span><span class="sxs-lookup"><span data-stu-id="38ffb-187">**Documents**: <xref:System.Windows.Controls.DocumentViewer>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentScrollViewer>, and <xref:System.Windows.Controls.StickyNoteControl>.</span></span>

- <span data-ttu-id="38ffb-188">**输入**： <xref:System.Windows.Controls.TextBox>、 <xref:System.Windows.Controls.RichTextBox>和 <xref:System.Windows.Controls.PasswordBox>。</span><span class="sxs-lookup"><span data-stu-id="38ffb-188">**Input**: <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Controls.PasswordBox>.</span></span>

- <span data-ttu-id="38ffb-189">**布局**： <xref:System.Windows.Controls.Border>、 <xref:System.Windows.Controls.Primitives.BulletDecorator>、 <xref:System.Windows.Controls.Canvas>、 <xref:System.Windows.Controls.DockPanel>、 <xref:System.Windows.Controls.Expander>、 <xref:System.Windows.Controls.Grid>、 <xref:System.Windows.Controls.GridView>、 <xref:System.Windows.Controls.GridSplitter>、 <xref:System.Windows.Controls.GroupBox>、 <xref:System.Windows.Controls.Panel>、 <xref:System.Windows.Controls.Primitives.ResizeGrip>、 <xref:System.Windows.Controls.Separator>、 <xref:System.Windows.Controls.Primitives.ScrollBar>、 <xref:System.Windows.Controls.ScrollViewer>、 <xref:System.Windows.Controls.StackPanel>、 <xref:System.Windows.Controls.Primitives.Thumb>、 <xref:System.Windows.Controls.Viewbox>、 <xref:System.Windows.Controls.VirtualizingStackPanel>、 <xref:System.Windows.Window>和 <xref:System.Windows.Controls.WrapPanel>。</span><span class="sxs-lookup"><span data-stu-id="38ffb-189">**Layout**: <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Primitives.BulletDecorator>, <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Expander>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridSplitter>, <xref:System.Windows.Controls.GroupBox>, <xref:System.Windows.Controls.Panel>, <xref:System.Windows.Controls.Primitives.ResizeGrip>, <xref:System.Windows.Controls.Separator>, <xref:System.Windows.Controls.Primitives.ScrollBar>, <xref:System.Windows.Controls.ScrollViewer>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Primitives.Thumb>, <xref:System.Windows.Controls.Viewbox>, <xref:System.Windows.Controls.VirtualizingStackPanel>, <xref:System.Windows.Window>, and <xref:System.Windows.Controls.WrapPanel>.</span></span>

- <span data-ttu-id="38ffb-190">**媒体**： <xref:System.Windows.Controls.Image>、 <xref:System.Windows.Controls.MediaElement>和 <xref:System.Windows.Controls.SoundPlayerAction>。</span><span class="sxs-lookup"><span data-stu-id="38ffb-190">**Media**: <xref:System.Windows.Controls.Image>, <xref:System.Windows.Controls.MediaElement>, and <xref:System.Windows.Controls.SoundPlayerAction>.</span></span>

- <span data-ttu-id="38ffb-191">**菜单**： <xref:System.Windows.Controls.ContextMenu>、 <xref:System.Windows.Controls.Menu>和 <xref:System.Windows.Controls.ToolBar>。</span><span class="sxs-lookup"><span data-stu-id="38ffb-191">**Menus**: <xref:System.Windows.Controls.ContextMenu>, <xref:System.Windows.Controls.Menu>, and <xref:System.Windows.Controls.ToolBar>.</span></span>

- <span data-ttu-id="38ffb-192">**导航**： <xref:System.Windows.Controls.Frame>、 <xref:System.Windows.Documents.Hyperlink>、 <xref:System.Windows.Controls.Page>、 <xref:System.Windows.Navigation.NavigationWindow>和 <xref:System.Windows.Controls.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="38ffb-192">**Navigation**: <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, and <xref:System.Windows.Controls.TabControl>.</span></span>

- <span data-ttu-id="38ffb-193">**选项**： <xref:System.Windows.Controls.CheckBox>、 <xref:System.Windows.Controls.ComboBox>、 <xref:System.Windows.Controls.ListBox>、 <xref:System.Windows.Controls.RadioButton>和 <xref:System.Windows.Controls.Slider>。</span><span class="sxs-lookup"><span data-stu-id="38ffb-193">**Selection**: <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.RadioButton>, and <xref:System.Windows.Controls.Slider>.</span></span>

- <span data-ttu-id="38ffb-194">**用户信息**： <xref:System.Windows.Controls.AccessText>、 <xref:System.Windows.Controls.Label>、 <xref:System.Windows.Controls.Primitives.Popup>、 <xref:System.Windows.Controls.ProgressBar>、 <xref:System.Windows.Controls.Primitives.StatusBar>、 <xref:System.Windows.Controls.TextBlock>和 <xref:System.Windows.Controls.ToolTip>。</span><span class="sxs-lookup"><span data-stu-id="38ffb-194">**User Information**: <xref:System.Windows.Controls.AccessText>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.ProgressBar>, <xref:System.Windows.Controls.Primitives.StatusBar>, <xref:System.Windows.Controls.TextBlock>, and <xref:System.Windows.Controls.ToolTip>.</span></span>

## <a name="layout"></a><span data-ttu-id="38ffb-195">Layout</span><span class="sxs-lookup"><span data-stu-id="38ffb-195">Layout</span></span>

<span data-ttu-id="38ffb-196">创建用户界面时，按照位置和大小排列控件以形成布局。</span><span class="sxs-lookup"><span data-stu-id="38ffb-196">When you create a user interface, you arrange your controls by location and size to form a layout.</span></span> <span data-ttu-id="38ffb-197">任何布局的一项关键要求都是适应窗口大小和显示设置的变化。</span><span class="sxs-lookup"><span data-stu-id="38ffb-197">A key requirement of any layout is to adapt to changes in window size and display settings.</span></span> <span data-ttu-id="38ffb-198">WPF 为你提供一流的可扩展布局系统，而不强制你编写代码以适应这些情况下的布局。</span><span class="sxs-lookup"><span data-stu-id="38ffb-198">Rather than forcing you to write the code to adapt a layout in these circumstances, WPF provides a first-class, extensible layout system for you.</span></span>

<span data-ttu-id="38ffb-199">布局系统的基础是相对定位，这提高了适应不断变化的窗口和显示条件的能力。</span><span class="sxs-lookup"><span data-stu-id="38ffb-199">The cornerstone of the layout system is relative positioning, which increases the ability to adapt to changing window and display conditions.</span></span> <span data-ttu-id="38ffb-200">该布局系统还可管理控件之间的协商以确定布局。</span><span class="sxs-lookup"><span data-stu-id="38ffb-200">The layout system also manages the negotiation between controls to determine the layout.</span></span> <span data-ttu-id="38ffb-201">协商是一个两步过程：首先，控件将需要的位置和大小告知父级。</span><span class="sxs-lookup"><span data-stu-id="38ffb-201">The negotiation is a two-step process: first, a control tells its parent what location and size it requires.</span></span> <span data-ttu-id="38ffb-202">其次，父级将控件可以有的空间告知控件。</span><span class="sxs-lookup"><span data-stu-id="38ffb-202">Second, the parent tells the control what space it can have.</span></span>

<span data-ttu-id="38ffb-203">该布局系统通过基 WPF 类公开给子控件。</span><span class="sxs-lookup"><span data-stu-id="38ffb-203">The layout system is exposed to child controls through base WPF classes.</span></span> <span data-ttu-id="38ffb-204">对于通用的布局（如网格、堆叠和停靠），WPF 包括若干布局控件：</span><span class="sxs-lookup"><span data-stu-id="38ffb-204">For common layouts such as grids, stacking, and docking, WPF includes several layout controls:</span></span>

- <span data-ttu-id="38ffb-205"><xref:System.Windows.Controls.Canvas>：子控件提供其自己的布局。</span><span class="sxs-lookup"><span data-stu-id="38ffb-205"><xref:System.Windows.Controls.Canvas>: Child controls provide their own layout.</span></span>

- <span data-ttu-id="38ffb-206"><xref:System.Windows.Controls.DockPanel>：子控件与面板的边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="38ffb-206"><xref:System.Windows.Controls.DockPanel>: Child controls are aligned to the edges of the panel.</span></span>

- <span data-ttu-id="38ffb-207"><xref:System.Windows.Controls.Grid>：子控件由行和列定位。</span><span class="sxs-lookup"><span data-stu-id="38ffb-207"><xref:System.Windows.Controls.Grid>: Child controls are positioned by rows and columns.</span></span>

- <span data-ttu-id="38ffb-208"><xref:System.Windows.Controls.StackPanel>：子控件垂直或水平堆叠。</span><span class="sxs-lookup"><span data-stu-id="38ffb-208"><xref:System.Windows.Controls.StackPanel>: Child controls are stacked either vertically or horizontally.</span></span>

- <span data-ttu-id="38ffb-209"><xref:System.Windows.Controls.VirtualizingStackPanel>：子控件在水平或垂直的行上虚拟化并排列。</span><span class="sxs-lookup"><span data-stu-id="38ffb-209"><xref:System.Windows.Controls.VirtualizingStackPanel>: Child controls are virtualized and arranged on a single line that is either horizontally or vertically oriented.</span></span>

- <span data-ttu-id="38ffb-210"><xref:System.Windows.Controls.WrapPanel>：子控件按从左到右的顺序放置，在当前行上的空间不足时</span><span class="sxs-lookup"><span data-stu-id="38ffb-210"><xref:System.Windows.Controls.WrapPanel>: Child controls are positioned in left-to-right order and wrapped to the next line when there isn't enough space.</span></span> <span data-ttu-id="38ffb-211">换行到下一行。</span><span class="sxs-lookup"><span data-stu-id="38ffb-211">on the current line.</span></span>

<span data-ttu-id="38ffb-212">下面的示例使用 <xref:System.Windows.Controls.DockPanel> 布置几个 <xref:System.Windows.Controls.TextBox> 控件：</span><span class="sxs-lookup"><span data-stu-id="38ffb-212">The following example uses a <xref:System.Windows.Controls.DockPanel> to lay out several <xref:System.Windows.Controls.TextBox> controls:</span></span>

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

<span data-ttu-id="38ffb-213"><xref:System.Windows.Controls.DockPanel> 允许子 <xref:System.Windows.Controls.TextBox> 控件，以告诉它如何排列这些控件。</span><span class="sxs-lookup"><span data-stu-id="38ffb-213">The <xref:System.Windows.Controls.DockPanel> allows the child <xref:System.Windows.Controls.TextBox> controls to tell it how to arrange them.</span></span> <span data-ttu-id="38ffb-214">为了完成此操作，<xref:System.Windows.Controls.DockPanel> 实现 `Dock` 附加了属性，该属性公开给子控件，以允许每个子控件指定停靠样式。</span><span class="sxs-lookup"><span data-stu-id="38ffb-214">To do this, the <xref:System.Windows.Controls.DockPanel> implements a `Dock` attached property that is exposed to the child controls to allow each of them to specify a dock style.</span></span>

> [!NOTE]
> <span data-ttu-id="38ffb-215">由父控件实现以便子控件使用的属性是 WPF 构造，称为[附加属性](../../../framework/wpf/advanced/attached-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-215">A property that's implemented by a parent control for use by child controls is a WPF construct called an [attached property](../../../framework/wpf/advanced/attached-properties-overview.md).</span></span>

<span data-ttu-id="38ffb-216">下图显示上一个示例中的 XAML 标记的结果：：</span><span class="sxs-lookup"><span data-stu-id="38ffb-216">The following figure shows the result of the XAML markup in the preceding example:</span></span>

:::image type="content" source="media/index/dockpanel-page.png" alt-text="DockPanel 页":::

## <a name="data-binding"></a><span data-ttu-id="38ffb-218">数据绑定</span><span class="sxs-lookup"><span data-stu-id="38ffb-218">Data binding</span></span>

<span data-ttu-id="38ffb-219">大多数应用程序旨在为用户提供查看和编辑数据的方法。</span><span class="sxs-lookup"><span data-stu-id="38ffb-219">Most applications are created to provide users with the means to view and edit data.</span></span> <span data-ttu-id="38ffb-220">对于 WPF 应用程序，存储和访问数据的工作已由许多不同的 .NET 数据访问库（例如 SQL 和 Entity Framework Core）提供。</span><span class="sxs-lookup"><span data-stu-id="38ffb-220">For WPF applications, the work of storing and accessing data is already provided for by many different .NET data access libraries such as SQL and Entity Framework Core.</span></span> <span data-ttu-id="38ffb-221">访问数据并将数据加载到应用程序的托管对象后，WPF 应用程序的复杂工作开始。</span><span class="sxs-lookup"><span data-stu-id="38ffb-221">After the data is accessed and loaded into an application's managed objects, the hard work for WPF applications begins.</span></span> <span data-ttu-id="38ffb-222">从根本上来说，这涉及到两件事：</span><span class="sxs-lookup"><span data-stu-id="38ffb-222">Essentially, this involves two things:</span></span>

01. <span data-ttu-id="38ffb-223">将数据从托管对象复制到控件，在控件中可以显示和编辑数据。</span><span class="sxs-lookup"><span data-stu-id="38ffb-223">Copying the data from the managed objects into controls, where the data can be displayed and edited.</span></span>

01. <span data-ttu-id="38ffb-224">确保使用控件对数据所做的更改将复制回托管对象。</span><span class="sxs-lookup"><span data-stu-id="38ffb-224">Ensuring that changes made to data by using controls are copied back to the managed objects.</span></span>

<span data-ttu-id="38ffb-225">为了简化应用程序开发，WPF 提供了一个强大的数据绑定引擎来自动处理这些步骤。</span><span class="sxs-lookup"><span data-stu-id="38ffb-225">To simplify application development, WPF provides a powerful data binding engine to automatically handle these steps.</span></span> <span data-ttu-id="38ffb-226">数据绑定引擎的核心单元是 <xref:System.Windows.Data.Binding> 类，其工作是将控件（绑定目标）绑定到数据对象（绑定源）。</span><span class="sxs-lookup"><span data-stu-id="38ffb-226">The core unit of the data binding engine is the <xref:System.Windows.Data.Binding> class, whose job is to bind a control (the binding target) to a data object (the binding source).</span></span> <span data-ttu-id="38ffb-227">下图阐释了这种关系：</span><span class="sxs-lookup"><span data-stu-id="38ffb-227">This relationship is illustrated by the following figure:</span></span>

:::image type="content" source="media/index/databinding-basic-diagram.png" alt-text="基本数据绑定示意图":::

<span data-ttu-id="38ffb-229">WPF 支持直接在 XAML 标记中声明绑定。</span><span class="sxs-lookup"><span data-stu-id="38ffb-229">WPF supports declaring bindings in the XAML markup directly.</span></span> <span data-ttu-id="38ffb-230">例如，下面的 XAML 代码使用“`{Binding ... }`”XAML 语法将 <xref:System.Windows.Controls.TextBox> 的 <xref:System.Windows.Controls.TextBox.Text%2A> 属性绑定到对象的 `Name` 属性。</span><span class="sxs-lookup"><span data-stu-id="38ffb-230">For example, the following XAML code binds the <xref:System.Windows.Controls.TextBox.Text%2A> property of the <xref:System.Windows.Controls.TextBox> to the `Name` property of an object using the "`{Binding ... }`" XAML syntax.</span></span> <span data-ttu-id="38ffb-231">这假设有一个数据对象设置为具有 `Name` 属性 `Window` 的 <xref:System.Windows.FrameworkElement.DataContext%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="38ffb-231">This assumes there's a data object set to the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the `Window` with a `Name` property.</span></span>

```xaml
 <Window
     xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
     xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
     x:Class="SDKSample.DataBindingWindow">

   <!-- Bind the TextBox to the data source (TextBox.Text to Person.Name) -->
   <TextBox Name="personNameTextBox" Text="{Binding Path=Name}" />

 </Window>
```

<span data-ttu-id="38ffb-232">WPF 数据绑定引擎不仅提供绑定，还提供验证、排序、筛选和分组。</span><span class="sxs-lookup"><span data-stu-id="38ffb-232">The WPF data binding engine provides more than just binding, it provides validation, sorting, filtering, and grouping.</span></span> <span data-ttu-id="38ffb-233">此外，数据绑定支持使用数据模板来为数据绑定创建自定义的用户界面。</span><span class="sxs-lookup"><span data-stu-id="38ffb-233">Furthermore, data binding supports the use of data templates to create custom user interface for bound data.</span></span>

<span data-ttu-id="38ffb-234">有关详细信息，请参阅[数据绑定概述](../data/index.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-234">For more information, see [Data binding overview](../data/index.md).</span></span>

## <a name="graphics--animation"></a><span data-ttu-id="38ffb-235">图形和动画</span><span class="sxs-lookup"><span data-stu-id="38ffb-235">Graphics & animation</span></span>

<span data-ttu-id="38ffb-236">WPF 提供一组广泛且灵活的图形功能，具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="38ffb-236">WPF provides an extensive and flexible set of graphics features that have the following benefits:</span></span>

- <span data-ttu-id="38ffb-237">**图形与分辨率和设备均无关**。</span><span class="sxs-lookup"><span data-stu-id="38ffb-237">**Resolution-independent and device-independent graphics**.</span></span> <span data-ttu-id="38ffb-238">WPF 图形系统中的基本度量单位是与设备无关的像素（即 1/96 英寸），为实现与分辨率和设备无关的呈现提供了基础。</span><span class="sxs-lookup"><span data-stu-id="38ffb-238">The basic unit of measurement in the WPF graphics system is the device-independent pixel, which is 1/96th of an inch, and provides the foundation for resolution-independent and device-independent rendering.</span></span> <span data-ttu-id="38ffb-239">每个与设备无关的像素都会自动缩放，以匹配呈现它的系统的每英寸点数 (dpi) 设置。</span><span class="sxs-lookup"><span data-stu-id="38ffb-239">Each device-independent pixel automatically scales to match the dots-per-inch (dpi) setting of the system it renders on.</span></span>

- <span data-ttu-id="38ffb-240">**精度更高**。</span><span class="sxs-lookup"><span data-stu-id="38ffb-240">**Improved precision**.</span></span> <span data-ttu-id="38ffb-241">WPF 坐标系统使用双精度浮点数字度量，而不是单精度数字。</span><span class="sxs-lookup"><span data-stu-id="38ffb-241">The WPF coordinate system is measured with double-precision floating-point numbers rather than single-precision.</span></span> <span data-ttu-id="38ffb-242">转换和不透明度值也表示为双精度数字。</span><span class="sxs-lookup"><span data-stu-id="38ffb-242">Transformations and opacity values are also expressed as double-precision.</span></span> <span data-ttu-id="38ffb-243">WPF 还支持广泛的颜色域 (scRGB)，并集成了对管理来自不同颜色空间的输入的支持。</span><span class="sxs-lookup"><span data-stu-id="38ffb-243">WPF also supports a wide color gamut (scRGB) and provides integrated support for managing inputs from different color spaces.</span></span>

- <span data-ttu-id="38ffb-244">**高级图形和动画支持**。</span><span class="sxs-lookup"><span data-stu-id="38ffb-244">**Advanced graphics and animation support**.</span></span> <span data-ttu-id="38ffb-245">WPF 通过为你管理动画场景简化了图形编程，你无需担心场景处理、呈现循环和双线性内插。</span><span class="sxs-lookup"><span data-stu-id="38ffb-245">WPF simplifies graphics programming by managing animation scenes for you; there's no need to worry about scene processing, rendering loops, and bilinear interpolation.</span></span> <span data-ttu-id="38ffb-246">此外，WPF 还提供了点击测试支持和全面的 alpha 合成支持。</span><span class="sxs-lookup"><span data-stu-id="38ffb-246">Additionally, WPF provides hit-testing support and full alpha-compositing support.</span></span>

- <span data-ttu-id="38ffb-247">**硬件加速**。</span><span class="sxs-lookup"><span data-stu-id="38ffb-247">**Hardware acceleration**.</span></span> <span data-ttu-id="38ffb-248">WPF 图形系统充分利用图形硬件来尽量降低 CPU 使用率。</span><span class="sxs-lookup"><span data-stu-id="38ffb-248">The WPF graphics system takes advantage of graphics hardware to minimize CPU usage.</span></span>

### <a name="2d-graphics"></a><span data-ttu-id="38ffb-249">2D 图形</span><span class="sxs-lookup"><span data-stu-id="38ffb-249">2D graphics</span></span>

<span data-ttu-id="38ffb-250">WPF 提供一个常用矢量绘制的二维形状库，例如矩形和椭圆。</span><span class="sxs-lookup"><span data-stu-id="38ffb-250">WPF provides a library of common vector-drawn 2D shapes, such as the rectangles and ellipses.</span></span> <span data-ttu-id="38ffb-251">形状不只是用于显示；还会实现许多你期望的控件功能，包括键盘和鼠标输入。</span><span class="sxs-lookup"><span data-stu-id="38ffb-251">The shapes aren't just for display; shapes implement many of the features that you expect from controls, including keyboard and mouse input.</span></span>

<span data-ttu-id="38ffb-252">WPF 提供的二维形状包含基本形状的标准集。</span><span class="sxs-lookup"><span data-stu-id="38ffb-252">The 2D shapes provided by WPF cover the standard set of basic shapes.</span></span> <span data-ttu-id="38ffb-253">但是，你可能需要创建自定义形状以辅助改进自定义用户界面的设计。</span><span class="sxs-lookup"><span data-stu-id="38ffb-253">However, you may need to create custom shapes to help the design of a customized user interface.</span></span> <span data-ttu-id="38ffb-254">WPF 提供几何图形来创建可直接绘制、用作画笔或用于剪辑其他形状和控件的自定义形状。</span><span class="sxs-lookup"><span data-stu-id="38ffb-254">WPF provides geometries to create a custom shape that can be drawn directly, used as a brush, or used to clip other shapes and controls.</span></span>

<span data-ttu-id="38ffb-255">有关详细信息，请参阅[几何图形概述](../../../framework/wpf/graphics-multimedia/geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-255">For more information, see [Geometry overview](../../../framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>

<span data-ttu-id="38ffb-256">WPF 二维功能的子集包括视觉效果，如渐变、位图、绘图、用视频绘画、旋转、缩放和倾斜。</span><span class="sxs-lookup"><span data-stu-id="38ffb-256">A subset of WPF 2D capabilities includes visual effects, such as gradients, bitmaps, drawings, painting with videos, rotation, scaling, and skewing.</span></span> <span data-ttu-id="38ffb-257">这些效果都是通过画笔实现的。</span><span class="sxs-lookup"><span data-stu-id="38ffb-257">These effects are all achieved with brushes.</span></span> <span data-ttu-id="38ffb-258">下图显示了一些示例：</span><span class="sxs-lookup"><span data-stu-id="38ffb-258">The following figure shows some examples:</span></span>

:::image type="content" source="media/index/graphics-brushes.png" alt-text="不同画笔的图示":::

<span data-ttu-id="38ffb-260">有关详细信息，请参阅 [WPF 画笔概述](../../../framework/wpf/graphics-multimedia/wpf-brushes-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-260">For more information, see [WPF brushes overview](../../../framework/wpf/graphics-multimedia/wpf-brushes-overview.md).</span></span>

### <a name="3d-rendering"></a><span data-ttu-id="38ffb-261">三维呈现</span><span class="sxs-lookup"><span data-stu-id="38ffb-261">3D rendering</span></span>

<span data-ttu-id="38ffb-262">WPF 还包括三维呈现功能，这些功能与二维图形集成，以创建更精彩、更有趣的用户界面。</span><span class="sxs-lookup"><span data-stu-id="38ffb-262">WPF also includes 3D rendering capabilities that integrate with 2D graphics to allow the creation of more exciting and interesting user interfaces.</span></span> <span data-ttu-id="38ffb-263">例如，下图显示呈现在三维形状上的二维图像：</span><span class="sxs-lookup"><span data-stu-id="38ffb-263">For example, the following figure shows 2D images rendered onto 3D shapes:</span></span>

:::image type="content" source="media/index/graphics-3d.png" alt-text="Visual3D 示例屏幕快照":::

<span data-ttu-id="38ffb-265">有关详细信息，请参阅[三维图形概述](../../../framework/wpf/graphics-multimedia/3-d-graphics-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-265">For more information, see [3D graphics overview](../../../framework/wpf/graphics-multimedia/3-d-graphics-overview.md).</span></span>

### <a name="animation"></a><span data-ttu-id="38ffb-266">动画</span><span class="sxs-lookup"><span data-stu-id="38ffb-266">Animation</span></span>

<span data-ttu-id="38ffb-267">WPF 动画支持可以使控件变大、抖动、旋转和淡出，以形成有趣的页面过渡等。</span><span class="sxs-lookup"><span data-stu-id="38ffb-267">WPF animation support lets you make controls grow, shake, spin, and fade, to create interesting page transitions, and more.</span></span> <span data-ttu-id="38ffb-268">你可以对大多数 WPF 类，甚至自定义类进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="38ffb-268">You can animate most WPF classes, even custom classes.</span></span> <span data-ttu-id="38ffb-269">下图显示了运行中的一个简单动画：</span><span class="sxs-lookup"><span data-stu-id="38ffb-269">The following figure shows a simple animation in action:</span></span>

:::image type="content" source="media/index/animation-cube.gif" alt-text="具有动画效果的立方体图":::

<span data-ttu-id="38ffb-271">有关详细信息，请参阅[动画概述](../../../framework/wpf/graphics-multimedia/animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-271">For more information, see [Animation overview](../../../framework/wpf/graphics-multimedia/animation-overview.md).</span></span>

## <a name="text-and-typography"></a><span data-ttu-id="38ffb-272">文本和版式</span><span class="sxs-lookup"><span data-stu-id="38ffb-272">Text and typography</span></span>

<span data-ttu-id="38ffb-273">WPF 提供以下功能以实现高质量的文本呈现：</span><span class="sxs-lookup"><span data-stu-id="38ffb-273">To provide high-quality text rendering, WPF offers the following features:</span></span>

- <span data-ttu-id="38ffb-274">OpenType 字体支持。</span><span class="sxs-lookup"><span data-stu-id="38ffb-274">OpenType font support.</span></span>
- <span data-ttu-id="38ffb-275">ClearType 增强功能。</span><span class="sxs-lookup"><span data-stu-id="38ffb-275">ClearType enhancements.</span></span>
- <span data-ttu-id="38ffb-276">利用硬件加速的高性能。</span><span class="sxs-lookup"><span data-stu-id="38ffb-276">High performance that takes advantage of hardware acceleration.</span></span>
- <span data-ttu-id="38ffb-277">文本与媒体、图形和动画的集成。</span><span class="sxs-lookup"><span data-stu-id="38ffb-277">Integration of text with media, graphics, and animation.</span></span>
- <span data-ttu-id="38ffb-278">国际字体支持和回退机制。</span><span class="sxs-lookup"><span data-stu-id="38ffb-278">International font support and fallback mechanisms.</span></span>

<span data-ttu-id="38ffb-279">作为文本与图形集成的演示，下图显示了文本修饰的应用程序：</span><span class="sxs-lookup"><span data-stu-id="38ffb-279">As a demonstration of text integration with graphics, the following figure shows the application of text decorations:</span></span>

:::image type="content" source="media/index/text.png" alt-text="具有各种文本修饰的文本":::

<span data-ttu-id="38ffb-281">有关详细信息，请参阅 [Windows Presentation Foundation 中的版式](../../../framework/wpf/advanced/typography-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-281">For more information, see [Typography in Windows Presentation Foundation](../../../framework/wpf/advanced/typography-in-wpf.md).</span></span>

## <a name="customize-wpf-apps"></a><span data-ttu-id="38ffb-282">自定义 WPF 应用</span><span class="sxs-lookup"><span data-stu-id="38ffb-282">Customize WPF apps</span></span>

<span data-ttu-id="38ffb-283">到目前为止，你已经了解用于开发应用程序的核心 WPF 构建块：</span><span class="sxs-lookup"><span data-stu-id="38ffb-283">Up to this point, you've seen the core WPF building blocks for developing applications:</span></span>

- <span data-ttu-id="38ffb-284">你可以使用该应用程序模型来托管和交付应用程序内容，它主要由控件组成。</span><span class="sxs-lookup"><span data-stu-id="38ffb-284">You use the application model to host and deliver application content, which consists mainly of controls.</span></span>
- <span data-ttu-id="38ffb-285">为简化用户界面中控件的安排，可使用 WPF 布局系统。</span><span class="sxs-lookup"><span data-stu-id="38ffb-285">To simplify the arrangement of controls in a user interface, you use the WPF layout system.</span></span>
- <span data-ttu-id="38ffb-286">可以使用数据绑定来减少将用户界面与数据集成的工作。</span><span class="sxs-lookup"><span data-stu-id="38ffb-286">You use data binding to reduce the work of integrating your user interface with data.</span></span>
- <span data-ttu-id="38ffb-287">若要增强你应用程序的可视化外观，可以使用 WPF 提供的综合图形、动画和媒体支持。</span><span class="sxs-lookup"><span data-stu-id="38ffb-287">To enhance the visual appearance of your application, you use the comprehensive range of graphics, animation, and media support provided by WPF.</span></span>

<span data-ttu-id="38ffb-288">不过，在创建和管理真正独特且视觉效果非凡的用户体验时，基础知识通常是不够的。</span><span class="sxs-lookup"><span data-stu-id="38ffb-288">Often, though, the basics aren't enough for creating and managing a truly distinct and visually stunning user experience.</span></span> <span data-ttu-id="38ffb-289">标准的 WPF 控件可能无法与你所需的应用程序外观集成。</span><span class="sxs-lookup"><span data-stu-id="38ffb-289">The standard WPF controls might not integrate with the desired appearance of your application.</span></span> <span data-ttu-id="38ffb-290">数据可能不会以最有效的方式显示。</span><span class="sxs-lookup"><span data-stu-id="38ffb-290">Data might not be displayed in the most effective way.</span></span> <span data-ttu-id="38ffb-291">你应用程序的整体用户体验可能不适合 Windows 主题的默认外观和感觉。</span><span class="sxs-lookup"><span data-stu-id="38ffb-291">Your application's overall user experience may not be suited to the default look and feel of Windows themes.</span></span>

<span data-ttu-id="38ffb-292">出于此原因，WPF 提供了各种机制来打造独特的用户体验。</span><span class="sxs-lookup"><span data-stu-id="38ffb-292">For this reason, WPF provides various mechanisms for creating unique user experiences.</span></span>

### <a name="content-model"></a><span data-ttu-id="38ffb-293">内容模型</span><span class="sxs-lookup"><span data-stu-id="38ffb-293">Content Model</span></span>

<span data-ttu-id="38ffb-294">大多数 WPF 控件的主要用途是显示内容。</span><span class="sxs-lookup"><span data-stu-id="38ffb-294">The main purpose of most of the WPF controls is to display content.</span></span> <span data-ttu-id="38ffb-295">在 WPF 中，可以构成控件内容的项的类型和数目称为控件的 *内容模型*。</span><span class="sxs-lookup"><span data-stu-id="38ffb-295">In WPF, the type and number of items that can constitute the content of a control is referred to as the control's *content model*.</span></span> <span data-ttu-id="38ffb-296">某些控件可以包含一种内容类型的一个项。</span><span class="sxs-lookup"><span data-stu-id="38ffb-296">Some controls can contain a single item and type of content.</span></span> <span data-ttu-id="38ffb-297">例如，<xref:System.Windows.Controls.TextBox> 的内容是分配给 <xref:System.Windows.Controls.TextBox.Text%2A> 属性的一个字符串值。</span><span class="sxs-lookup"><span data-stu-id="38ffb-297">For example, the content of a <xref:System.Windows.Controls.TextBox> is a string value that is assigned to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>

<span data-ttu-id="38ffb-298">但是，其他控件可以包含不同内容类型的多个项；<xref:System.Windows.Controls.Button> 的内容（由 <xref:System.Windows.Controls.ContentControl.Content%2A> 属性指定）可以包含各种项，包括布局控件、文本、图像和形状。</span><span class="sxs-lookup"><span data-stu-id="38ffb-298">Other controls, however, can contain multiple items of different types of content; the content of a <xref:System.Windows.Controls.Button>, specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property, can contain various items including layout controls, text, images, and shapes.</span></span>

<span data-ttu-id="38ffb-299">有关各种控件支持的内容类型的详细信息，请参阅 [WPF 内容模型](../../../framework/wpf/controls/wpf-content-model.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-299">For more information on the kinds of content that is supported by various controls, see [WPF content model](../../../framework/wpf/controls/wpf-content-model.md).</span></span>

### <a name="triggers"></a><span data-ttu-id="38ffb-300">触发器</span><span class="sxs-lookup"><span data-stu-id="38ffb-300">Triggers</span></span>

<span data-ttu-id="38ffb-301">尽管 XAML 标记的主要用途是实现应用程序的外观，你也可以使用 XAML 来实现应用程序行为的某些方面。</span><span class="sxs-lookup"><span data-stu-id="38ffb-301">Although the main purpose of XAML markup is to implement an application's appearance, you can also use XAML to implement some aspects of an application's behavior.</span></span> <span data-ttu-id="38ffb-302">其中一个示例是使用触发器来基于用户交互更改应用程序的外观。</span><span class="sxs-lookup"><span data-stu-id="38ffb-302">One example is the use of triggers to change an application's appearance based on user interactions.</span></span> <span data-ttu-id="38ffb-303">有关详细信息，请参阅[样式和模板](../controls/styles-templates-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-303">For more information, see [Styles and templates](../controls/styles-templates-overview.md).</span></span>

### <a name="templates"></a><span data-ttu-id="38ffb-304">模板</span><span class="sxs-lookup"><span data-stu-id="38ffb-304">Templates</span></span>

<span data-ttu-id="38ffb-305">WPF 控件的默认用户界面通常是从其他控件和形状构造的。</span><span class="sxs-lookup"><span data-stu-id="38ffb-305">The default user interfaces for WPF controls are typically constructed from other controls and shapes.</span></span> <span data-ttu-id="38ffb-306">例如， <xref:System.Windows.Controls.Button> 由 <xref:Microsoft.Windows.Themes.ButtonChrome> 和 <xref:System.Windows.Controls.ContentPresenter> 控件组成。</span><span class="sxs-lookup"><span data-stu-id="38ffb-306">For example, a <xref:System.Windows.Controls.Button> is composed of both <xref:Microsoft.Windows.Themes.ButtonChrome> and <xref:System.Windows.Controls.ContentPresenter> controls.</span></span> <span data-ttu-id="38ffb-307"><xref:Microsoft.Windows.Themes.ButtonChrome> 提供了标准按钮外观，而 <xref:System.Windows.Controls.ContentPresenter> 显示按钮的内容，正如 <xref:System.Windows.Controls.ContentControl.Content%2A> 属性所指定。</span><span class="sxs-lookup"><span data-stu-id="38ffb-307">The <xref:Microsoft.Windows.Themes.ButtonChrome> provides the standard button appearance, while the <xref:System.Windows.Controls.ContentPresenter> displays the button's content, as specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property.</span></span>

<span data-ttu-id="38ffb-308">有时，某个控件的默认外观可能与应用程序的整体外观冲突。</span><span class="sxs-lookup"><span data-stu-id="38ffb-308">Sometimes the default appearance of a control may conflict with the overall appearance of an application.</span></span> <span data-ttu-id="38ffb-309">在这种情况下，可以使用 <xref:System.Windows.Controls.ControlTemplate> 更改控件的用户界面的外观，而不更改其内容和行为。</span><span class="sxs-lookup"><span data-stu-id="38ffb-309">In this case, you can use a <xref:System.Windows.Controls.ControlTemplate> to change the appearance of the control's user interface without changing its content and behavior.</span></span>

<span data-ttu-id="38ffb-310">例如，单击 <xref:System.Windows.Controls.Button> 时会引发 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件。</span><span class="sxs-lookup"><span data-stu-id="38ffb-310">For example, a <xref:System.Windows.Controls.Button> raises the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event when it's clicked.</span></span> <span data-ttu-id="38ffb-311">通过更改按钮的模板来显示 <xref:System.Windows.Shapes.Ellipse> 形状，控件的可视方位发生了变化，但功能却没有。</span><span class="sxs-lookup"><span data-stu-id="38ffb-311">By changing the template of a button to display an <xref:System.Windows.Shapes.Ellipse> shape, the visual of the aspect of the control has changed, but the functionality hasn't.</span></span> <span data-ttu-id="38ffb-312">你仍可以单击该控件的可视方位，将按预期引发 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件。</span><span class="sxs-lookup"><span data-stu-id="38ffb-312">You can still click on the visual aspect of the control and the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event is raised as expected.</span></span>

:::image type="content" source="media/index/template-button.png" alt-text="省略号按钮和第二个窗口":::

### <a name="data-templates"></a><span data-ttu-id="38ffb-314">数据模板</span><span class="sxs-lookup"><span data-stu-id="38ffb-314">Data templates</span></span>

<span data-ttu-id="38ffb-315">使用控件模板可以指定控件的外观，而使用数据模板则可以指定控件内容的外观。</span><span class="sxs-lookup"><span data-stu-id="38ffb-315">Whereas a control template lets you specify the appearance of a control, a data template lets you specify the appearance of a control's content.</span></span> <span data-ttu-id="38ffb-316">数据模板经常用于改进绑定数据的显示方式。</span><span class="sxs-lookup"><span data-stu-id="38ffb-316">Data templates are frequently used to enhance how bound data is displayed.</span></span> <span data-ttu-id="38ffb-317">下图显示 <xref:System.Windows.Controls.ListBox> 的默认外观，它绑定到 `Task` 对象的集合，其中每个任务都具有名称、描述和优先级：</span><span class="sxs-lookup"><span data-stu-id="38ffb-317">The following figure shows the default appearance for a <xref:System.Windows.Controls.ListBox> that is bound to a collection of `Task` objects, where each task has a name, description, and priority:</span></span>

:::image type="content" source="media/index/data-template-listbox-normal.png" alt-text="具有默认外观的列表框":::

<span data-ttu-id="38ffb-319">默认外观是你对 <xref:System.Windows.Controls.ListBox>的期望。</span><span class="sxs-lookup"><span data-stu-id="38ffb-319">The default appearance is what you would expect from a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="38ffb-320">但是，每个任务的默认外观仅包含任务名称。</span><span class="sxs-lookup"><span data-stu-id="38ffb-320">However, the default appearance of each task contains only the task name.</span></span> <span data-ttu-id="38ffb-321">若要显示任务名称、描述和优先级，必须使用 <xref:System.Windows.Controls.ListBox> 更改 <xref:System.Windows.DataTemplate>控件绑定列表项的默认外观。</span><span class="sxs-lookup"><span data-stu-id="38ffb-321">To show the task name, description, and priority, the default appearance of the <xref:System.Windows.Controls.ListBox> control's bound list items must be changed by using a <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="38ffb-322">下面是一个示例，说明如何应用为 `Task` 对象创建的数据模板。</span><span class="sxs-lookup"><span data-stu-id="38ffb-322">Here is an example of applying a data template that was created for the `Task` object.</span></span>

:::image type="content" source="media/index/data-template-listbox-applied.png" alt-text="使用数据模板的列表框":::

<span data-ttu-id="38ffb-324"><xref:System.Windows.Controls.ListBox> 会保留其行为和整体外观；只有列表框所显示内容的外观发生变化。</span><span class="sxs-lookup"><span data-stu-id="38ffb-324">The <xref:System.Windows.Controls.ListBox> retains its behavior and overall appearance and only the appearance of the content being displayed by the list box has changed.</span></span>

<span data-ttu-id="38ffb-325">有关详细信息，请参阅[数据模板化概述](../../../framework/wpf/data/data-templating-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-325">For more information, see [Data templating overview](../../../framework/wpf/data/data-templating-overview.md).</span></span>

### <a name="styles"></a><span data-ttu-id="38ffb-326">样式</span><span class="sxs-lookup"><span data-stu-id="38ffb-326">Styles</span></span>

<span data-ttu-id="38ffb-327">通过样式功能，开发人员和设计人员能够对其产品的特定外观进行标准化。</span><span class="sxs-lookup"><span data-stu-id="38ffb-327">Styles enable developers and designers to standardize on a particular appearance for their product.</span></span> <span data-ttu-id="38ffb-328">WPF 提供了一个强样式模型，其基础是 <xref:System.Windows.Style> 元素。</span><span class="sxs-lookup"><span data-stu-id="38ffb-328">WPF provides a strong style model, the foundation of which is the <xref:System.Windows.Style> element.</span></span> <span data-ttu-id="38ffb-329">样式可以将属性值应用于类型。</span><span class="sxs-lookup"><span data-stu-id="38ffb-329">Styles can apply property values to types.</span></span> <span data-ttu-id="38ffb-330">引用样式时，可以根据类型将其自动应用于所有对象，或应用于单个对象。</span><span class="sxs-lookup"><span data-stu-id="38ffb-330">They can be applied automatically to the everything according to the type or individual objects when referenced.</span></span> <span data-ttu-id="38ffb-331">下面的示例创建一个样式，该样式将窗口上的每个 <xref:System.Windows.Controls.Button> 的背景色设置为 `Orange`：</span><span class="sxs-lookup"><span data-stu-id="38ffb-331">The following example creates a style that sets the background color for every <xref:System.Windows.Controls.Button> on the window to `Orange`:</span></span>

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

<span data-ttu-id="38ffb-332">由于此样式针对所有 <xref:System.Windows.Controls.Button> 控件，因此将自动应用于窗口中的所有按钮，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="38ffb-332">Because this style targets all <xref:System.Windows.Controls.Button> controls, the style is automatically applied to all the buttons in the window, as shown in the following figure:</span></span>

:::image type="content" source="media/index/styles-buttons.png" alt-text="两个橙色按钮":::

<span data-ttu-id="38ffb-334">有关详细信息，请参阅[样式和模板](../controls/styles-templates-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-334">For more information, see [Styles and templates](../controls/styles-templates-overview.md).</span></span>

### <a name="resources"></a><span data-ttu-id="38ffb-335">资源</span><span class="sxs-lookup"><span data-stu-id="38ffb-335">Resources</span></span>

<span data-ttu-id="38ffb-336">应用程序中的控件应共享相同的外观，它可以包括从字体和背景色到控件模板、数据模板和样式的所有内容。</span><span class="sxs-lookup"><span data-stu-id="38ffb-336">Controls in an application should share the same appearance, which can include anything from fonts and background colors to control templates, data templates, and styles.</span></span> <span data-ttu-id="38ffb-337">你可以对用户界面资源使用 WPF 支持，以将这些资源封装在一个位置以便重复使用。</span><span class="sxs-lookup"><span data-stu-id="38ffb-337">You can use WPF's support for user interface resources to encapsulate these resources in a single location for reuse.</span></span>

<span data-ttu-id="38ffb-338">下面的示例定义 <xref:System.Windows.Controls.Button> 和 <xref:System.Windows.Controls.Label>共享的通用背景色：</span><span class="sxs-lookup"><span data-stu-id="38ffb-338">The following example defines a common background color that is shared by a <xref:System.Windows.Controls.Button> and a <xref:System.Windows.Controls.Label>:</span></span>

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

<span data-ttu-id="38ffb-339">有关详细信息，请参阅[如何定义和引用 WPF 资源](../systems/xaml-resources-how-to-define-and-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-339">For more information, see [How to define and reference a WPF resource](../systems/xaml-resources-how-to-define-and-reference.md).</span></span>

### <a name="custom-controls"></a><span data-ttu-id="38ffb-340">自定义控件</span><span class="sxs-lookup"><span data-stu-id="38ffb-340">Custom controls</span></span>

<span data-ttu-id="38ffb-341">尽管 WPF 提供了大量自定义支持，但你仍可能会遇到现有 WPF 控件不满足你的应用程序或其用户的需求的情况。</span><span class="sxs-lookup"><span data-stu-id="38ffb-341">Although WPF provides a host of customization support, you may encounter situations where existing WPF controls do not meet the needs of either your application or its users.</span></span> <span data-ttu-id="38ffb-342">出现这种情况的原因有：</span><span class="sxs-lookup"><span data-stu-id="38ffb-342">This can occur when:</span></span>

- <span data-ttu-id="38ffb-343">不能通过自定义现有 WPF 实现的外观和感觉创建所需的用户界面。</span><span class="sxs-lookup"><span data-stu-id="38ffb-343">The user interface that you require cannot be created by customizing the look and feel of existing WPF implementations.</span></span>
- <span data-ttu-id="38ffb-344">现有 WPF 实现不支持（或很难支持）所需的行为。</span><span class="sxs-lookup"><span data-stu-id="38ffb-344">The behavior that you require isn't supported (or not easily supported) by existing WPF implementations.</span></span>

<span data-ttu-id="38ffb-345">但是，此时，你可以充分利用三个 WPF 模型中的一个来创建新的控件。</span><span class="sxs-lookup"><span data-stu-id="38ffb-345">At this point, however, you can take advantage of one of three WPF models to create a new control.</span></span> <span data-ttu-id="38ffb-346">每个模型都针对一个特定的方案并要求你的自定义控件派生自特定 WPF 基类。</span><span class="sxs-lookup"><span data-stu-id="38ffb-346">Each model targets a specific scenario and requires your custom control to derive from a particular WPF base class.</span></span> <span data-ttu-id="38ffb-347">下面列出了这三个模型：</span><span class="sxs-lookup"><span data-stu-id="38ffb-347">The three models are listed here:</span></span>

- <span data-ttu-id="38ffb-348">**用户控件模型**</span><span class="sxs-lookup"><span data-stu-id="38ffb-348">**User Control Model**</span></span>\
<span data-ttu-id="38ffb-349">自定义控件派生自 <xref:System.Windows.Controls.UserControl> 并由一个或多个其他控件组成。</span><span class="sxs-lookup"><span data-stu-id="38ffb-349">A custom control derives from <xref:System.Windows.Controls.UserControl> and is composed of one or more other controls.</span></span>

- <span data-ttu-id="38ffb-350">**控件模型** 自定义控件派生自 <xref:System.Windows.Controls.Control>，并用于生成使用模板将其行为与其外观分隔开来的实现，非常类似大多数 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="38ffb-350">**Control Model** A custom control derives from <xref:System.Windows.Controls.Control> and is used to build implementations that separate their behavior from their appearance using templates, much like most WPF controls.</span></span> <span data-ttu-id="38ffb-351">派生自 <xref:System.Windows.Controls.Control> 使得你可以更自由地创建自定义用户界面（相较用户控件），但它可能需要花费更多精力。</span><span class="sxs-lookup"><span data-stu-id="38ffb-351">Deriving from <xref:System.Windows.Controls.Control> allows you more freedom for creating a custom user interface than user controls, but it may require more effort.</span></span>

- <span data-ttu-id="38ffb-352">**框架元素模型**。</span><span class="sxs-lookup"><span data-stu-id="38ffb-352">**Framework Element Model**.</span></span>\
<span data-ttu-id="38ffb-353">当其外观由自定义呈现逻辑（而不是模板）定义时，自定义控件派生自 <xref:System.Windows.FrameworkElement> 。</span><span class="sxs-lookup"><span data-stu-id="38ffb-353">A custom control derives from <xref:System.Windows.FrameworkElement> when its appearance is defined by custom rendering logic (not templates).</span></span>

<span data-ttu-id="38ffb-354">有关自定义控件的详细信息，请参阅[控件创作概述](../../../framework/wpf/controls/control-authoring-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="38ffb-354">For more information on custom controls, see [Control authoring overview](../../../framework/wpf/controls/control-authoring-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="38ffb-355">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38ffb-355">See also</span></span>

- [<span data-ttu-id="38ffb-356">教程：创建新的 WPF 应用</span><span class="sxs-lookup"><span data-stu-id="38ffb-356">Tutorial: Create a new WPF app</span></span>](../get-started/create-app-visual-studio.md)
- [<span data-ttu-id="38ffb-357">将 WPF 应用迁移到 .NET Core</span><span class="sxs-lookup"><span data-stu-id="38ffb-357">Migrate a WPF app to .NET Core</span></span>](../migration/convert-project-from-net-framework.md)
- [<span data-ttu-id="38ffb-358">WPF 窗口概述</span><span class="sxs-lookup"><span data-stu-id="38ffb-358">Overview of WPF windows</span></span>](../windows/index.md)
- [<span data-ttu-id="38ffb-359">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="38ffb-359">Data binding overview</span></span>](../data/index.md)
- [<span data-ttu-id="38ffb-360">XAML概述</span><span class="sxs-lookup"><span data-stu-id="38ffb-360">XAML overview</span></span>](../xaml/index.md)
