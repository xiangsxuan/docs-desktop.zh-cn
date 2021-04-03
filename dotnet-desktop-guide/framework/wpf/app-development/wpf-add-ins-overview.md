---
title: 外接程序概述
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- add-ins and XAML browser applications [WPF]
- add-ins overview [WPF]
- add-ins [WPF], performance
- add-ins [WPF], benefits
- .NET Framework add-in model [WPF]
- add-ins [WPF], user interface
- add-ins and the user interface [WPF]
- add-ins [WPF], architecture
- add-ins [WPF], limitations
ms.assetid: 00b4c776-29a8-4dba-b603-280a0cdc2ade
ms.openlocfilehash: 5847542a1f51312d525d4939d4b21d11b1a70113
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972965"
---
# <a name="wpf-add-ins-overview"></a>WPF 外接程序概述

<a name="Introduction"></a> .NET Framework 包含外接程序模型，开发人员可以使用该模型来创建支持外接程序扩展性的应用程序。 借助此外接程序模型，可以创建与应用程序功能集成并进行扩展的外接程序。 在某些情况下，应用程序还需要显示外接程序提供的用户界面。本主题演示 WPF 如何补充 .NET Framework 外接程序模型，以实现这些方案、其背后的体系结构、其优点和其局限性。

<a name="Requirements"></a>

## <a name="prerequisites"></a>先决条件

熟悉 .NET Framework 外接程序模型是必需的。 有关详细信息，请参阅[外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))。

<a name="AddInsOverview"></a>

## <a name="add-ins-overview"></a>外接程序概述

为了需要对应用程序重新编译和重新部署才能引入新功能这一复杂过程，应用程序实现了扩展机制，使开发者（包括第一方和第三方）能够创建与应用程序集成的其他应用程序。 支持此扩展性类型的最常见方式是，使用外接程序（也称为“加载项”和“插件”）。 通过外接程序公开扩展性的实际应用程序示例包括：

- Internet Explorer 加载项。

- Windows Media Player 插件。

- Visual Studio 外接程序。

例如，通过 Windows Media Player 外接程序模型，第三方开发人员可以实现“插件”，从而以各种方式对 Windows Media Player 进行扩展，包括为 Windows Media Player 本身不支持的媒体格式（例如 DVD、MP3）创建解码器和编码器，创建音频效果和外观。 尽管有一些实体和行为是所有外接程序模型共有的，但会生成每个外接程序模型以公开某个应用程序的特有功能。

典型外接程序扩展性解决方案的三大实体是“协定”、“外接程序”和“主机应用程序”。 协定会定义外接程序与主机应用程序之间的两种集成方式：

- 外接程序集成主机应用程序所实现的功能。

- 主机应用程序公开供外接程序集成的功能。

为了使外接程序能发挥作用，主机应用程序需要在运行时找到它们并进行加载。 因此，支持外接程序的应用程序需要承担以下附加的职责：

- **发现**：查找遵循主机应用程序所支持的协定的外接程序。

- **激活**：加载和运行外接程序并与它们建立通信。

- **隔离**：使用应用程序域或进程建立隔离边界，以保护应用程序不受外接程序潜在安全问题和执行问题的影响。

- **通信**：通过调用方法和传递数据，允许外接程序和主机应用程序跨过隔离边界相互通信。

- **生存期管理**：通过可预测的干净方式来加载和卸载应用程序域和进程（请参阅 [应用程序域](/dotnet/framework/app-domains/application-domains)）。

- **版本管理**：确保在创建主机应用程序或外接程序的新版本后，它们仍可进行通信。

总之，开发一个可靠的外接程序模型不是一项简单的任务。 出于此原因，.NET Framework 提供了一个用于生成外接程序模型的基础结构。

> [!NOTE]
> 有关外接程序的更多详细信息，请参阅[外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))。

<a name="NETFrameworkAddInModelOverview"></a>

## <a name="net-framework-add-in-model-overview"></a>.NET Framework 外接程序模型概述

