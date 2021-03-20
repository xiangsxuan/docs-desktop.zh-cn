---
title: 混合应用程序疑难解答
ms.date: 03/30/2017
helpviewer_keywords:
- overlapping controls [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid applications [WPF interoperability]
- message loops [WPF]
ms.assetid: f440c23f-fa5d-4d5a-852f-ba61150e6405
ms.openlocfilehash: 028d1f83a73d59ebb1a3d3779244b0eac773a860
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664634"
---
# <a name="troubleshooting-hybrid-applications"></a>混合应用程序疑难解答

<a name="introduction"></a> 本主题列出了创作混合应用程序时可能出现的一些常见问题，它们使用 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 和 Windows 窗体技术。  

<a name="overlapping_controls"></a>

## <a name="overlapping-controls"></a>重叠控件  

 控件可能不按预期的方式重叠。 Windows 窗体对每个控件使用单独的 HWND。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 为一个页面上的所有内容使用一个 HWND。 这一实现差异会导致意外的重叠行为。  
  
 中承载的 Windows 窗体控件 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 始终显示在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容之上。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件中承载的内容 <xref:System.Windows.Forms.Integration.ElementHost> 将按控件的 z 顺序显示 <xref:System.Windows.Forms.Integration.ElementHost> 。 可以重叠 <xref:System.Windows.Forms.Integration.ElementHost> 控件，但所承载的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 内容不会合并或交互。  
  
<a name="child_property"></a>

## <a name="child-property"></a>子属性  

 <xref:System.Windows.Forms.Integration.WindowsFormsHost>和 <xref:System.Windows.Forms.Integration.ElementHost> 类只能承载一个子控件或元素。 若要承载多个控件或元素，则必须使用容器作为子内容。 例如，您可以将 Windows 窗体按钮和复选框控件添加到 <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> 控件，然后将面板分配给 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件的 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> 属性。 但是，不能将按钮控件和复选框控件分别添加到同一个 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件。  
  
<a name="scaling"></a>

## <a name="scaling"></a>扩展  

 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 和 Windows 窗体具有不同的缩放模式。 某些 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 缩放转换对于 Windows 窗体控件是有意义的，但有些则不是。 例如，将 Windows 窗体控件缩放到0将起作用，但如果尝试将同一控件缩放回非零值，则该控件的大小将保持为0。 有关详细信息，请参阅 [WindowsFormsHost 元素的布局注意事项](layout-considerations-for-the-windowsformshost-element.md)。  
  
<a name="adapter"></a>

## <a name="adapter"></a>适配器  

 当使用和类时，可能会产生混淆 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.ElementHost> ，因为它们包含隐藏容器。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>和 <xref:System.Windows.Forms.Integration.ElementHost> 类都有一个称为 *适配器* 的隐藏容器，用来承载内容。 对于 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素，适配器派生自 <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType> 类。 对于 <xref:System.Windows.Forms.Integration.ElementHost> 控件，适配器派生自 <xref:System.Windows.Controls.DockPanel> 元素。 如果你发现其他互操作主题中提到了适配器，那么所讨论的就是此容器。  
  
<a name="nesting"></a>

## <a name="nesting"></a>嵌套  

 <xref:System.Windows.Forms.Integration.WindowsFormsHost>不支持在控件内嵌套元素 <xref:System.Windows.Forms.Integration.ElementHost> 。 <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Forms.Integration.WindowsFormsHost> 也不支持在元素内嵌套控件。  
  
<a name="focus"></a>

## <a name="focus"></a>焦点  

 焦点在和 Windows 窗体中的工作方式不同 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，这意味着在混合应用程序中可能会出现焦点问题。 例如，如果焦点位于某个 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素内，而您最小化和还原该页或显示模式对话框，则该元素内部的焦点 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 可能会丢失。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素仍具有焦点，但它内部的控件可能不具有焦点。  
  
 焦点还会影响数据验证。 验证在元素中起作用 <xref:System.Windows.Forms.Integration.WindowsFormsHost> ，但当您从 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素中或在两个不同的元素之间切换时，它不起作用 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。  
  
<a name="property_mapping"></a>

## <a name="property-mapping"></a>属性映射  

 某些属性映射需要广泛的解读来在和 Windows 窗体技术之间桥接不同的实现 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 属性映射可使代码对字体、颜色和其他属性的更改做出反应。 通常，属性映射的工作方式是侦听 *Property* Changed 事件或 On *Property* 调用，然后在子控件或其适配器上设置适当的属性。 有关详细信息，请参阅 [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)。  
  
<a name="layoutrelated_properties_on_hosted_content"></a>

## <a name="layout-related-properties-on-hosted-content"></a>所承载内容上的布局相关属性  

 当 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType> 分配了或 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType> 属性时，将自动设置承载内容上的多个与布局相关的属性。 更改这些内容属性可能会导致意外的布局行为。  
  
 承载的内容将停靠，以填充 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 和 <xref:System.Windows.Forms.Integration.ElementHost> 父级。 为了启用此填充行为，在设置子属性时，将设置多个属性。 下表列出了和类设置了哪些内容属性 <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。  
  
|宿主类|内容属性|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 请勿在所承载的内容上直接设置这些属性。 有关详细信息，请参阅 [WindowsFormsHost 元素的布局注意事项](layout-considerations-for-the-windowsformshost-element.md)。  
  
<a name="navigation_applications"></a>

## <a name="navigation-applications"></a>导航应用程序  

 导航应用程序不能保持用户状态。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>当元素用于导航应用程序时，它将重新创建其控件。 当用户离开托管元素的页 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 并返回到该控件时，将会重新创建子控件。 用户已经键入的所有内容都将丢失。  
  
<a name="message_loop_interoperation"></a>

## <a name="message-loop-interoperation"></a>消息循环互操作  

 处理 Windows 窗体消息循环时，消息可能无法按预期方式处理。 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>方法由 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 构造函数调用。 此方法将向 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 消息循环中添加消息筛选器。 如果是消息的目标，则此筛选器调用 <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> 方法 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> ，并转换/调度消息。  
  
 如果 <xref:System.Windows.Window> 使用在 Windows 窗体消息循环中显示 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> ，则除非调用方法，否则不能键入任何内容 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> 。 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>方法采用 <xref:System.Windows.Window> 并添加 <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType> ，后者将与键相关的消息重排到 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 消息循环中。 有关详细信息，请参阅 [Windows 窗体和 WPF 互操作性输入体系结构](windows-forms-and-wpf-interoperability-input-architecture.md)。  
  
<a name="opacity_and_layering"></a>

## <a name="opacity-and-layering"></a>不透明度和分层  

 <xref:System.Windows.Interop.HwndHost>类不支持分层。 这意味着，在 <xref:System.Windows.UIElement.Opacity%2A> 元素上设置属性 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 不起作用，并且其他设置为的窗口不会进行混合 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window.AllowsTransparency%2A> `true` 。  
  
<a name="dispose"></a>

## <a name="dispose"></a>释放  

 未正确释放类可能会泄漏资源。 在混合应用程序中，请确保 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 和 <xref:System.Windows.Forms.Integration.ElementHost> 类已释放，否则可能会泄漏资源。 Windows 窗体 <xref:System.Windows.Forms.Integration.ElementHost> 在其非模式 <xref:System.Windows.Forms.Form> 父项关闭时释放控件。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Forms.Integration.WindowsFormsHost>在应用程序关闭时释放元素。 可以 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Window> 在 Windows 窗体消息循环的中显示元素。 在这种情况下，代码可能不会收到应用程序正在关闭的通知。  
  
<a name="enabling_visual_styles"></a>

## <a name="enabling-visual-styles"></a>启用视觉样式  

 可能未启用 Windows 窗体控件上的 Microsoft Windows XP 视觉样式。 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>在 Windows 窗体应用程序的模板中调用方法。 尽管默认情况下不会调用此方法，但如果你使用 Visual Studio 创建项目，则将获得适用于控件的 Microsoft Windows XP 视觉样式（如果版本 6.0 Comctl32.dll 可用）。 在 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 线程上创建句柄之前，必须先调用方法。 有关详细信息，请参阅[如何：在混合应用程序中启用视觉样式](how-to-enable-visual-styles-in-a-hybrid-application.md)。  
  
<a name="licensed_controls"></a>

## <a name="licensed-controls"></a>授权控件  

 向用户显示消息框中的许可信息的许可 Windows 窗体控件可能会导致混合应用程序出现意外行为。 某些授权控件会显示一个对话框来响应创建句柄的操作。 例如，授权控件可能会通知用户需要许可证，或者用户还可以试用该控件三次。  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素派生自 <xref:System.Windows.Interop.HwndHost> 类，并在方法中创建子控件的句柄 <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> 。 <xref:System.Windows.Interop.HwndHost>类不允许在方法中处理消息 <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> ，但显示一个对话框会导致发送消息。 若要启用此授权方案，请 <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType> 在将控件指定为元素的子级之前，对其调用方法 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。  
  
<a name="wpf_designer"></a>

## <a name="wpf-designer"></a>WPF 设计器  

 可以通过使用 Visual Studio 的 WPF 设计器来设计 WPF 内容。 以下部分列出了用 WPF 设计器创作混合应用程序时可能出现的一些常见问题。  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>在设计时忽略 BackColorTransparent  

 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>属性在设计时可能无法按预期方式工作。  
  
 如果 WPF 控件不在可见父控件上，则 WPF 运行时将忽略 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 该值。 可能被忽略的原因 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 是， <xref:System.Windows.Forms.Integration.ElementHost> 对象是在单独的中创建的 <xref:System.AppDomain> 。 但是，当你运行应用程序时， <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 会按预期方式工作。  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>删除 obj 文件夹时出现设计时错误列表  

 如果删除 obj 文件夹，会出现设计时错误列表。  
  
 当你使用进行设计时 <xref:System.Windows.Forms.Integration.ElementHost> ，Windows 窗体设计器将在项目的 obj 文件夹内的 "调试" 或 "发布" 文件夹中使用生成的文件。 如果删除这些文件，将出现设计时错误列表。 若要解决此问题，请重新生成项目。 有关详细信息，请参阅 [Windows 窗体设计器中的设计时错误](/dotnet/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer)。  
  
<a name="elementhost_and_ime"></a>

## <a name="elementhost-and-ime"></a>ElementHost 和 IME  

 中承载的 WPF 控件 <xref:System.Windows.Forms.Integration.ElementHost> 当前不支持 <xref:System.Windows.Forms.Control.ImeMode%2A> 属性。 所 <xref:System.Windows.Forms.Control.ImeMode%2A> 承载的控件将忽略对的更改。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [WPF 设计器中的互操作性](/previous-versions/visualstudio/visual-studio-2010/bb628658(v=vs.100))
- [Windows 窗体和 WPF 互操作性输入体系结构](windows-forms-and-wpf-interoperability-input-architecture.md)
- [如何：在混合应用程序中启用视觉对象样式](how-to-enable-visual-styles-in-a-hybrid-application.md)
- [WindowsFormsHost 元素的布局注意事项](layout-considerations-for-the-windowsformshost-element.md)
- [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)
- [Windows 窗体设计器中的设计时错误](/dotnet/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer)
- [迁移和互操作性](migration-and-interoperability.md)
