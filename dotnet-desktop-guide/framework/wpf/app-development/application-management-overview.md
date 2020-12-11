---
title: 应用程序管理概述
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: a735791b00b1a8eba48f381ccac2a6325058c842
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973635"
---
# <a name="application-management-overview"></a>应用程序管理概述

所有应用程序都可能会共享一组适用于实现和管理应用程序的常见功能。 本主题概述了 <xref:System.Windows.Application> 用于创建和管理应用程序的类中的功能。

## <a name="the-application-class"></a>Application 类

在 WPF 中，公共应用程序范围内的功能封装在 <xref:System.Windows.Application> 类中。 <xref:System.Windows.Application>类包含以下功能：

- 对应用程序的生存期进行跟踪并与之进行交互。

- 检索和处理命令行参数。

- 检测和响应未经处理的异常。

- 共享应用程序范围的属性和资源。

- 管理独立应用程序中的窗口。

- 跟踪和管理导航。

<a name="The_Application_Class"></a>

## <a name="how-to-perform-common-tasks-using-the-application-class"></a>如何使用 Application 类执行常见任务

如果你对类的所有详细信息不感兴趣 <xref:System.Windows.Application> ，下表列出了一些常见的任务， <xref:System.Windows.Application> 以及如何完成这些任务。 通过查看相关的 API 和主题，可以找到详细信息和示例代码。

|任务|方法|
|----------|--------------|
|获取表示当前应用程序的对象|使用 <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> 属性。|
|将启动屏幕添加到应用程序中|请参阅 [将初始屏幕添加到 WPF 应用程序](how-to-add-a-splash-screen-to-a-wpf-application.md)。|
|启动应用程序|使用 <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType> 方法。|
|停止应用程序|使用 <xref:System.Windows.Application.Shutdown%2A> 对象的方法 <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> 。|
|从命令行获取参数|处理 <xref:System.Windows.Application.Startup?displayProperty=nameWithType> 事件并使用 <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> 属性。 有关示例，请参阅 <xref:System.Windows.Application.Startup?displayProperty=nameWithType> 事件。|
|获取和设置应用程序退出代码|<xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType>在 <xref:System.Windows.Application.Exit?displayProperty=nameWithType> 事件处理程序中设置属性，或调用 <xref:System.Windows.Application.Shutdown%2A> 方法并传入整数。|
|检测和响应未经处理的异常|处理 <xref:System.Windows.Application.DispatcherUnhandledException> 事件。|
|获取和设置应用程序范围的资源|使用 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 属性。|
|使用应用程序范围的资源字典|请参阅 [使用 Application-Scope 资源字典](how-to-use-an-application-scope-resource-dictionary.md)。|
|获取和设置应用程序范围的属性|使用 <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType> 属性。|
|获取和保存应用程序的状态|请参阅 [在应用程序会话之间保留和还原 Application-Scope 属性](persist-and-restore-application-scope-properties.md)。|
|管理非代码数据文件，包括资源文件、内容文件和源站点文件。|请参阅 [WPF 应用程序资源、内容和数据文件](wpf-application-resource-content-and-data-files.md)。|
|管理独立应用程序中的窗口|请参阅 [WPF 窗口概述](wpf-windows-overview.md)。|
|跟踪和管理导航|请参阅 [导航概述](navigation-overview.md)。|

<a name="The_Application_Definition"></a>

## <a name="the-application-definition"></a>应用程序定义

若要利用类的功能 <xref:System.Windows.Application> ，必须实现应用程序定义。 WPF 应用程序定义是一个派生自的类， <xref:System.Windows.Application> 并使用特殊的 MSBuild 设置进行配置。

### <a name="implementing-an-application-definition"></a>实现应用程序定义

使用标记和代码隐藏来实现典型的 WPF 应用程序定义。 因此，可以使用标记以声明方式设置应用程序的属性、资源和注册事件，同时还能处理事件并在代码隐藏中实现特定于应用程序的行为。

以下示例演示了如何使用标记和代码隐藏来实现应用程序定义：