命名空间中的 .NET Framework 外接程序模型 <xref:System.AddIn> 包含一组类型，这些类型旨在简化外接程序扩展性的开发。 .NET Framework 外接程序模型的基本单位为协定，该 *协定* 定义主机应用程序和外接程序之间的通信方式。 会使用特定于主机应用程序的协定 *视图* 向主机应用程序公开协定。 同样，向外接程序公开特定于外接程序的协定 *视图*。 使用 *适配器*，主机应用程序和外接程序可以在它们各自的协定视图之间进行通信。 协定、视图和适配器称为管道段，一组相关的管道段组成一条 *管道*。 管道是 .NET Framework 外接程序模型支持发现、激活、安全隔离、执行隔离 (使用应用程序域和进程) 、通信、生存期管理和版本控制的基础。

所有这些支持使得开发人员能够生成与主机应用程序的功能相集成的外接程序。 不过，某些方案需要宿主应用程序显示外接程序提供的用户界面。由于 .NET Framework 中的每个表示技术都有自己的模型来实现用户界面，.NET Framework 外接程序模型不支持任何特定的表示技术。 而 WPF 却扩展了 .NET Framework 外接程序模型，其中包含外接程序的 UI 支持。

<a name="WPFAddInModel"></a>

## <a name="wpf-add-ins"></a>WPF 外接程序

WPF 与 .NET Framework 外接程序模型一起使用，可以解决需要宿主应用程序从外接程序显示用户界面的各种方案。具体而言，WPF 使用以下两种编程模型解决了这些方案：

1. **外接程序返回 UI**。 外接程序通过方法调用向宿主应用程序返回一个 UI，由协定定义。 此方案可用于以下情况：

    - 外接程序返回的 UI 的外观依赖于只在运行时存在的数据或条件，如动态生成的报表。

    - 外接程序提供的服务的 UI 不同于可以使用外接程序的宿主应用程序的 UI。

    - 外接程序主要为主机应用程序执行服务，并使用 UI 向主机应用程序报告状态。

2. **外接程序为 UI**。 外接程序是由协定定义的 UI。 此方案可用于以下情况：

    - 外接程序提供的服务都需要显示，例如广告。

    - 外接程序提供的服务的 UI 对于所有可使用该外接程序的宿主应用程序（如计算器或颜色选取器）都是通用的。

这些方案要求可以在主机应用程序和外接程序应用程序域之间传递 UI 对象。 由于 .NET Framework 外接程序模型依赖于远程处理来在应用程序域之间进行通信，因此在它们之间传递的对象必须是可远程处理的。

可远程处理的对象是某个类的实例，并执行以下一个或多个任务：

- 派生自 <xref:System.MarshalByRefObject> 类。

- 实现 <xref:System.Runtime.Serialization.ISerializable> 接口。

- 应用了 <xref:System.SerializableAttribute> 特性。

> [!NOTE]
> 有关创建可远程处理 .NET Framework 对象的详细信息，请参阅 [使对象可远程](/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100))处理。

WPF UI 类型不能远程处理。 为了解决此问题，WPF 扩展了 .NET Framework 外接程序模型，以允许从主机应用程序显示外接程序创建的 WPF UI。 此支持由 WPF 通过两种类型提供： <xref:System.AddIn.Contract.INativeHandleContract> 由类实现的接口和两个静态方法 <xref:System.AddIn.Pipeline.FrameworkElementAdapters> ： <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 和 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 。 从较高层面来看，这些类型和方法按以下方式使用：

1. WPF 要求外接程序提供的用户界面是直接或间接从派生的类 <xref:System.Windows.FrameworkElement> ，如形状、控件、用户控件、布局面板和页面。

2. 无论协定声明在外接程序和宿主应用程序之间传递 UI，都必须将其声明为 <xref:System.AddIn.Contract.INativeHandleContract> (而不是 <xref:System.Windows.FrameworkElement>) ; <xref:System.AddIn.Contract.INativeHandleContract> 是可在隔离边界之间传递的外接程序 UI 的可远程表示形式。

3. 在从外接程序的应用程序域中传递时， <xref:System.Windows.FrameworkElement> 通过调用将作为打包成 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 。

4. 向宿主应用程序的应用程序域传递后， <xref:System.AddIn.Contract.INativeHandleContract> 必须通过调用将重新打包为 <xref:System.Windows.FrameworkElement> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 。

如何 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 使用、、和 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 取决于具体的方案。 下面几节介绍每个编程模型的详细信息。

