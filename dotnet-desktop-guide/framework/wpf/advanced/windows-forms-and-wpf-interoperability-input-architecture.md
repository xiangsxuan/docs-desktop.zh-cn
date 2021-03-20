---
title: Windows 窗体和 WPF 互操作输入体系结构
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- input architecture [WPF interoperability]
- messages [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- modeless forms [WPF]
- ElementHost keyboard and messages [WPF]
- keyboard interoperation [WPF]
- WindowsFormsHost keyboard and messages [WPF]
- modeless dialog boxes [WPF]
ms.assetid: 0eb6f137-f088-4c5e-9e37-f96afd28f235
ms.openlocfilehash: 115eb98fb61d0bbb0abc71701267ab8afbecb62e
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667078"
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Windows 窗体和 WPF 互操作性输入体系结构
和 Windows 窗体之间的互操作 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 要求两种技术都具有适当的键盘输入处理。 本主题介绍这些技术如何实现键盘和消息处理，以便在混合应用程序中实现平滑互操作。  
  
 本主题包含以下小节：  
  
- 无模式窗体和对话框  
  
- System.windows.forms.integration.windowsformshost> 键盘和消息处理  
  
- ElementHost 键盘和消息处理  
  
## <a name="modeless-forms-and-dialog-boxes"></a>无模式窗体和对话框  
 对 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> 元素调用方法 <xref:System.Windows.Forms.Integration.WindowsFormsHost> ，以从基于的应用程序中打开无模式窗体或对话框 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
 对 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> 控件调用方法 <xref:System.Windows.Forms.Integration.ElementHost> ，以 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 在基于 Windows 窗体的应用程序中打开无模式页面。  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>System.windows.forms.integration.windowsformshost> 键盘和消息处理  
 由 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 基于的应用程序托管时，Windows 窗体键盘和消息处理包含以下各项：  
  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>类从消息循环获取消息 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，该消息循环由 <xref:System.Windows.Interop.ComponentDispatcher> 类实现。  
  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>类创建一个代理项 Windows 窗体消息循环，以确保发生普通的 Windows 窗体键盘处理。  
  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>类实现 <xref:System.Windows.Interop.IKeyboardInputSink> 接口，以便与焦点管理协调 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>控件会自行注册并启动其消息循环。  
  
 以下部分更详细地介绍了此过程的各个部分。  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>从 WPF 消息循环获取消息  
 <xref:System.Windows.Interop.ComponentDispatcher>类实现的消息循环管理器 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 <xref:System.Windows.Interop.ComponentDispatcher>类提供挂钩，使外部客户端能够在处理消息前对消息进行筛选 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
 互操作实现处理 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 事件，该事件使 Windows 窗体控件可以在控件之前处理消息 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
### <a name="surrogate-windows-forms-message-loop"></a>代理项 Windows 窗体消息循环  
 默认情况下， <xref:System.Windows.Forms.Application?displayProperty=nameWithType> 类包含用于 Windows 窗体应用程序的主消息循环。 在互操作期间，Windows 窗体消息循环不处理消息。 因此，必须重现此逻辑。 事件的处理程序 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 执行以下步骤：  
  
1. 使用接口筛选消息 <xref:System.Windows.Forms.IMessageFilter> 。  
  
2. 调用 <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> 方法。  
  
3. 如果需要，请转换并调度消息。  
  
4. 如果没有其他控件处理消息，则将消息传递给宿主控件。  
  
### <a name="ikeyboardinputsink-implementation"></a>System.windows.interop.ikeyboardinputsink> 实现  
 代理项消息循环处理键盘管理。 因此， <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> 方法是唯一 <xref:System.Windows.Interop.IKeyboardInputSink> 需要类中的实现的成员 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。  
  
 默认情况下， <xref:System.Windows.Interop.HwndHost> 类 `false` 为其 <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> 实现返回。 这会阻止从 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件到 Windows 窗体控件的 tab 键。  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>方法的实现 <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> 执行以下步骤：  
  
1. 查找控件包含的第一个或最后一个 Windows 窗体控件， <xref:System.Windows.Forms.Integration.WindowsFormsHost> 该控件可以接收焦点。 控件选择取决于遍历信息。  
  
2. 将焦点设置到控件并返回 `true` 。  
  
3. 如果没有控件可以接收焦点，则返回 `false` 。  
  
### <a name="windowsformshost-registration"></a>System.windows.forms.integration.windowsformshost> 注册  
 当创建控件的窗口句柄时 <xref:System.Windows.Forms.Integration.WindowsFormsHost> ，控件将 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 调用一个内部静态方法，用于注册消息循环的状态。  
  
 在注册期间， <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件将检查消息循环。 如果消息循环尚未启动，则 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 创建事件处理程序。 附加事件处理程序时，消息循环被视为正在运行 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 。  
  
 销毁窗口句柄时，控件会将 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 其自身从注册中移除。  
  
## <a name="elementhost-keyboard-and-message-processing"></a>ElementHost 键盘和消息处理  
 当由 Windows 窗体应用程序承载时， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 键盘和消息处理由以下内容组成：  
  
- <xref:System.Windows.Interop.HwndSource>、 <xref:System.Windows.Interop.IKeyboardInputSink> 和 <xref:System.Windows.Interop.IKeyboardInputSite> 接口实现。  
  
- Tab 键和箭头键。  
  
- 命令键和对话框键。  
  
- Windows 窗体加速器处理。  
  
 以下部分更详细地介绍了这些部分。  
  
### <a name="interface-implementations"></a>接口实现  
 在 Windows 窗体中，键盘消息将路由到具有焦点的控件的窗口句柄。 在 <xref:System.Windows.Forms.Integration.ElementHost> 控件中，这些消息将路由到承载的元素。 为实现此目的， <xref:System.Windows.Forms.Integration.ElementHost> 控件提供了一个 <xref:System.Windows.Interop.HwndSource> 实例。 如果 <xref:System.Windows.Forms.Integration.ElementHost> 控件有焦点，则该 <xref:System.Windows.Interop.HwndSource> 实例将路由大多数键盘输入，以便可以由类进行处理 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> 。  
  
 <xref:System.Windows.Interop.HwndSource>类实现 <xref:System.Windows.Interop.IKeyboardInputSink> 和 <xref:System.Windows.Interop.IKeyboardInputSite> 接口。  
  
 键盘互操作依赖实现 <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> 方法来处理将焦点移出托管元素的 TAB 键和箭头键输入。  
  
### <a name="tabbing-and-arrow-keys"></a>Tab 键和箭头键  
 Windows 窗体选择逻辑映射到 <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> 和 <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> 方法以实现 TAB 键和箭头键导航。 重写 <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> 方法完成此映射。  
  
### <a name="command-keys-and-dialog-box-keys"></a>命令键和对话框键  
 为了让 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 第一次机会处理命令键和对话框键，Windows 窗体命令预处理连接到 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> 方法。 重写 <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> 方法会连接这两个技术。  
  
 通过 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> 方法，所承载的元素可以处理任何关键消息，如 WM_KEYDOWN、WM_KEYUP、WM_SYSKEYDOWN 或 WM_SYSKEYUP，包括命令键，如 TAB、ENTER、ESC 和箭头键。 如果未处理某个关键消息，则会将该消息发送 Windows 窗体祖先层次结构进行处理。  
  
### <a name="accelerator-processing"></a>加速器处理  
 若要正确处理快捷键，Windows 窗体加速器处理必须连接到 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> 类。 此外，所有 WM_CHAR 消息都必须正确路由到托管元素。  
  
 由于方法的默认 <xref:System.Windows.Interop.HwndSource> 实现 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> 返回，因此 `false` 使用以下逻辑处理 WM_CHAR 消息：  
  
- <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType>重写方法以确保将所有 WM_CHAR 消息转发到承载的元素。  
  
- 如果按下了 ALT 键，则会 WM_SYSCHAR 消息。 Windows 窗体不会通过方法对此消息进行预处理 <xref:System.Windows.Forms.Control.IsInputChar%2A> 。 因此，将 <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> 重写方法以查询 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> 注册的快捷键。 如果找到了已注册的加速器，则对 <xref:System.Windows.Input.AccessKeyManager> 其进行处理。  
  
- 如果未按下 ALT 键，则 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> 类将处理未处理的输入。 如果输入是加速器，则会 <xref:System.Windows.Input.AccessKeyManager> 处理它。 <xref:System.Windows.Input.InputManager.PostProcessInput>对于未处理 WM_CHAR 消息，将处理事件。  
  
 当用户按下 ALT 键时，将在整个窗体上显示快捷键视觉提示。 为了支持此行为， <xref:System.Windows.Forms.Integration.ElementHost> 活动窗体上的所有控件都将收到 WM_SYSKEYDOWN 消息，不管哪个控件具有焦点。  
  
 消息只发送到 <xref:System.Windows.Forms.Integration.ElementHost> 活动窗体中的控件。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [演练：在 WPF 中托管 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [演练：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)
