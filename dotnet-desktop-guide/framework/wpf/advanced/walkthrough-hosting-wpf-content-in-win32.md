---
title: 在 Win32 中承载 WPF 内容
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
ms.openlocfilehash: 40dbd6a4d53c96c8d24384ad097752825d365a9f
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665284"
---
# <a name="walkthrough-hosting-wpf-content-in-win32"></a>演练：在 Win32 中承载 WPF 内容
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 提供了用于创建应用程序的丰富环境。 但是，当你在 Win32 代码中有大量投资时，向 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序添加功能（而不是重写原始代码）可能更有效。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供了一种简单的机制，用于 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 在 Win32 窗口中承载内容。  
  
 本教程介绍如何编写示例应用程序， [在 Win32 窗口中承载 WPF 内容在](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32HostingWPFPage)win32 窗口中承载 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容。 你可以扩展此示例来托管任何 Win32 窗口。 由于它涉及混合托管代码和非托管代码，因此，应用程序是用 c + +/CLI 编写的。  

<a name="requirements"></a>
## <a name="requirements"></a>要求  
 本教程假定你基本熟悉 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 和 Win32 编程。 有关编程的基本简介 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，请参阅 [入门](../getting-started/index.md)。 有关 Win32 编程的简介，你应在主题上通过 Charles Petzold 在特定 *编程窗口* 中引用任意一本书。  
  
 由于本教程随附的示例是在 c + +/CLI 中实现的，因此本教程假定你熟悉如何使用 c + + 对 Windows API 进行编程，并了解托管代码编程。 熟悉 c + +/CLI 非常有用，但并不重要。  
  
> [!NOTE]
> 本教程包括来自相关示例的一些代码示例。 但是，出于可读性考虑，不包括完整的示例代码。 有关完整的示例代码，请参阅 [在 Win32 窗口中承载 WPF 内容示例](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32HostingWPFPage)。  
  
<a name="basic_procedure"></a>
## <a name="the-basic-procedure"></a>基本过程  
 本部分概述了用于 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 在 Win32 窗口中承载内容的基本过程。 其余章节说明每个步骤的详细内容。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]在 Win32 窗口中承载内容的关键是 <xref:System.Windows.Interop.HwndSource> 类。 此类 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 在 Win32 窗口中包装内容，从而使其可以 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 作为子窗口合并到中。 下面的方法将 Win32 和组合到 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 一个应用程序中。  
  
1. 将你 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 的内容作为托管类实现。  
  
2. 使用 c + +/CLI 实现 Windows 应用程序 如果从现有应用程序和非托管 c + + 代码开始，你通常可以通过更改项目设置以包括编译器标志来使其可以调用托管代码 `/clr` 。  
  
3. 将线程处理模型设置为单线程单元 (STA)。  
  
4. 在窗口过程中处理 [WM_CREATE](/windows/desktop/winmsg/wm-create)通知，并执行以下操作：  
  
    1. 创建一个新的 <xref:System.Windows.Interop.HwndSource> 对象，将父窗口用作其 `parent` 参数。  
  
    2. 创建 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容类的一个实例。  
  
    3. 向的属性分配对 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容对象的引用 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> <xref:System.Windows.Interop.HwndSource> 。  
  
    4. 获取该内容的 HWND。 <xref:System.Windows.Interop.HwndSource.Handle%2A> 对象的 <xref:System.Windows.Interop.HwndSource> 属性包含窗口句柄 (HWND)。 要获取可在应用程序的非托管部分中使用的 HWND，需将 `Handle.ToPointer()` 强制装换为 HWND。  
  
5. 实现一个托管类，该类包含一个用于保存对 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容的引用的静态字段。 此类允许您 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 从您的 Win32 代码获取对内容的引用。  
  
6. 向静态字段分配 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容。  
  
7. [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]通过将处理程序附加到一个或多个事件来从内容接收通知 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
8. 通过使用存储在静态字段中用于设置属性等的引用来与 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容通信。  
  
> [!NOTE]
> 你还可以使用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 来实现 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容。 但是，您必须将它单独编译为动态链接库 (DLL) 并从 Win32 应用程序中引用该 DLL。 该过程的其余部分与上述相似。