[!code-xaml[ApplicationSnippets#ApplicationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]

[!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
[!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]

要允许标记文件和代码隐藏文件协同工作，需要进行以下配置：

- 在标记中， `Application` 元素必须包含 `x:Class` 属性。 生成应用程序后， `x:Class` 在标记文件中存在会使 MSBuild 创建一个 `partial` 派生自的类， <xref:System.Windows.Application> 并具有由特性指定的名称 `x:Class` 。 这需要为 XAML 架构 () 添加 XML 命名空间声明 `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` 。

- 在代码隐藏中，类必须是 `partial` 由标记中的特性指定的同名类， `x:Class` 并且必须派生自 <xref:System.Windows.Application> 。 这允许在生成应用程序时将代码隐藏文件与为 `partial` 标记文件生成的类相关联 (请参阅 [生成 WPF 应用程序](building-a-wpf-application-wpf.md)) 。

> [!NOTE]
> 使用 Visual Studio 创建新的 WPF 应用程序项目或 WPF 浏览器应用程序项目时，默认情况下将包含应用程序定义，并使用标记和代码隐藏来定义应用程序定义。

至少要有这段代码，才能实现应用程序定义。 但是，在生成和运行应用程序之前，需要对应用程序定义进行附加的 MSBuild 配置。

### <a name="configuring-the-application-definition-for-msbuild"></a>针对 MSBuild 配置应用程序定义

独立应用程序和 XAML 浏览器应用程序 (Xbap) 需要实现某个特定级别的基础结构，然后才能运行。 在该基础结构中，入口点是最重要的一个部分。 当用户启动某个应用程序时，操作系统会调用入口点，这是一个为人熟知的应用程序启动函数。

通常，开发者需要自行编写其中的部分或全部代码（具体取决于所采用的技术）。 但是，当您的应用程序定义的标记文件配置为 MSBuild 项时，WPF 将为您生成此代码 `ApplicationDefinition` ，如下面的 msbuild 项目文件所示：

```xml
<Project
  DefaultTargets="Build"
                        xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  ...
  <ApplicationDefinition Include="App.xaml" />
  <Compile Include="App.xaml.cs" />
  ...
</Project>
```

由于代码隐藏文件包含代码，因此它将标记为 MSBuild `Compile` 项，这是正常的。

将这些 MSBuild 配置应用于应用程序定义的标记和代码隐藏文件会导致 MSBuild 生成如下所示的代码：

[!code-csharp[auto-generated-code](~/samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs)]
[!code-vb[auto-generated-code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb)]

生成的代码通过附加的基础结构代码（包括入口点方法）来补充应用程序定义 `Main` 。 <xref:System.STAThreadAttribute>特性应用于 `Main` 方法，以指示 wpf 应用程序的主 UI 线程是 wpf 应用程序所需的 STA 线程。 调用时，将 `Main` 创建一个新的实例， `App` 然后调用 `InitializeComponent` 方法以注册事件并设置在标记中实现的属性。 由于 `InitializeComponent` 会为你生成，因此你不需要 `InitializeComponent` 从应用程序定义中显式调用，就像对和实现执行的操作一样 <xref:System.Windows.Controls.Page> <xref:System.Windows.Window> 。 最后， <xref:System.Windows.Application.Run%2A> 调用方法以启动应用程序。

<a name="Getting_the_Current_Application"></a>

## <a name="getting-the-current-application"></a>获取当前应用程序

由于类的功能在 <xref:System.Windows.Application> 应用程序之间共享，因此每个只能有一个类的实例 <xref:System.Windows.Application> <xref:System.AppDomain> 。 若要强制执行此类，请将 <xref:System.Windows.Application> 类作为单独类实现 (参阅[在 c # 中实现单一](/previous-versions/msp-n-p/ff650316(v=pandp.10))实例) ，这将创建其自身的单一实例，并使用属性提供对该实例的共享访问 `static` <xref:System.Windows.Application.Current%2A> 。

下面的代码演示如何获取对当前对象的引用 <xref:System.Windows.Application> <xref:System.AppDomain> 。

[!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]

<xref:System.Windows.Application.Current%2A> 返回对类的实例的引用 <xref:System.Windows.Application> 。 如果需要对派生类的引用 <xref:System.Windows.Application> ，则必须强制转换该属性的值 <xref:System.Windows.Application.Current%2A> ，如下面的示例中所示。

[!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]

您可以在对象的生存期内的 <xref:System.Windows.Application.Current%2A> 任何时间点检查的值 <xref:System.Windows.Application> 。 但是，检查时要小心。 对 <xref:System.Windows.Application> 类进行实例化后，对象的状态不 <xref:System.Windows.Application> 一致。 在此期间， <xref:System.Windows.Application> 将执行您的代码运行所需的各种初始化任务，包括建立应用程序基础结构、设置属性和注册事件。 如果尝试 <xref:System.Windows.Application> 在此期间使用对象，代码可能会产生意外的结果，尤其是在它依赖于 <xref:System.Windows.Application> 所设置的各种属性时。

<xref:System.Windows.Application>完成其初始化工作时，它的生存期确实会开始。

<a name="Application_Lifetime"></a>

## <a name="application-lifetime"></a>应用程序生存期

WPF 应用程序的生存期由引发的多个事件标记，以便 <xref:System.Windows.Application> 在应用程序启动、激活和停用并关闭时，通知您。

<a name="Splash_Screen"></a>

### <a name="splash-screen"></a>初始屏幕

从 .NET Framework 3.5 SP1 开始，可以指定要在启动窗口中使用的映像或 *初始屏幕*。 使用类，可以在 <xref:System.Windows.SplashScreen> 加载应用程序时轻松显示启动窗口。 在 <xref:System.Windows.SplashScreen> 调用之前，将创建并显示该窗口 <xref:System.Windows.Application.Run%2A> 。 有关详细信息，请参阅 [应用程序启动时间](../advanced/application-startup-time.md) 和 [将初始屏幕添加到 WPF 应用程序](how-to-add-a-splash-screen-to-a-wpf-application.md)。

<a name="Starting_an_Application"></a>

### <a name="starting-an-application"></a>启动应用程序

<xref:System.Windows.Application.Run%2A>调用并初始化应用程序后，即可运行应用程序。 此时将在 <xref:System.Windows.Application.Startup> 引发事件时表示：

[!code-csharp[Startup-event](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs?range=3-11,31-33)]
[!code-vb[Startup-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb?range=5-11,30-32)]

在应用程序生存期内的这一点，最常见的做法是显示 UI。

<a name="Showing_a_User_Interface"></a>

### <a name="showing-a-user-interface"></a>显示用户界面

大多数独立的 Windows 应用程序在 <xref:System.Windows.Window> 开始运行时打开。 <xref:System.Windows.Application.Startup>事件处理程序是一个位置，你可以从该位置执行此操作，如以下代码所示。

[!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]

[!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
[!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]

> [!NOTE]
> <xref:System.Windows.Window>默认情况下，在独立应用程序中实例化的第一个将成为主应用程序窗口。 此 <xref:System.Windows.Window> 对象由 <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> 属性引用。 <xref:System.Windows.Application.MainWindow%2A>如果不同于第一个实例化的窗口 <xref:System.Windows.Window> 应为主窗口，则可以通过编程方式更改属性的值。

XBAP 首次启动时，它很可能会导航到 <xref:System.Windows.Controls.Page> 。 以下代码对此进行演示。

[!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]

[!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
[!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]

如果处理 <xref:System.Windows.Application.Startup> 只是打开 <xref:System.Windows.Window> 或导航到 <xref:System.Windows.Controls.Page> ，则可以 `StartupUri` 改为在标记中设置特性。

下面的示例演示如何使用 <xref:System.Windows.Application.StartupUri%2A> 独立应用程序中的打开 <xref:System.Windows.Window> 。

[!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]

下面的示例演示如何 <xref:System.Windows.Application.StartupUri%2A> 从 XBAP 使用以导航到 <xref:System.Windows.Controls.Page> 。

[!code-xaml[PageSnippets#XBAPStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]

此标记的效果等同于用于打开窗口的上一段代码。

> [!NOTE]
> 有关导航的详细信息，请参阅 [导航概述](navigation-overview.md)。

<xref:System.Windows.Application.Startup> <xref:System.Windows.Window> 如果需要使用非参数构造函数来实例化事件，或者需要在显示该事件之前设置其属性或订阅其事件，则需要处理该事件，或者需要处理在启动应用程序时提供的任何命令行参数。

<a name="Processing_Command_Line_Arguments"></a>

### <a name="processing-command-line-arguments"></a>处理命令行参数

在 Windows 中，可以从命令提示符或桌面启动独立应用程序。 在这两种情况下，命令行参数都可以传递至应用程序。 以下示例展示了一个通过单个命令行参数“/StartMinimized”来启动的应用程序：

`wpfapplication.exe /StartMinimized`

在应用程序初始化期间，WPF 将从操作系统检索命令行参数，并通过参数的属性将其传递到 <xref:System.Windows.Application.Startup> 事件处理程序 <xref:System.Windows.StartupEventArgs.Args%2A> <xref:System.Windows.StartupEventArgs> 。 可以使用如下代码来检索和存储命令行参数。

[!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]

[!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
[!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]

<xref:System.Windows.Application.Startup>用于检查是否提供了 **/StartMinimized** 命令行参数的代码句柄; 如果已提供，则使用的打开主窗口 <xref:System.Windows.WindowState> <xref:System.Windows.WindowState.Minimized> 。 请注意，由于 <xref:System.Windows.Window.WindowState%2A> 必须以编程方式设置属性，因此 <xref:System.Windows.Window> 必须在代码中显式打开 main。

Xbap 无法检索和处理命令行参数，因为它们是使用 ClickOnce 部署启动的 (请参阅 [部署 WPF 应用程序](deploying-a-wpf-application-wpf.md)) 。 但是，它们可以检索和处理来自用于启动它们的 URL 的查询字符串参数。

<a name="Application_Activation_and_Deactivation"></a>

### <a name="application-activation-and-deactivation"></a>应用程序激活和停用

Windows 允许用户在应用程序之间切换。 最常见的方法是使用 ALT + TAB 键组合。 仅当应用程序具有可供用户选择的可见时，才能切换到该应用程序 <xref:System.Windows.Window> 。 当前选定的 <xref:System.Windows.Window> 是 *活动窗口* (也称为 *前台窗口*) 并且是 <xref:System.Windows.Window> 接收用户输入的。 具有活动窗口的应用程序是 *活动应用程序* (或 *前台应用* 程序) 。 应用程序会在以下情况下变为活动应用程序：

- 它已启动并显示 <xref:System.Windows.Window> 。

- 用户通过 <xref:System.Windows.Window> 在应用程序中选择，从其他应用程序切换。

可以通过处理事件来检测应用程序何时变为活动状态 <xref:System.Windows.Application.Activated?displayProperty=nameWithType> 。

同样地，应用程序会在以下情况下变为非活动状态：

- 用户从当前应用程序切换到另一应用程序。

- 应用程序关闭后。

可以通过处理事件来检测应用程序处于非活动状态的时间 <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> 。

下面的代码演示如何处理 <xref:System.Windows.Application.Activated> 和 <xref:System.Windows.Application.Deactivated> 事件，以确定应用程序是否处于活动状态。

[!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]

[!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
[!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]

<xref:System.Windows.Window>还可以激活和停用。 有关更多信息，请参见<xref:System.Windows.Window.Activated?displayProperty=nameWithType>和<xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>。

> [!NOTE]
> <xref:System.Windows.Application.Activated?displayProperty=nameWithType>对于 xbap，和都不 <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> 会引发。

<a name="Application_Shutdown"></a>

### <a name="application-shutdown"></a>应用程序关闭

应用程序的生存期会在其关闭时结束，出现这一情况可能是因为：

- 用户关闭每个 <xref:System.Windows.Window> 。

- 用户关闭 main <xref:System.Windows.Window> 。

- 用户通过注销或关闭来结束 Windows 会话。

- 满足了特定于应用程序的条件。

为帮助你管理应用程序关闭， <xref:System.Windows.Application> 提供 <xref:System.Windows.Application.Shutdown%2A> 方法、 <xref:System.Windows.Application.ShutdownMode%2A> 属性和 <xref:System.Windows.Application.SessionEnding> 和 <xref:System.Windows.Application.Exit> 事件。

> [!NOTE]
> <xref:System.Windows.Application.Shutdown%2A> 只能从具有的应用程序调用 <xref:System.Security.Permissions.UIPermission> 。 独立 WPF 应用程序始终具有此权限。 但是，在 Internet 区域部分信任安全沙箱中运行的 Xbap 不会。

#### <a name="shutdown-mode"></a>关闭模式

大多数应用程序会在所有窗口都关闭后或在主窗口关闭后关闭。 但是，有时，应用程序会在何时关闭取决于特定于应用程序的其他条件。 你可以通过 <xref:System.Windows.Application.ShutdownMode%2A> 使用以下枚举值之一来指定应用程序将关闭的条件 <xref:System.Windows.ShutdownMode> ：

- <xref:System.Windows.ShutdownMode.OnLastWindowClose>

- <xref:System.Windows.ShutdownMode.OnMainWindowClose>

- <xref:System.Windows.ShutdownMode.OnExplicitShutdown>

的默认值 <xref:System.Windows.Application.ShutdownMode%2A> 为 <xref:System.Windows.ShutdownMode.OnLastWindowClose> ，这意味着当用户关闭应用程序中的最后一个窗口时，应用程序会自动关闭。 但是，如果在主窗口关闭时，应用程序应关闭，则在将设置为时，WPF 会自动执行此功能 <xref:System.Windows.Application.ShutdownMode%2A> <xref:System.Windows.ShutdownMode.OnMainWindowClose> 。 下面的示例说明了这一点。

[!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]

如果有特定于应用程序的关闭条件，则将设置 <xref:System.Windows.Application.ShutdownMode%2A> 为 <xref:System.Windows.ShutdownMode.OnExplicitShutdown> 。 在这种情况下，您负责通过显式调用方法关闭应用程序， <xref:System.Windows.Application.Shutdown%2A> 否则即使关闭所有窗口，应用程序仍将继续运行。 请注意， <xref:System.Windows.Application.Shutdown%2A> 当为或时，将隐式调用 <xref:System.Windows.Application.ShutdownMode%2A> <xref:System.Windows.ShutdownMode.OnLastWindowClose> <xref:System.Windows.ShutdownMode.OnMainWindowClose> 。

> [!NOTE]
> <xref:System.Windows.Application.ShutdownMode%2A> 可从 XBAP 设置，但会被忽略。当在浏览器中离开 XBAP 时，或者当承载 XBAP 的浏览器关闭时，XBAP 始终关闭。 有关详细信息，请参阅 [导航概述](navigation-overview.md)。

#### <a name="session-ending"></a>会话结束

属性描述的关闭条件 <xref:System.Windows.Application.ShutdownMode%2A> 是特定于应用程序的。 不过，在某些情况下，应用程序可能会因外部条件而关闭。 当用户通过以下操作结束 Windows 会话时，将会出现最常见的外部情况：

- 注销

- 关闭

- 重新启动

- 休眠

若要检测 Windows 会话何时结束，可以处理 <xref:System.Windows.Application.SessionEnding> 事件，如以下示例中所示。

[!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]

[!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
[!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]

在此示例中，代码会检查 <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> 属性，以确定如何结束 Windows 会话。 它会根据该值向用户显示确认消息。 如果用户不希望会话结束，则代码会将设置 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 为 `true` 以阻止 Windows 会话结束。

> [!NOTE]
> <xref:System.Windows.Application.SessionEnding> 对于 Xbap，不会引发。

#### <a name="exit"></a>退出

应用程序在关闭时可能需要执行一些最终处理，如保持应用程序状态。 对于这些情况，可以处理 <xref:System.Windows.Application.Exit> 事件，如 `App_Exit` 以下示例中的事件处理程序所示。 它在 *应用程序 .xaml* 文件中定义为事件处理程序。 它在 *App.xaml.cs* 和 *应用程序 .xaml* 文件中突出显示了其实现。

[!code-xaml[Defining-the-Exit-event-handler](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]

[!code-csharp[Handling-the-Exit-event](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=42-55)]
[!code-vb[Handling-the-Exit-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=34-45)]

有关完整的示例，请参阅 [跨应用程序会话保持和还原 Application-Scope 属性](persist-and-restore-application-scope-properties.md)。

<xref:System.Windows.Application.Exit> 独立应用程序和 Xbap 均可处理。 对于 Xbap， <xref:System.Windows.Application.Exit> 将在以下情况下引发：

- 从中导航掉了 XBAP。

- 在 Internet Explorer 中，当承载 XBAP 的选项卡关闭时。

- 关闭浏览器时。

#### <a name="exit-code"></a>退出代码

在大多数情况下，应用程序由操作系统根据用户的请求来启动。 但是，应用程序也可由另一应用程序启动，以执行某项特定任务。 当被启动的应用程序关闭时，执行启动操作的应用程序可能想要了解导致被启动应用程序关闭的条件。 在这些情况下，Windows 允许应用程序在关闭时返回应用程序退出代码。 默认情况下，WPF 应用程序返回退出代码值0。

> [!NOTE]
> 当你从 Visual Studio 进行调试时，应用程序退出代码将在应用程序关闭时显示在 " **输出** " 窗口中，出现如下所示的消息：
>
> `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`
>
> 可以通过单击 "**视图**" 菜单上的 "**输出**" 打开 "**输出**" 窗口。

若要更改退出代码，可以调用 <xref:System.Windows.Application.Shutdown%28System.Int32%29> 重载，该重载接受整数参数作为退出代码：

[!code-csharp[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
[!code-vb[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]

可以通过处理事件来检测退出代码的值并对其进行更改 <xref:System.Windows.Application.Exit> 。 向 <xref:System.Windows.Application.Exit> 事件处理程序传递，该事件处理程序通过 <xref:System.Windows.ExitEventArgs> 属性提供对退出代码的访问 <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> 。 有关详细信息，请参阅 <xref:System.Windows.Application.Exit>。

> [!NOTE]
> 可以在独立的应用程序和 Xbap 中设置退出代码。 但对于 Xbap，将忽略退出代码值。

<a name="Unhandled_Exceptions"></a>

### <a name="unhandled-exceptions"></a>未经处理的异常

有时，应用程序可能会在异常条件下关闭，如引发意外异常时。 在这种情况下，应用程序可能没有可用于检测和处理异常的代码。 这类异常就是未经处理的异常；应用程序会在关闭之前显示一个与下图所示内容类似的通知。

![显示未经处理的异常通知的屏幕截图。](./media/application-management-overview/unhandled-exception-notification.png)

从用户体验的角度来看，应用程序最好通过执行以下部分或全部操作来避免这种默认行为：

- 显示对用户友好的信息。

- 尝试让应用程序保持运行。

- 在 Windows 事件日志中记录详细的、开发人员友好的异常信息。

实现此支持取决于是否能够检测到 <xref:System.Windows.Application.DispatcherUnhandledException> 引发事件的未处理异常。

[!code-xaml[detecting-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]

[!code-csharp[code-to-detect-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs)]
[!code-vb[code-to-detect-unhandled-exceptions](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb)]

向 <xref:System.Windows.Application.DispatcherUnhandledException> 事件处理程序传递一个 <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> 参数，该参数包含有关未经处理的异常的上下文信息，其中包括异常本身 (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>) 。 这些信息可用来确定如何处理异常。

在处理时 <xref:System.Windows.Application.DispatcherUnhandledException> ，应将属性设置 <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> 为 `true` ; 否则，WPF 仍会将异常视为未处理的异常，并恢复到前面所述的默认行为。 如果引发了未经处理的异常且 <xref:System.Windows.Application.DispatcherUnhandledException> 未处理事件，或者处理了事件并且 <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> 将设置为 `false` ，则应用程序将立即关闭。 此外，不 <xref:System.Windows.Application> 会引发任何其他事件。 因此， <xref:System.Windows.Application.DispatcherUnhandledException> 如果应用程序具有必须在应用程序关闭之前运行的代码，则需要处理。

正如下一节所述，虽然应用程序可能会因未经处理的异常而关闭，但通常都是应用户请求而关闭的。

<a name="Application_Lifetime_Events"></a>

### <a name="application-lifetime-events"></a>应用程序生存期事件

独立应用程序和 Xbap 的生存期不完全相同。 下图展示了独立应用程序生存期内的各个关键事件及其引发顺序。

![独立应用程序 &#45; 应用程序对象事件](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")

同样，下图说明了 XBAP 生存期内的键事件，并显示了它们的引发顺序。

![XBAP &#45; 应用程序对象事件](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Application>
- [WPF Windows 概述](wpf-windows-overview.md)
- [导航概述](navigation-overview.md)
- [WPF 应用程序资源、内容和数据文件](wpf-application-resource-content-and-data-files.md)
- [WPF 中的 Pack URI](pack-uris-in-wpf.md)
- [应用程序模型：操作说明主题](/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))
- [应用程序开发](index.md)