<a name="ReturnUIFromAddInContract"></a>

## <a name="add-in-returns-a-user-interface"></a>外接程序返回用户界面

若要使外接程序向宿主应用程序返回 UI，需要满足以下要求：

1. 必须创建宿主应用程序、外接程序和管道，如 .NET Framework [外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) 文档中所述。

2. 协定必须实现 <xref:System.AddIn.Contract.IContract> 并返回 UI，协定必须使用类型为的返回值声明方法 <xref:System.AddIn.Contract.INativeHandleContract> 。

3. 在外接程序和宿主应用程序之间传递的 UI 必须直接或间接从派生 <xref:System.Windows.FrameworkElement> 。

4. 必须先将外接程序返回的 UI 从转换为 <xref:System.Windows.FrameworkElement> ， <xref:System.AddIn.Contract.INativeHandleContract> 然后才能跨越隔离边界。

5. <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.Windows.FrameworkElement> 在跨越隔离边界之后，必须将返回的 UI 从转换为。

6. 宿主应用程序将显示返回的 <xref:System.Windows.FrameworkElement> 。

有关演示如何实现返回 UI 的外接程序的示例，请参阅 [创建返回 Ui 的 Add-In](how-to-create-an-add-in-that-returns-a-ui.md)。

<a name="AddInIsAUI"></a>

## <a name="add-in-is-a-user-interface"></a>外接程序为用户界面

当外接程序为 UI 时，需要以下各项：

1. 必须创建宿主应用程序、外接程序和管道，如 .NET Framework [外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) 文档中所述。

2. 外接程序的协定接口必须实现 <xref:System.AddIn.Contract.INativeHandleContract> 。

3. 传递到主机应用程序的外接程序必须直接或间接从派生 <xref:System.Windows.FrameworkElement> 。

4. 在 <xref:System.Windows.FrameworkElement> <xref:System.AddIn.Contract.INativeHandleContract> 越过隔离边界之前，外接程序必须从转换为。

5. 在 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.Windows.FrameworkElement> 越过隔离边界后，外接程序必须从转换为。

6. 宿主应用程序将显示返回的 <xref:System.Windows.FrameworkElement> 。

有关演示如何实现作为 UI 的外接程序的示例，请参阅 [创建作为 ui 的 Add-In](how-to-create-an-add-in-that-is-a-ui.md)。

<a name="ReturningMultipleUIsFromAnAddIn"></a>

## <a name="returning-multiple-uis-from-an-add-in"></a>从外接程序返回多个 UI

