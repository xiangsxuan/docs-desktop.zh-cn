---
title: WindowsFormsHost 元素的布局注意事项
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element layout considerations [WPF]
- dynamic layout [WPF interoperability]
- device-independent pixels
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
ms.openlocfilehash: 5c8a93779141ee061e7bac3dcdfc3fe8b99e2209
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665661"
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>WindowsFormsHost 元素的布局注意事项
本主题介绍元素如何 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 与 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 布局系统交互。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 和 Windows 窗体支持不同但类似的逻辑，用于在窗体或页面上调整和定位元素。 当你在中创建 Windows 窗体控件宿主 (UI) 的混合用户界面时 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ， <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素将集成两个布局方案。  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>WPF 与 Windows 窗体之间的布局差异  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 使用与分辨率无关的布局。 所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 布局维度均使用 *与设备无关的像素* 来指定。 与设备无关的像素是指大小与分辨率无关的一英寸的 1/6，因此无论是呈现为 72 dpi 监视器还是 19200 dpi 打印机，都可以获得类似的结果。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 还基于 *动态布局*。 这意味着，UI 元素会根据其内容、其父布局容器和可用屏幕大小在窗体或页面上排列自身。 动态布局通过在 UI 元素包含更改长度的字符串时自动调整其大小和位置来简化本地化。  
  
 Windows 窗体中的布局取决于设备，并且更有可能是静态的。 通常，Windows 窗体控件在窗体上绝对定位在硬件像素中指定的维度。 不过，Windows 窗体支持一些动态布局功能，如下表所示。  
  
|布局功能|说明|  
|--------------------|-----------------|  
|自动调整|某些 Windows 窗体控件调整其大小以正确显示其内容。 有关详细信息，请参阅 [AutoSize 属性概述](/dotnet/framework/winforms/controls/autosize-property-overview)。|  
|锚定和停靠|Windows 窗体控件支持根据父容器定位和调整大小。 有关详细信息，请参阅 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>。|  
|自动缩放|容器控件根据输出设备的分辨率或默认容器字体的大小（以像素为单位）调整自身及其子控件的大小。 有关详细信息，请参阅 [Windows 窗体中的自动缩放](/dotnet/framework/winforms/automatic-scaling-in-windows-forms)。|  
|布局容器|<xref:System.Windows.Forms.FlowLayoutPanel>和 <xref:System.Windows.Forms.TableLayoutPanel> 控件根据其内容排列子控件并调整其大小。|  
  
## <a name="layout-limitations"></a>布局限制  
 通常情况下，Windows 窗体控件不能缩放并转换为中可能的范围 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 下面的列表介绍当 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素尝试将其承载 Windows 窗体控件集成到布局系统中时的已知限制 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
- 在某些情况下，不能调整 Windows 窗体控件的大小，也不能仅调整到特定尺寸。 例如，Windows 窗体 <xref:System.Windows.Forms.ComboBox> 控件仅支持通过控件的字号定义的单个高度。 在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 元素可垂直拉伸的动态布局中，承载的 <xref:System.Windows.Forms.ComboBox> 控件不会按预期拉伸。  
  
- 不能旋转或倾斜 Windows 窗体控件。 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 如果应用了倾斜或旋转变换，则元素会引发事件。 如果不处理该 <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 事件， <xref:System.InvalidOperationException> 则会引发。  
  
- 在大多数情况下，Windows 窗体控件不支持按比例缩放。 尽管该控件的整体尺寸将会缩放，但其子控件和组件元素可能不会按预期调整大小。 此限制取决于每个 Windows 窗体控件对缩放的支持程度。 此外，不能将 Windows 窗体控制缩小到大小为0像素。  
  
- Windows 窗体控件支持自动缩放，其中窗体将根据字号自动调整自身及其控件的大小。 在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 用户界面中，更改字号不会改变整个布局的大小，但是可动态调整单个元素的大小。  
  
### <a name="z-order"></a>Z 顺序  
 在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 用户界面中，可以更改元素的 z 顺序以控制重叠行为。 承载 Windows 窗体控件在单独的 HWND 中绘制，因此始终在元素之上绘制 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
 宿主 Windows 窗体控件也是在任何元素的顶部绘制的 <xref:System.Windows.Documents.Adorner> 。  
  
