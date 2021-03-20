---
title: WPF 和 Win32 互操作
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: 87c2ec5bd52921221b65b7b55aeae9f92555ba83
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667052"
---
# <a name="wpf-and-win32-interoperation"></a>WPF 和 Win32 互操作

本主题概述了如何互操作 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 和 Win32 代码。 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 提供了用于创建应用程序的丰富环境。 但是，当你在 Win32 代码中有大量投资时，重复使用其中的某些代码可能会更有效。

<a name="basics"></a>

## <a name="wpf-and-win32-interoperation-basics"></a>WPF 和 Win32 互操作基础知识

和 Win32 代码之间的互操作有两种基本方法 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。

- [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]在 Win32 窗口中承载内容。 使用此方法，你可以在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 标准 Win32 窗口和应用程序的框架中使用的高级图形功能。

- 在内容中托管 Win32 窗口 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 使用此技术，可以在其他内容的上下文中使用现有的自定义 Win32 控件 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，并跨边界传递数据。

本主题中对上述每种方法进行了概念性介绍。 有关在 Win32 中承载的更面向代码的说明 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，请参阅 [演练：在 Win32 中承载 WPF 内容](walkthrough-hosting-wpf-content-in-win32.md)。 有关在中承载 Win32 的更面向代码的说明 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，请参阅 [演练：在 WPF 中承载 win32 控件](walkthrough-hosting-a-win32-control-in-wpf.md)。

<a name="projects"></a>

## <a name="wpf-interoperation-projects"></a>WPF 互操作项目

