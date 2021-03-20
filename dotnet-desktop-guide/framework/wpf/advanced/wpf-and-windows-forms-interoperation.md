---
title: WPF 和 Windows 窗体互操作
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 34f4ca0a36498af679bc185bb3ffd570f065b87a
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667026"
---
# <a name="wpf-and-windows-forms-interoperation"></a>WPF 和 Windows 窗体互操作
[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 和 Windows 窗体提供用于创建应用程序接口的两个不同的体系结构。 <xref:System.Windows.Forms.Integration?displayProperty=nameWithType>命名空间提供用于启用常见互操作方案的类。 实现互操作功能的两个关键类是 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 和 <xref:System.Windows.Forms.Integration.ElementHost> 。 本主题介绍支持哪些互操作方案以及不支持哪些互操作方案。  
  
> [!NOTE]
> 关于 *混合控件* 方案，需要考虑一些特殊因素。 混合控件将一种技术中的控件嵌套于另一种技术中的控件。 这也称为 *嵌套互操作*。 *多级混合控件* 具有多个级别的混合控件嵌套。 多级嵌套互操作的一个示例是包含控件的 Windows 窗体控件 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，该控件包含另一个 Windows 窗体控件。 不支持多级混合控件。  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>
## <a name="hosting-windows-forms-controls-in-wpf"></a>在 WPF 中承载 Windows 窗体控件  
 当控件承载 Windows 窗体控件时，支持以下互操作方案 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ：  
  
- [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]控件可以使用 XAML 承载一个或多个 Windows 窗体控件。  
  
- 它可以使用代码承载一个或多个 Windows 窗体控件。  
  
- 它可以承载包含其他 Windows 窗体控件 Windows 窗体容器控件。  
  
- 它可以承载一个主/详细信息窗体，其中包含一个主窗体 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 和 Windows 窗体详细信息。  
  
- 它可以承载具有 Windows 窗体母版和详细信息的主/详细信息窗体 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
- 它可以承载一个或多个 ActiveX 控件。  
  
- 它可以承载一个或多个复合控件。  
  
- 它可以使用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 承载混合控件。  
  
- 它可以使用代码承载混合控件。  
  
### <a name="layout-support"></a>布局支持  
 下面的列表介绍当  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素尝试将其承载 Windows 窗体控件集成到布局系统中时的已知限制 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
- 在某些情况下，不能调整 Windows 窗体控件的大小，也不能仅调整到特定尺寸。 例如，Windows 窗体 <xref:System.Windows.Forms.ComboBox> 控件仅支持通过控件的字号定义的单个高度。 在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 假定元素可垂直拉伸的动态布局中，承载的 <xref:System.Windows.Forms.ComboBox> 控件不会按预期拉伸。  
  
- 不能旋转或倾斜 Windows 窗体控件。 例如，将用户界面旋转90度时，承载 Windows 窗体控件将保持其垂直位置。  
  
- 在大多数情况下，Windows 窗体控件不支持按比例缩放。 尽管该控件的整体尺寸将会缩放，但其子控件和组件元素可能不会按预期调整大小。 此限制取决于每个 Windows 窗体控件对缩放的支持程度。  
  
- 在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 用户界面中，可以更改元素的 z 顺序以控制重叠行为。 承载 Windows 窗体控件在单独的 HWND 中绘制，因此始终在元素之上绘制 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
- Windows 窗体控件支持基于字号的自动缩放。 在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 用户界面中，更改字号不会改变整个布局的大小，但是可动态调整单个元素的大小。  
  
### <a name="ambient-properties"></a>环境属性  
 控件的某些环境属性 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 具有 Windows 窗体等效项。 这些环境属性传播到寄宿 Windows 窗体控件，并作为控件上的公共属性公开 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>控件将每个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 环境属性转换为其等效 Windows 窗体。  
  
 有关详细信息，请参阅 [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)。  
  
### <a name="behavior"></a>行为  
 下表介绍互操作行为。  
  
|行为|支持|不支持|  
|--------------|---------------|-------------------|  
|透明度|Windows 窗体控件呈现支持透明度。 父控件的背景 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 可以成为寄宿 Windows 窗体控件的背景。|某些 Windows 窗体控件不支持透明度。 例如，在 <xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.ComboBox> 由承载时，和控件将不透明 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。|  
|Tab 键次序|宿主 Windows 窗体控件的 Tab 键顺序与这些控件承载于基于 Windows 窗体的应用程序中时相同。<br /><br /> [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]使用 tab 键和 SHIFT + TAB 键从控件到 Windows 窗体控件的 tab 键按常规方式工作。<br /><br /> <xref:System.Windows.Forms.Control.TabStop%2A> `false` 当用户通过控件选项卡通过控件时，属性值为的 Windows 窗体控件不会获得焦点。<br /><br /> -每个 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件都有一个 <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> 值，该值确定 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件将接收焦点的时间。<br />-包含在容器内的 Windows 窗体控件 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 遵循属性指定的顺序 <xref:System.Windows.Forms.Control.TabIndex%2A> 。 从最后一个 Tab 键索引使用 Tab 键切换会将焦点置于下一个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件上（若存在）。 如果不存在其他可获得焦点 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 的控件，则按 tab 键顺序返回到第一个 Windows 窗体控件。<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> 内控件的值 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 相对于控件中包含的同级 Windows 窗体控件 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。<br />-    按 Tab 键遵循特定于控件的行为。 例如，在 <xref:System.Windows.Forms.TextBox> 属性值为的控件中按 tab 键可在 <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> `true` 文本框中输入一个选项卡，而不是移动焦点。|不适用。|  
|使用箭头键导航|-控件中的箭头键的导航与 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 普通 Windows 窗体容器控件中相同：向上键和向左键选择上一个控件，向下键和向右键选择下一个控件。<br />-控件中包含的第一个控件的向上键和向左键 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 执行与 SHIFT + TAB 键盘快捷方式相同的操作。 如果有可获得焦点的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件，焦点将移到 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件外。 此行为不同于中的标准 <xref:System.Windows.Forms.ContainerControl> 行为，因为没有环绕最后一个控件。 如果不存在其他可 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 获得焦点的控件，焦点将返回到 tab 键顺序中的最后一个 Windows 窗体控件。<br />-包含在控件中的最后一个控件的向下箭头和向右箭头键 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 执行与 TAB 键相同的操作。 如果有可获得焦点的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件，焦点将移到 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件外。 此行为不同于中的标准行为，因为这样做 <xref:System.Windows.Forms.ContainerControl> 不会换行到第一个控件。 如果不存在其他可 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 获得焦点的控件，焦点将返回到 tab 键顺序中的第一个 Windows 窗体控件。|不适用。|  
|加速键|加速键按常规方式工作，但“不支持”列中注明的情况除外。|跨多种技术的重复加速键与普通重复加速键的工作方式不同。 如果加速器跨技术重复，且至少有一个在 Windows 窗体控件上，另一个在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件上，则 Windows 窗体控件会始终接收该快捷键。 当按重复加速键时，焦点不会在控件之间切换。|  
|快捷键|快捷键按常规方式工作，但“不支持”列中注明的情况除外。|-在预处理阶段处理 Windows 窗体快捷键始终优先于 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 快捷键。 例如，如果你具有一个 <xref:System.Windows.Forms.ToolStrip> 定义了 ctrl + s 快捷键的控件，并且有一个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 绑定到 Ctrl + s 的命令，则 <xref:System.Windows.Forms.ToolStrip> 始终首先调用控件处理程序，而不考虑焦点。<br />-由事件处理 Windows 窗体的快捷键 <xref:System.Windows.Forms.Control.KeyDown> 在中最后处理 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 可以通过重写 Windows 窗体控件的 <xref:System.Windows.Forms.Control.IsInputKey%2A> 方法或处理事件来防止此行为 <xref:System.Windows.Forms.Control.PreviewKeyDown> 。 `true`从方法返回 <xref:System.Windows.Forms.Control.IsInputKey%2A> ，或 <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> `true` 在事件处理程序中将属性的值设置为 <xref:System.Windows.Forms.Control.PreviewKeyDown> 。|  
|AcceptsReturn、AcceptsTab 以及其他特定于控件的行为|更改默认键盘行为的属性将像平常一样工作，假定 Windows 窗体控件重写 <xref:System.Windows.Forms.Control.IsInputKey%2A> 要返回的方法 `true` 。|通过处理事件来更改默认键盘行为 Windows 窗体控件 <xref:System.Windows.Forms.Control.KeyDown> 将在宿主控件中最后处理 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 因为最后处理这些控件，所以它们可能产生意外行为。|  
|Enter 和 Leave 事件|如果焦点不会转到包含 <xref:System.Windows.Forms.Integration.ElementHost> 控件，则在单个控件中焦点更改时，Enter 和 Leave 事件会照常引发 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。|发生以下焦点更改时，不会引发 Enter 和 Leave 事件：<br /><br /> -从内部到控件外 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。<br />-从外部到控件内 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。<br />-控件外 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。<br />-从控件中承载的 Windows 窗体控件 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 到 <xref:System.Windows.Forms.Integration.ElementHost> 在同一中承载的控件 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。|  
|多线程处理|支持所有类型的多线程处理。|Windows 窗体和技术都 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 采用单线程并发模型。 调试期间，从其他线程调用框架对象会引发一个异常，以强制实施此要求。|  
|安全性|所有互操作方案都需要完全信任。|部分信任情况下，不允许任何互操作方案。|  
|可访问性|支持所有辅助功能方案。 辅助技术产品适用于同时包含 Windows 窗体和控件的混合应用程序时，它们可以正常工作 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。|不适用。|  
|剪贴板|所有剪贴板操作按常规方式工作。 这包括 Windows 窗体和控件之间的剪切和粘贴 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。|不适用。|  
|拖放功能|所有拖放操作按常规方式工作。 这包括 Windows 窗体和控件之间 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 的操作。|不适用。|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>
## <a name="hosting-wpf-controls-in-windows-forms"></a>在 Windows 窗体中承载 WPF 控件  
 当 Windows 窗体控件承载控件时，支持以下互操作方案 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ：  
  
- 使用代码承载一个或多个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件。  
  
- 将属性表与一个或多个承载的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件关联。  
  
- 在窗体中承载一个或多个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 页。  
  
- 启动 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 窗口。  
  
- 承载具有 Windows 窗体母版和详细信息的主/详细信息窗体 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
- 使用主/详细信息窗体宿主 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 并 Windows 窗体详细信息。  
  
- 承载自定义 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件。  
  
- 承载混合控件。  
  
### <a name="ambient-properties"></a>环境属性  
 Windows 窗体控件的某些环境属性具有等效项 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 这些环境属性传播到所承载的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件，并作为控件上的公共属性公开 <xref:System.Windows.Forms.Integration.ElementHost> 。 <xref:System.Windows.Forms.Integration.ElementHost>控件将每个 Windows 窗体环境属性转换为其 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 等效的。  
  
 有关详细信息，请参阅 [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)。  
  
### <a name="behavior"></a>行为  
 下表介绍互操作行为。  
  
|行为|支持|不支持|  
|--------------|---------------|-------------------|  
|透明度|[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件呈现支持透明度。 父 Windows 窗体控件的背景可以成为寄宿控件的背景 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。|不适用。|  
|多线程处理|支持所有类型的多线程处理。|Windows 窗体和技术都 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 采用单线程并发模型。 调试期间，从其他线程调用框架对象会引发一个异常，以强制实施此要求。|  
|安全性|所有互操作方案都需要完全信任。|部分信任情况下，不允许任何互操作方案。|  
|可访问性|支持所有辅助功能方案。 辅助技术产品适用于同时包含 Windows 窗体和控件的混合应用程序时，它们可以正常工作 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。|不适用。|  
|剪贴板|所有剪贴板操作按常规方式工作。 这包括 Windows 窗体和控件之间的剪切和粘贴 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。|不适用。|  
|拖放功能|所有拖放操作按常规方式工作。 这包括 Windows 窗体和控件之间 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 的操作。|不适用。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [演练：在 WPF 中承载 Windows 窗体控件](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [演练：在 WPF 中托管 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [演练：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)