<a name="implementing_the_application"></a>
## <a name="implementing-the-host-application"></a>实现主机应用程序
 本节介绍如何 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 在基本的 Win32 应用程序中托管内容。 内容本身在 c + +/CLI 中作为托管类实现。 大多数情况下，它是简单的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 编程。 内容实现的主要方面在 [实现 WPF 内容](#implementing_the_wpf_page)中进行了讨论。

- [基本应用程序](#the_basic_application)

- [承载 WPF 内容](#hosting_the_wpf_page)

- [保存对 WPF 内容的引用](#holding_a_reference)

- [与 WPF 内容通信](#communicating_with_the_page)

<a name="the_basic_application"></a>
### <a name="the-basic-application"></a>基本应用程序
 主机应用程序的起点是创建 Visual Studio 2005 模板。

1. 打开 Visual Studio 2005，然后从 "**文件**" 菜单中选择 "**新建项目**"。

2. 从 Visual C++ 项目类型列表中选择 " **Win32** "。 如果默认语言不是 c + +，则会在 " **其他语言**" 下找到这些项目类型。

3. 选择 " **Win32 项目** " 模板，为项目分配一个名称，然后单击 **"确定"** 以启动 " **Win32 应用程序向导**"。

4. 接受向导的默认设置，然后单击 " **完成** " 以启动项目。

 该模板将创建一个基本的 Win32 应用程序，其中包括：

- 应用程序的入口点。

- 一个窗口和关联的窗口过程 (WndProc)。

- 包含 **文件** 和 **帮助** 标题的菜单。 " **文件** " 菜单具有用于关闭应用程序的 " **退出** " 项。 " **帮助** " 菜单具有用于启动一个简单对话框的 " **关于** " 项。

 在开始编写代码以托管内容之前 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，需要对基本模板进行两次修改。

 第一项是将项目作为托管代码进行编译。 默认情况下，项目将作为非托管代码进行编译。 但是，由于 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 是在托管代码中实现的，因此必须将项目进行相应编译。

1. 在 **解决方案资源管理器** 中右键单击项目名称，然后从上下文菜单中选择 " **属性** " 以启动 " **属性页** " 对话框。

2. 从左窗格中的树视图中选择 " **配置属性** "。

3. 从右窗格中的 "**项目默认值**" 列表中选择 "**公共语言运行时** 支持"。

4. 从下拉列表框中 **(/clr) 选择 "公共语言运行时支持** "。

> [!NOTE]
> 此编译器标志使你能够在应用程序中使用托管代码，但非托管代码将仍将像以前一样进行编译。

 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 使用单线程单元 (STA) 线程处理模型。 若要正常使用 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容代码，必须通过对入口点应用特性，将应用程序的线程模型设置为 STA。

 [!code-cpp[Win32HostingWPFPage#WinMain](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]

<a name="hosting_the_wpf_page"></a>
### <a name="hosting-the-wpf-content"></a>承载 WPF 内容
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]内容是一个简单的地址条目应用程序。 它包含若干个 <xref:System.Windows.Controls.TextBox> 控件，这些控件用于获得用户名称、地址等。 还有两个 <xref:System.Windows.Controls.Button> 控件，即 **"确定" 和 "** **取消**"。 当用户单击 **"确定**" 时，按钮的 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件处理程序将从控件中收集数据 <xref:System.Windows.Controls.TextBox> ，将其分配给相应的属性，并引发自定义事件 `OnButtonClicked` 。 当用户单击 " **取消**" 时，处理程序将直接引发 `OnButtonClicked` 。 `OnButtonClicked` 的事件参数对象包含布尔型字段，用于指示被单击的按钮。

 宿主内容的代码 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 在主机窗口上的 [WM_CREATE](/windows/desktop/winmsg/wm-create) 通知的处理程序中实现。

 [!code-cpp[Win32HostingWPFPage#WMCreate](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]

 `GetHwnd`方法使用大小和位置信息以及父窗口句柄并返回所承载内容的窗口句柄 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。

> [!NOTE]
> 无法对 `#using` 命名空间使用 `System::Windows::Interop` 指令。 如果进行此操作，将造成该命名空间中的 <xref:System.Windows.Interop.MSG> 结构和在 winuser.h 中声明的 MSG 结构之间的名称冲突。 必须使用完全限定名来访问该命名空间的内容。

 [!code-cpp[Win32HostingWPFPage#GetHwnd](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]

 你不能 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 直接在应用程序窗口中托管内容。 从而，首先创建 <xref:System.Windows.Interop.HwndSource> 对象以包装 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容。 此对象基本上是设计用于托管内容的窗口 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 <xref:System.Windows.Interop.HwndSource>通过将对象创建为 Win32 窗口的子窗口（它是应用程序的一部分），将其承载于父窗口中。 <xref:System.Windows.Interop.HwndSource>构造函数参数包含的信息与你在创建 Win32 子窗口时要传递给 CreateWindow 的信息几乎相同。

 接下来，创建 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容对象的实例。 在这种情况下， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] `WPFPage` 使用 c + +/cli 将内容作为单独的类实现 还可以使用 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 实现 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 内容。 但是，若要执行此操作，需要设置一个单独的项目，并将 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容构建为 DLL。 可以向项目中添加对该 DLL 的引用，并使用该引用创建内容的实例 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。

 通过向的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 属性分配对内容的引用，可在子窗口中显示内容 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Interop.HwndSource.RootVisual%2A> <xref:System.Windows.Interop.HwndSource> 。

 代码的下一行将一个事件处理程序 `WPFButtonClicked` 附加到 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容 `OnButtonClicked` 事件。 当用户单击 **"确定" 或 "** **取消** " 按钮时，将调用此处理程序。 有关此事件处理程序的进一步讨论，请参阅 [communicating_with_the_WPF 内容](#communicating_with_the_page) 。

 代码显示的最后一行返回与 <xref:System.Windows.Interop.HwndSource> 对象关联的窗口句柄 (HWND)。 您可以使用 Win32 代码中的此句柄将消息发送到托管窗口，尽管该示例不这样做。 每当 <xref:System.Windows.Interop.HwndSource> 对象收到一条消息时就会引发一个事件。 若要处理消息，请调用 <xref:System.Windows.Interop.HwndSource.AddHook%2A> 方法来附加消息处理程序，然后在此处理程序中处理消息。

<a name="holding_a_reference"></a>
### <a name="holding-a-reference-to-the-wpf-content"></a>保存对 WPF 内容的引用
 对于许多应用程序，你将需要稍后与 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容进行通信。 例如，可能需要修改 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容属性，或可能让 <xref:System.Windows.Interop.HwndSource> 对象托管不同的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容。 执行此操作需要对 <xref:System.Windows.Interop.HwndSource> 对象或 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容的引用。 <xref:System.Windows.Interop.HwndSource> 对象及其关联 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容保留在内存中，直到销毁窗口句柄。 但是，一旦从窗口过程返回，分配给 <xref:System.Windows.Interop.HwndSource> 对象的变量就将超出范围。 处理 Win32 应用程序的这一问题的习惯方法是使用静态或全局变量。 遗憾的是，你无法向这些类型的变量分配托管对象。 可以向全局或静态变量分配与 <xref:System.Windows.Interop.HwndSource> 对象关联的窗口句柄，但这一操作不会提供对对象本身的访问。

 针对这一问题最简单的解决方案是实现一个托管类，该类包含一组静态字段，这些字段保存对需要访问的任何托管对象的引用。 此示例使用 `WPFPageHost` 类来保存对 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容的引用，以及对该内容某些属性的初始值的引用（用户以后可能会对这些属性进行更改）。 这在标头中进行定义。

 [!code-cpp[Win32HostingWPFPage#WPFPageHost](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]

 `GetHwnd` 函数的后半部分将值分配给这些字段以供以后使用（在 `myPage` 仍处于范围内时）。

<a name="communicating_with_the_page"></a>
### <a name="communicating-with-the-wpf-content"></a>与 WPF 内容通信
 与 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容的通信有两种类型。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]当用户单击 **"确定" 或 "** **取消**" 按钮时，应用程序接收来自内容的信息。 该应用程序还具有 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]，使用户可以更改各种 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容属性，例如背景色或默认字体大小。

 如上所述，用户单击任一按钮时，[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容将引发 `OnButtonClicked` 事件。 该应用程序将一个处理程序附加到此事件以接收这些通知。 如果单击 **"确定"** 按钮，则处理程序将从内容获取用户信息 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 并将其显示在一组静态控件中。

 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]

 该处理程序从 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容接收到一个自定义事件参数对象 `MyPageEventArgs`。 `IsOK` `true` 如果单击 **"确定"** 按钮，则对象的属性设置为， `false` 如果单击 "**取消**" 按钮，则设置为。

 如果单击了 **"确定"** 按钮，则处理程序将从容器类获取对内容的引用 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 然后它会收集由关联的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容属性保存的用户信息，并使用静态控件在父窗口上显示该信息。 由于 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容数据的形式为托管字符串，因此必须对其进行封送处理以供 Win32 控件使用。 如果单击了 " **取消** " 按钮，处理程序将清除静态控件中的数据。

 应用程序 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 提供一组单选按钮，允许用户修改 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容的背景色和若干与字体相关的属性。 下面的示例是应用程序的窗口过程 (WndProc) 的一段摘录及其消息处理功能，通过该功能可设置不同消息上的各种属性，包括背景色。 其他内容与此类似，将不进行展示。 请查看完整示例了解详细信息和上下文。

 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]

 若要设置背景色，请从 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 获取对 `hostedPage` 内容 (`WPFPageHost`) 的引用并将背景色属性设置为适当的颜色。 此示例使用三种颜色选项：原始颜色、浅绿色或浅橙红色。 原始背景色作为静态字段存储在 `WPFPageHost` 类中。 若要设置其他两种颜色，请创建一个新的 <xref:System.Windows.Media.SolidColorBrush> 对象，并从 <xref:System.Windows.Media.Colors> 对象向构造函数传递一个静态颜色值。

<a name="implementing_the_wpf_page"></a>
## <a name="implementing-the-wpf-page"></a>实现 WPF 页
 你可以在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 不了解实际实现的情况下托管和使用内容。 如果 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 已将内容打包到了单独的 DLL 中，则可能是在任何公共语言运行时 (CLR) 语言中生成的。 下面是示例中使用的 c + +/CLI 实现的简短演练。 本节包含下列子节。

- [布局](#page_layout)

- [将数据返回到主机窗口](#returning_data_to_window)

- [设置 WPF 属性](#set_page_properties)

<a name="page_layout"></a>
### <a name="layout"></a>Layout
 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]内容中的元素 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 由五个 <xref:System.Windows.Controls.TextBox> 控件组成，它们具有关联 <xref:System.Windows.Controls.Label> 控件：名称、地址、城市、省/市/自治区和邮政编码。 还有两个 <xref:System.Windows.Controls.Button> 控件，即 **"确定" 和 "** **取消**"

 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容在 `WPFPage` 类中实现。 布局通过 <xref:System.Windows.Controls.Grid> 布局元素进行处理。 该类继承自实际使其成为 <xref:System.Windows.Controls.Grid> 内容根元素的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]。

 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]内容构造函数采用所需的宽度和高度，并 <xref:System.Windows.Controls.Grid> 相应地调整大小。 然后，它通过创建一组 <xref:System.Windows.Controls.ColumnDefinition> 和 <xref:System.Windows.Controls.RowDefinition> 对象并将它们分别添加到 <xref:System.Windows.Controls.Grid> 对象基 <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> 和 <xref:System.Windows.Controls.Grid.RowDefinitions%2A> 集合来定义基本布局。 这将定义具有 5 行和 7 列的网格，该网格具有单元内容定义的维度。

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]

 接下来，此构造函数将 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 元素添加到 <xref:System.Windows.Controls.Grid>。 第一个元素是标题文本，这是一个在网格首行居中的 <xref:System.Windows.Controls.Label> 控件。

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]

 下一行包含名称 <xref:System.Windows.Controls.Label> 控制及其关联的 <xref:System.Windows.Controls.TextBox> 控件。 由于对每个标签/文本框对使用同一代码，因而该代码被置于一对专用方法内并用于所有五个标签/文本框对。 该方法创建相应的控件，并调用 <xref:System.Windows.Controls.Grid> 类静态 <xref:System.Windows.Controls.Grid.SetColumn%2A> 和 <xref:System.Windows.Controls.Grid.SetRow%2A> 方法，以将控件置于相应单元格内。 创建控件后，该示例对 <xref:System.Windows.Controls.UIElementCollection.Add%2A> 的 <xref:System.Windows.Controls.Panel.Children%2A> 属性调用 <xref:System.Windows.Controls.Grid> 方法，以便将控件添加到网格。 用于添加剩余标签/文本框对的代码相似。 请参阅示例代码了解详细信息。

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]

 这两种方法的实现如下所示：

 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]

 最后，该示例添加 **"确定" 和 "** **取消** " 按钮，并将事件处理程序附加到其 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件。

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]

<a name="returning_data_to_window"></a>
### <a name="returning-the-data-to-the-host-window"></a>将数据返回到主机窗口
 单击任一按钮后，将引发其 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件。 主机窗口只需将处理程序附加到这些事件，然后直接从 <xref:System.Windows.Controls.TextBox> 控件获取数据。 此示例使用的是不太直接的方法。 它在 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 内容中处理 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，然后引发自定义事件 `OnButtonClicked` 以通知 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容。 这使 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容能够在通知主机之前执行某些参数验证。 该处理程序从 <xref:System.Windows.Controls.TextBox> 控件获取文本，然后将其分配给公共属性（主机可从其中检索信息）。

 WPFPage.h 中的事件声明：

 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]

 WPFPage.cpp 中的 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件处理程序：

 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]

<a name="set_page_properties"></a>
### <a name="setting-the-wpf-properties"></a>设置 WPF 属性
 Win32 宿主允许用户更改多个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容属性。 从 Win32 端来看，只需更改属性即可。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容类中的实现从某种意义上来说更加复杂，因为不存在控制所有控件的字体的单个全局属性。 相反，每个控件的相应属性均是在属性的 set 访问器中进行更改的。 下面的示例演示属性的代码 `DefaultFontFamily` 。 设置属性将调用专用方法，该方法依次又将为各控件设置 <xref:System.Windows.Controls.Control.FontFamily%2A> 属性。

 从 WPFPage.h：

 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]

 从 WPFPage.cpp：

 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Interop.HwndSource>
- [WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)