[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Api 是托管代码，但大多数现有 Win32 程序都是用非托管 c + + 编写的。  不能 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 从真正的非托管程序调用 api。 但是，通过将 `/clr` 选项与 Microsoft Visual C++ 编译器一起使用，你可以创建混合托管的非托管程序，你可以在其中无缝混合托管和非托管的 API 调用。

一个项目级别的难点在于，您不能将 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 文件编译为 c + + 项目。  可通过一些项目分离技术对此进行弥补。

- 创建一个 c # DLL，其中包含所有 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 页面作为已编译的程序集，然后让 c + + 可执行文件将该 dll 作为引用。

- 为内容创建 c # 可执行文件 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，并使其引用包含 Win32 内容的 c + + DLL。

- 使用 <xref:System.Windows.Markup.XamlReader.Load%2A> [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 在运行时加载任何，而不编译 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。

- 不要使用 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，而是编写所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 的代码，并从生成元素树 <xref:System.Windows.Application> 。

请使用最适合你的方法。

> [!NOTE]
> 如果你之前未使用过 c + +/CLI，你可能会注意到一些 "新建" 关键字（例如 `gcnew` 和） `nullptr` 在互操作代码示例中。 这些关键字将取代旧的双下划线语法 (`__gc`) 并为 c + + 中的托管代码提供更自然的语法。  若要了解有关 c + +/CLI 托管功能的详细信息，请参阅 [运行时平台的组件扩展](/cpp/windows/component-extensions-for-runtime-platforms)。

<a name="hwnds"></a>

## <a name="how-wpf-uses-hwnds"></a>WPF 如何使用 Hwnd

若要充分利用 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]“HWND 互操作”，需要了解 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 如何使用 HWND。 对于任何 HWND，不能 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 使用 DirectX 呈现或 gdi/GDI + 呈现来混合呈现。 这具有许多影响。 首先，若要混合这些绘制模型，必须创建互操作解决方案，并对选择使用的每个绘制模型使用互操作的指定段。 此外，绘制行为会为互操作解决方案可实现的操作创建一个“空域”限制。 有关“空域”概念的详细信息，请参见[技术区概述](technology-regions-overview.md)主题。

屏幕上的所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 元素最终受 HWND 支持。 当你创建时 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> ，将 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 创建一个顶级 HWND，并使用将及其 <xref:System.Windows.Interop.HwndSource> 内容放入 <xref:System.Windows.Window> [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] HWND。  应用程序中的其余 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容共享单个 HWND。 菜单、组合框下拉列表和其他弹出窗口例外。 这些元素会创建自己的顶层窗口，因此 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 菜单可能超出所在窗口 HWND 的边缘。 使用在 <xref:System.Windows.Interop.HwndHost> 中放置 HWND 时 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 通知 Win32 如何相对于 HWND 定位新的子 HWND [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> 。

与之相关的 HWND 概念是每个 HWND 内及其之间的透明度。 [技术区概述](technology-regions-overview.md)主题中对此也有相关介绍。

<a name="hosting_a_wpf_page"></a>

## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>在 Microsoft Win32 窗口中承载 WPF 内容

[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]在 Win32 窗口中承载的关键是 <xref:System.Windows.Interop.HwndSource> 类。 此类 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 在 Win32 窗口中包装内容，以便 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 可以将内容作为子窗口合并到中 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 。 下面的方法将 Win32 和组合到 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 一个应用程序中。

1. 将 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容（内容根元素）作为托管类实现。 通常，类继承自一个可包含多个子元素和/或用作根元素（例如或）的类 <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Page> 。 后续步骤中，此类被称为 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容类，此类的实例被称为 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容对象。

2. 使用 c + +/CLI 实现 Windows 应用程序 如果是从现有的非托管 c + + 应用程序开始，则通常可以通过将项目设置更改为包含编译器标志来使其调用托管代码， `/clr` (`/clr` 本主题中未说明支持编译所需的完整范围) 。

3. 将线程处理模型设置为单线程单元 (STA)。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 使用此线程模型。

4. 处理窗口过程中的 WM_CREATE 通知。

5. 在处理程序（或处理程序调用的函数）中，执行以下操作：

    1. <xref:System.Windows.Interop.HwndSource>使用父窗口 HWND 作为其参数创建一个新的对象 `parent` 。

    2. 创建 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容类的一个实例。

    3. 将对内容对象的引用分配 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 给 <xref:System.Windows.Interop.HwndSource> 对象 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 属性。

    4. <xref:System.Windows.Interop.HwndSource>对象 <xref:System.Windows.Interop.HwndSource.Handle%2A> 属性包含 (HWND) 的窗口句柄。 要获取可在应用程序的非托管部分中使用的 HWND，需将 `Handle.ToPointer()` 强制装换为 HWND。

6. 实现一个托管类，该类包含一个用于保存对 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容对象的引用的静态字段。 使用此类可以从 Win32 代码中获取对 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容对象的引用，但更重要的是，它可以防止无意中对其进行 <xref:System.Windows.Interop.HwndSource> 垃圾回收。

7. 通过将处理程序附加到一个或多个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容对象事件，接收 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容对象的通知。

8. 通过使用存储在静态字段中的引用设置属性、调用方法等，与 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容对象进行通信。

> [!NOTE]
> 如果生成一个单独的程序集然后对其进行引用，对于步骤 1，可使用内容类的默认分部类在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中完成部分或全部 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容类定义。 虽然在 <xref:System.Windows.Application> 将对象编译为程序集的过程中通常包括一个对象 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，但最终不会将其 <xref:System.Windows.Application> 作为互操作的一部分使用，只需对应用程序所引用的文件使用一个或多个根类， [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 并引用其分部类。 该过程的其余部分基本与上述相似。
>
> [演练：在 Win32 中承载 WPF 内容](walkthrough-hosting-wpf-content-in-win32.md)主题中对这些每个步骤通过代码进行了说明。

<a name="hosting_an_hwnd"></a>

## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>在 WPF 中承载 Microsoft Win32 窗口

在其他内容中承载 Win32 窗口的关键 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 是 <xref:System.Windows.Interop.HwndHost> 类。 该类在可添加到 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 元素树的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 元素中包装窗口。 <xref:System.Windows.Interop.HwndHost> 还支持 Api，这些 Api 允许您将此类任务作为托管窗口的进程消息执行。 基本过程：

1. 为 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序创建一个元素树（可通过代码或标记）。 在元素树中查找 <xref:System.Windows.Interop.HwndHost> 可作为子元素添加的相应和允许的点。 剩余步骤中，此元素称为保留元素。

2. 派生自 <xref:System.Windows.Interop.HwndHost> 以创建保存 Win32 内容的对象。

3. 在该宿主类中，重写 <xref:System.Windows.Interop.HwndHost> 方法 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> 。 返回承载窗口的 HWND。 可能需要将实际控件包装为返回窗口的子窗口；在承载窗口中包装控件为 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容从控件接收通知提供了一种简单的方式。 此方法有助于纠正有关托管控件边界上的消息处理的某些 Win32 问题。

4. 重写 <xref:System.Windows.Interop.HwndHost> 方法 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 和 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 。 这样做的目的是处理清除和删除对承载内容的引用，尤其是在已创建对非托管对象的引用的情况下。

5. 在代码隐藏文件中，创建控件承载类的一个实例，并使其成为保留元素的子元素。 通常，使用事件处理程序 <xref:System.Windows.FrameworkElement.Loaded> ，如，或使用分部类构造函数。 但也可通过运行时行为添加互操作内容。

6. 处理选择的窗口消息，例如控件通知。 方法有两种。 两种方法提供对消息流的相同访问权限，因此你的选择很大程度上取决于编程简便性。

    - 实现所有消息的消息处理 (不只是在重写方法时) 关闭 <xref:System.Windows.Interop.HwndHost> 消息 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 。

    - 让宿主 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 元素通过处理事件来处理消息 <xref:System.Windows.Interop.HwndHost.MessageHook> 。 对发送到承载窗口的主窗口过程的每个消息都会引发该事件。

    - 不能使用在进程外的窗口处理消息 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 。

7. 通过使用平台调用来调用非托管 `SendMessage` 函数，与承载窗口通信。

按照这些步骤，创建一个处理鼠标输入的应用程序。 通过实现接口，可以为您的托管窗口添加 tab 键支持 <xref:System.Windows.Interop.IKeyboardInputSink> 。

[演练：在 WPF 中承载 Win32 控件](walkthrough-hosting-a-win32-control-in-wpf.md)主题中对这些每个步骤通过代码进行了说明。

### <a name="hwnds-inside-wpf"></a>WPF 内部的 Hwnd

您可以 <xref:System.Windows.Interop.HwndHost> 将视为一种特殊的控件。 从技术上说， <xref:System.Windows.Interop.HwndHost> 它是一个 <xref:System.Windows.FrameworkElement> 派生类，而不是一个 <xref:System.Windows.Controls.Control> 派生类，但可以将其视为用于互操作的控件。 ) <xref:System.Windows.Interop.HwndHost> 抽象所承载内容的基础 Win32 性质，使 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 托管内容成为另一个类似控件的对象，该对象应呈现并处理输入。 ( <xref:System.Windows.Interop.HwndHost> 通常的行为与任何其他行为相同 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement> ，不过，在输出 (图形和图形之间存在一些重要差异，) 和输入 (鼠标和键盘，) 基于底层 hwnd 可支持的限制。

#### <a name="notable-differences-in-output-behavior"></a>输出行为的显著差异

- <xref:System.Windows.FrameworkElement>，它是 <xref:System.Windows.Interop.HwndHost> 基类，具有表示 UI 更改的几个属性。 其中包括诸如之类的属性，这些属性 <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType> 将元素内元素的布局更改为父级。 但是，这些属性中的大部分都不会映射到可能的 Win32 等效项，即使存在此类等效项也是如此。 过多这些属性及其含义具有过高的绘制技术针对性，这使得映射并不可行。 因此，设置等属性 <xref:System.Windows.FrameworkElement.FlowDirection%2A> <xref:System.Windows.Interop.HwndHost> 不起作用。

- <xref:System.Windows.Interop.HwndHost> 不能旋转、缩放、倾斜或以其他方式受转换影响。

- <xref:System.Windows.Interop.HwndHost> 不支持 <xref:System.Windows.UIElement.Opacity%2A> 属性 (alpha 混合) 。 如果中的内容 <xref:System.Windows.Interop.HwndHost> 执行 <xref:System.Drawing> 包含 alpha 信息的操作，则不会发生冲突，但 <xref:System.Windows.Interop.HwndHost> 作为整体仅支持 Opacity = 1.0 (100% ) 。

- <xref:System.Windows.Interop.HwndHost> 将显示在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 同一顶级窗口中的其他元素之上。 但是， <xref:System.Windows.Controls.ToolTip> 或 <xref:System.Windows.Controls.ContextMenu> 生成的菜单是单独的顶级窗口，因此在中将正常运行 <xref:System.Windows.Interop.HwndHost> 。

- <xref:System.Windows.Interop.HwndHost> 不遵守其父项的剪辑区域 <xref:System.Windows.UIElement> 。 如果尝试将某个 <xref:System.Windows.Interop.HwndHost> 类放置在滚动区域或中，这可能是一个问题 <xref:System.Windows.Controls.Canvas> 。

#### <a name="notable-differences-in-input-behavior"></a>输入行为的显著差异

- 通常，当输入设备在托管的 Win32 区域内范围内时 <xref:System.Windows.Interop.HwndHost> ，输入事件会直接跳到 win32。

- 当鼠标悬停在上时 <xref:System.Windows.Interop.HwndHost> ，应用程序不会接收 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 鼠标事件，并且属性的值 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.IsMouseOver%2A> 将为 `false` 。

- 当 <xref:System.Windows.Interop.HwndHost> 具有键盘焦点时，应用程序不会接收 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 键盘事件，并且属性的值 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> 将为 `false` 。

- 当焦点在内 <xref:System.Windows.Interop.HwndHost> 并且更改到中的另一个控件时 <xref:System.Windows.Interop.HwndHost> ，应用程序将不会接收 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 事件 <xref:System.Windows.UIElement.GotFocus> 或 <xref:System.Windows.UIElement.LostFocus> 。

- 相关的触笔属性和事件类似，当触笔悬停于上方时不报告信息 <xref:System.Windows.Interop.HwndHost> 。

<a name="tabbing_mnemonics_accelerators"></a>

## <a name="tabbing-mnemonics-and-accelerators"></a>Tab 键、助记键和加速键

<xref:System.Windows.Interop.IKeyboardInputSink>和 <xref:System.Windows.Interop.IKeyboardInputSite> 接口允许您为混合 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 和 Win32 应用程序创建无缝键盘体验：

- 在 Win32 和组件之间切换 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]

- 焦点位于 Win32 组件内和 WPF 组件内时皆起作用的助记键和加速键。

<xref:System.Windows.Interop.HwndHost>和 <xref:System.Windows.Interop.HwndSource> 类都提供了的实现 <xref:System.Windows.Interop.IKeyboardInputSink> ，但它们可能不会处理你需要用于更高级方案的所有输入消息。 替换为适当方法，获取所需的键盘行为。

接口仅为在和 Win32 区域之间的转换时所发生的情况提供支持 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 在 Win32 区域内，按 tab 键（如果有）的 Win32 实现逻辑完全控制 tab 键行为。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Interop.HwndHost>
- <xref:System.Windows.Interop.HwndSource>
- <xref:System.Windows.Interop>
- [演练：在 WPF 中承载 Win32 控件](walkthrough-hosting-a-win32-control-in-wpf.md)
- [演练：在 Win32 中承载 WPF 内容](walkthrough-hosting-wpf-content-in-win32.md)