## <a name="layout-behavior"></a>布局行为  
 以下各节介绍了在中承载 Windows 窗体控件时的布局行为的特定方面 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>缩放、单位转换和设备独立性  
 每当 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素执行涉及 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 和 Windows 窗体维度的操作时，都涉及两个坐标系统： Windows 窗体的与设备无关的像素 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 和硬件像素。 因此，您必须应用适当的单元和缩放转换才能实现一致的布局。  
  
 坐标系统之间的转换取决于当前的设备分辨率以及应用于该 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素或其上级的任何布局或呈现转换。  
  
 如果输出设备为 96 dpi，且未对元素应用缩放，则 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 一个与设备无关的像素等于一个硬件像素。  
  
 所有其他情况都需要坐标系统缩放。 不调整承载的控件的大小。 相反， <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素会尝试缩放承载的控件及其所有子控件。 由于 Windows 窗体不完全支持缩放，因此 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素会缩放到特定控件支持的程度。  
  
 重写 <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> 方法以提供承载 Windows 窗体控件的自定义缩放行为。  
  
 除缩放外，元素还 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 处理舍入和溢出事例，如下表所述。  
  
|转换问题|说明|  
|----------------------|-----------------|  
|舍入|[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 与设备无关的像素尺寸指定为 `double` ，Windows 窗体硬件像素尺寸指定为 `int` 。 在 `double` 基于的维度转换为 `int` 基于的维度时， <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素使用标准舍入，以便小于0.5 的小数值向下舍入为0。|  
|溢出|当 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素从值转换 `double` 为 `int` 值时，可能会发生溢出。 大于的值 <xref:System.Int32.MaxValue> 将设置为 <xref:System.Int32.MaxValue> 。|  
  
### <a name="layout-related-properties"></a>与布局相关的属性  
 用于控制 Windows 窗体控件和元素中的布局行为的属性 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 将由元素进行相应映射 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。 有关详细信息，请参阅 [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)。  
  
### <a name="layout-changes-in-the-hosted-control"></a>寄宿控件中的布局更改  
 承载 Windows 窗体控件中的布局更改将传播到 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 以触发布局更新。 <xref:System.Windows.UIElement.InvalidateMeasure%2A>上的方法 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 可确保寄宿控件中的布局更改会导致 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 布局引擎运行。  
  
### <a name="continuously-sized-windows-forms-controls"></a>持续调整 Windows 窗体控件大小  
 支持连续缩放的 Windows 窗体控件完全与 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 布局系统交互。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素使用 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 和 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 方法照常使用和方法来调整承载 Windows 窗体控件的大小和顺序。  
  
### <a name="sizing-algorithm"></a>大小调整算法  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素使用以下过程来调整托管控件的大小：  
  
1. <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素重写 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 和 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 方法。  
  
2. 若要确定承载的控件的大小，该 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 方法将 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 使用从传递给该方法的约束转换的约束来调用托管控件的方法 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 。  
  
3. <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>方法尝试将承载的控件设置为给定的大小约束。  
  
4. 如果承载的控件的 <xref:System.Windows.Forms.Control.Size%2A> 属性与指定的约束相匹配，则承载的控件将调整为约束的大小。  
  
 如果该 <xref:System.Windows.Forms.Control.Size%2A> 属性与指定的约束不匹配，则承载的控件不支持连续调整大小。 例如， <xref:System.Windows.Forms.MonthCalendar> 控件仅允许离散大小。 此控件的允许大小包含整数 (表示高度和宽度) 的月份数。 在这种情况下， <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的行为如下所示：  
  
- 如果 <xref:System.Windows.Forms.Control.Size%2A> 属性返回的大小比指定的约束大，则 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素会剪辑承载的控件。 高度和宽度是单独处理的，因此可能会在任一方向上剪裁托管控件。  
  
- 如果 <xref:System.Windows.Forms.Control.Size%2A> 属性返回的大小小于指定的约束，则 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 接受此大小值，并将值返回到 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 布局系统。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [演练：在 WPF 中排列 Windows 窗体控件](walkthrough-arranging-windows-forms-controls-in-wpf.md)
- [有关在 WPF 中排列 Windows 窗体控件的示例](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WpfLayoutHostingWfWithXaml)
- [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)
- [迁移和互操作性](migration-and-interoperability.md)