外接程序通常为宿主应用程序提供多个用户界面以显示。 例如，请考虑作为 UI 的外接程序，该外接程序还向宿主应用程序提供状态信息。 此类外接程序可以通过结合使用[外接程序返回用户界面](#ReturnUIFromAddInContract)和[外接程序为用户界面](#AddInIsAUI)模型中的技术来实现。

<a name="AddInsAndXBAPs"></a>

## <a name="add-ins-and-xaml-browser-applications"></a>外接程序和 XAML 浏览器应用程序

到目前为止，示例中的主机应用程序都安装为独立应用程序。 但 XAML 浏览器应用程序 (Xbap) 也可以承载外接程序，但有以下额外的生成和实现要求：

- XBAP 应用程序清单必须经过专门配置，以将管道 (文件夹和程序集) 和外接程序程序集下载到客户端计算机上的 ClickOnce 应用程序缓存中，即 XBAP 所在的文件夹中。

- 用于发现和加载外接程序的 XBAP 代码必须使用 XBAP 的 ClickOnce 应用程序缓存作为管道和外接程序位置。

- 如果外接程序引用位于源站点的松散文件，XBAP 必须将外接程序加载到特殊安全上下文中;当由 Xbap 承载时，外接程序只能引用位于主机应用程序源站点的松散文件。

下面几个小节将详细介绍这些任务。

### <a name="configuring-the-pipeline-and-add-in-for-clickonce-deployment"></a>配置用于 ClickOnce 部署的管道和外接程序

Xbap 将下载到并从 ClickOnce 部署缓存中的一个安全文件夹运行。 为了使 XBAP 承载外接程序，还必须将管道和外接程序程序集下载到 safe 文件夹中。 为此，需要将应用程序清单配置为包含要下载的管道和外接程序程序集。 尽管管道和外接程序程序集需要位于主机 XBAP 项目的根文件夹中，但对于 Visual Studio 检测管道程序集，但这在 Visual Studio 中最容易实现。

因此，第一步是通过设置每个管道程序集和外接程序程序集项目的生成输出，将管道和外接程序程序集生成到 XBAP 项目的根。 下表显示了管道程序集项目和外接程序程序集项目的生成输出路径，该程序集项目位于与宿主 XBAP 项目相同的解决方案和根文件夹中。

表 1：XBAP 承载的管道程序集的生成输出路径

|管道程序集项目|生成输出路径|
|-------------------------------|-----------------------|
|合约|`..\HostXBAP\Contracts\`|
|加载项视图|`..\HostXBAP\AddInViews\`|
|加载项方适配器|`..\HostXBAP\AddInSideAdapters\`|
|宿主端适配器|`..\HostXBAP\HostSideAdapters\`|
|外接程序|`..\HostXBAP\AddIns\WPFAddIn1`|

下一步是通过执行以下操作，将管道程序集和外接程序程序集指定为 Visual Studio 中的 Xbap 内容文件：

1. 通过在“解决方案资源管理器”中右键单击每个管道文件夹，然后选择“包括在项目中”，将管道和外接程序程序集包括在项目中。

2. 在“属性”窗口中，将每个管道程序集和外接程序程序集的“生成操作”都设置为“内容”。

最后一步是配置应用程序清单，以包含要下载的管道程序集文件和外接程序程序集文件。 文件应位于 XBAP 应用程序所占用的 ClickOnce 缓存中文件夹根目录的文件夹中。 通过执行以下操作，可以在 Visual Studio 中实现该配置：

1. 右键单击 XBAP 项目，单击 " **属性**"，单击 " **发布**"，然后单击 " **应用程序文件** " 按钮。

2. 在“应用程序文件”对话框中，将每个管道和外接程序 DLL 的“发布状态”都设置为“包括(自动)”，并将每个管道和外接程序 DLL 的“下载组”都设置为“(必需)”。

### <a name="using-the-pipeline-and-add-in-from-the-application-base"></a>从应用程序基使用管道和外接程序

为 ClickOnce 部署配置管道和外接程序时，会将它们下载到与 XBAP 相同的 ClickOnce 缓存文件夹中。 若要从 XBAP 使用管道和外接程序，XBAP 代码必须从应用程序基获取它们。 使用管道和外接程序的 .NET Framework 外接程序模型的各种类型和成员为此方案提供特殊支持。 首先，路径由 <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase> 枚举值标识。 将此值用于使用管道的相关外接程序成员的重载，这些成员包括：

- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

### <a name="accessing-the-hosts-site-of-origin"></a>访问宿主的源站点

为确保外接程序可以引用源站点的文件，必须使用等效于主机应用程序的安全隔离来加载外接程序。 此安全级别由 <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> 枚举值标识，并在激活外接程序 <xref:System.AddIn.Hosting.AddInToken.Activate%2A> 时传递给方法。

<a name="WPFAddInModelArchitecture"></a>

## <a name="wpf-add-in-architecture"></a>WPF 外接程序体系结构

如我们所见，在最高级别，WPF 允许 .NET Framework 外接程序 <xref:System.Windows.FrameworkElement> 使用、和从) 实现直接或间接派生的用户界面 <xref:System.AddIn.Contract.INativeHandleContract> (<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 。 结果是，主机应用程序返回了一个 <xref:System.Windows.FrameworkElement> ，它从主机应用程序的 UI 中显示。

对于简单的 UI 外接程序方案，这是开发人员所需的详细信息。 对于更复杂的方案（尤其是那些尝试使用其他 WPF 服务（如布局、资源和数据绑定）的情况，需要 WPF 如何扩展带有 UI 支持的 .NET Framework 外接程序模型，以了解其优点和局限性。

从根本上讲，WPF 不会将 UI 从外接程序传递到主机应用程序;而是使用 WPF 互操作性为 UI 传递 Win32 窗口句柄。 因此，当外接程序中的 UI 被传递到主机应用程序时，将发生以下情况：

- 在外接程序端，WPF 会为将由主机应用程序显示的 UI 获取一个窗口句柄。 窗口句柄由派生自并实现的内部 WPF 类封装 <xref:System.Windows.Interop.HwndSource> <xref:System.AddIn.Contract.INativeHandleContract> 。 此类的实例由返回 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> ，并从外接程序的应用程序域封送到主机应用程序的应用程序域。

- 在宿主应用程序端，WPF 将 <xref:System.Windows.Interop.HwndSource> 作为从派生并使用的内部 WPF 类重新打包 <xref:System.Windows.Interop.HwndHost> <xref:System.AddIn.Contract.INativeHandleContract> 。 此类的实例由 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 向宿主应用程序返回。

<xref:System.Windows.Interop.HwndHost> 存在，用于显示 WPF 用户界面中由窗口句柄标识的用户界面。 有关详细信息，请参阅 [WPF 和 Win32 互操作](../advanced/wpf-and-win32-interoperation.md)。

摘要、、 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 和存在， <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 以允许将 WPF UI 的窗口句柄从外接程序传递到主机应用程序，在该应用程序中，它由进行封装 <xref:System.Windows.Interop.HwndHost> 并显示宿主应用程序的 UI。

> [!NOTE]
> 由于宿主应用程序获取 <xref:System.Windows.Interop.HwndHost> ，因此主机应用程序无法将返回的对象转换 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 为它作为该外接程序实现的类型 (例如， <xref:System.Windows.Controls.UserControl>) 。

本质上， <xref:System.Windows.Interop.HwndHost> 具有某些限制，它们会影响主机应用程序使用它们的方式。 不过，WPF 扩展 <xref:System.Windows.Interop.HwndHost> 了多个外接程序方案的功能。 下面介绍这些优点和限制。

<a name="WPFAddInModelBenefits"></a>

## <a name="wpf-add-in-benefits"></a>WPF 外接程序的优点

因为 WPF 外接程序用户界面是使用派生自的内部类从主机应用程序显示的 <xref:System.Windows.Interop.HwndHost> ，所以这些用户界面受 <xref:System.Windows.Interop.HwndHost> 与 WPF UI 服务（如布局、呈现、数据绑定、样式、模板和资源）有关的功能的限制。 不过，WPF 通过其他功能增强了其内部 <xref:System.Windows.Interop.HwndHost> 子类，其中包括：

- 在宿主应用程序的 UI 和外接程序的 UI 之间进行 tab 键切换。 请注意，"外接程序是 UI" 编程模型要求外接程序端适配器进行重写 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> ，以启用 tab 键切换，无论外接程序是完全信任的还是部分信任的。

- 满足从主机应用程序用户界面中显示的外接程序用户界面的辅助功能要求。

- 允许 WPF 应用程序在多个应用程序域方案中安全运行。

- 当外接程序使用安全隔离运行时，阻止对外接程序 UI 窗口句柄进行非法访问 (即部分信任的安全沙箱) 。 调用 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 可确保安全：

  - 对于 "外接程序返回 UI" 编程模型，传递跨隔离边界的外接程序 UI 的窗口句柄的唯一方法是调用 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 。

  - 对于 "外接程序是 UI" 编程模型， <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 在外接程序端适配器上重写并调用 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> (如前面的示例所示) 是必需的，正如从宿主端适配器调用外接程序端适配器的 `QueryContract` 实现一样。

- 提供多个应用程序域执行保护。 由于应用程序域的限制，因此即使存在隔离边界，外接程序应用程序域中引发的未经处理的异常也会导致整个应用程序出现故障。 不过，WPF 和 .NET Framework 外接程序模型提供一种简单的方法来解决此问题并提高应用程序的稳定性。 如果主机应用程序是 WPF 应用程序，则显示 UI 的 WPF 外接程序将 <xref:System.Windows.Threading.Dispatcher> 为运行应用程序域的线程创建。 通过处理 WPF 外接程序的事件，可以检测应用程序域中发生的所有未经处理的异常 <xref:System.Windows.Threading.Dispatcher.UnhandledException> <xref:System.Windows.Threading.Dispatcher> 。 可以 <xref:System.Windows.Threading.Dispatcher> 从 <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> 属性获取。

<a name="WPFAddInModelLimitations"></a>

## <a name="wpf-add-in-limitations"></a>WPF 外接程序限制

除了 WPF 添加到 <xref:System.Windows.Interop.HwndSource> 、和窗口句柄提供的默认行为以外 <xref:System.Windows.Interop.HwndHost> ，还存在从主机应用程序显示的外接程序用户界面的限制：

- 宿主应用程序显示的外接程序用户界面不遵守主机应用程序的剪辑行为。

- 互操作性方案中的“空域”概念也适用于外接程序（请参阅[技术区概述](../advanced/technology-regions-overview.md)）。

- 宿主应用程序的 UI 服务（如资源继承、数据绑定和命令）不会自动提供给外接程序用户界面。 若要向外接程序提供这些服务，需要更新管道。

- 外接程序 UI 不能旋转、缩放、倾斜或以其他方式受转换影响 (请参阅 [转换概述](../graphics-multimedia/transforms-overview.md)) 。

- 由命名空间的绘图操作呈现的外接程序用户界面内的内容 <xref:System.Drawing> 可以包含 alpha 混合。 但是，加载项 UI 和包含它的主机应用程序 UI 必须是100% 不透明;换言之， `Opacity` 两者上的属性必须设置为1。

- 如果 <xref:System.Windows.Window.AllowsTransparency%2A> 宿主应用程序中包含外接程序 UI 的窗口的属性设置为，则外接程序将不 `true` 可见。 即使外接程序 UI 为100% 不透明 (也是如此，属性的值为 `Opacity` 1) 。

- 外接程序 UI 必须出现在同一顶级窗口中的其他 WPF 元素之上。

- 外接程序的 UI 不能使用呈现 <xref:System.Windows.Media.VisualBrush> 。 相反，外接程序可能会拍摄生成的 UI 的快照，以创建一个可以使用协定所定义的方法传递到主机应用程序的位图。

- <xref:System.Windows.Controls.MediaElement>在外接程序 UI 中，无法从中播放媒体文件。

- 为外接程序 UI 生成的鼠标事件既不是由宿主应用程序接收也不会引发， `IsMouseOver` 主机应用程序 ui 的属性的值为 `false` 。

- 当焦点在外接程序 UI 中的控件之间移动时， `GotFocus` 和 `LostFocus` 事件既不会接收，也不会由主机应用程序引发。

- 在打印时，包含外接程序 UI 的主机应用程序部分显示为白色。

- <xref:System.Windows.Threading.Dispatcher>如果主机应用程序继续执行，则在卸载 owner 外接程序之前，必须手动关闭所有调度程序 (查看由外接程序 UI 创建) 。 协定可以实现一些方法，这些方法允许主机应用程序在外接程序卸载之前通知外接程序，从而允许外接程序 UI 关闭其调度程序。

- 如果外接程序 UI 是 <xref:System.Windows.Controls.InkCanvas> 或包含 <xref:System.Windows.Controls.InkCanvas> ，则不能卸载外接程序。

<a name="PerformanceOptimization"></a>

## <a name="performance-optimization"></a>性能优化

默认情况下，当使用多个应用程序域时，每个应用程序所需的各种 .NET Framework 程序集都将加载到该应用程序的域中。 因此，创建新应用程序域和在应用程序域中启动应用程序所需的时间可能会影响性能。 不过，通过指示应用程序在已加载的应用程序域之间共享程序集，.NET Framework 提供了一种减少开始时间的方法。 为此，需要使用 <xref:System.LoaderOptimizationAttribute> 属性，该属性必须应用于入口点方法 (`Main`) 。 这种情况下，只能使用代码来实现应用程序定义（请参阅[应用程序管理概述](application-management-overview.md)）。

## <a name="see-also"></a>另请参阅

- <xref:System.LoaderOptimizationAttribute>
- [外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [应用程序域](/dotnet/framework/app-domains/application-domains)
- [.NET Framework 远程处理概述](/previous-versions/dotnet/netframework-4.0/kwdt6w2k(v=vs.100))
- [使对象可远程处理](/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100))
- [操作指南主题](how-to-topics.md)
