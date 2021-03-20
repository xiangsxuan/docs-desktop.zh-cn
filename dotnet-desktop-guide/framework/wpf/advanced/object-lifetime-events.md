---
title: 对象生存期事件
ms.date: 03/30/2017
helpviewer_keywords:
- events [WPF], ContentRendered
- events [WPF], Deactivated
- events [WPF], Unloaded
- Activated events [WPF]
- events [WPF], Loaded
- Application objects [WPF], lifetime events
- events [WPF], Activated
- ContentRendered events [WPF]
- Deactivated events [WPF]
- events [WPF], Initialized
- events [WPF], Closing
- Unloaded events [WPF]
- exit events [WPF]
- objects' lifetime events [WPF]
- Loaded events [WPF]
- Closing events [WPF]
- events [WPF], Closed
- Initialized events [WPF]
- Closed events [WPF]
- startup events [WPF]
- lifetime events of objects [WPF]
ms.assetid: face6fc7-465b-4502-bfe5-e88d2e729a78
ms.openlocfilehash: 5df6e6bdf6704229fbfbc0108c552db10f8c198b
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666701"
---
# <a name="object-lifetime-events"></a>对象生存期事件
本主题介绍表示对象生存期（创建、使用和销毁）中的阶段的特定 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 事件。  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>必备条件  
 本主题假设你作为 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 类的现有依赖属性的使用者已经对依赖属性有所了解，并且已经阅读了[依赖属性概述](dependency-properties-overview.md)主题。 若要理解本主题中的示例，还应当了解 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)]（请参阅 [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)）并知道如何编写 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序。  
  
<a name="intro"></a>
## <a name="object-lifetime-events"></a>对象生存期事件  
 Microsoft .NET Framework 托管代码中的所有对象都会经历一组类似的生命周期、创建、使用和销毁。 许多对象还包括生命终止阶段，该阶段属于销毁阶段的一部分。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 对象（更明确的说，[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 标识为元素的视觉对象）还具有对象生命的一系列常见阶段。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 编程和应用程序模型将这些阶段作为一系列事件公开。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 中有四种与生存期事件有关的主要类型对象 - 即常规元素、窗口元素、导航宿主和应用程序对象。 窗口和导航宿主也都属于视觉对象（元素）这个较大的组。 本主题首先介绍所有元素的通用生存期事件，然后介绍应用于应用程序定义、窗口或导航宿主的更具针对性的生存期事件。  
  
<a name="common_events"></a>
## <a name="common-lifetime-events-for-elements"></a>元素通用生存期事件  
 任何从或) 派生的对象 (WPF 框架级别元素 <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> 都具有三个常见生存期事件： <xref:System.Windows.FrameworkElement.Initialized> 、 <xref:System.Windows.FrameworkElement.Loaded> 和 <xref:System.Windows.FrameworkElement.Unloaded> 。  
  
### <a name="initialized"></a>Initialized  
 <xref:System.Windows.FrameworkElement.Initialized> 首先引发，并大致对应于通过调用其构造函数初始化的对象。 由于事件为响应初始化而发生，因此可以确保对象的所有属性均已设置。  (异常是表达式用法，如动态资源或绑定;这将是未计算的表达式。 ) 由于设置了所有属性，因此在 <xref:System.Windows.FrameworkElement.Initialized> 标记中定义的嵌套元素所引发的序列显示为先按元素树中的最深层元素，然后指向根的父元素。 采用此顺序是鉴于父子关系和包容均为属性，因此在填充属性的子元素完全初始化前，父元素无法报告初始化。  
  
 编写处理程序以响应 <xref:System.Windows.FrameworkElement.Initialized> 事件时，必须考虑到元素树中的所有其他元素都 (逻辑树或可视化树) 在创建了处理程序的位置，尤其是父元素。 成员变量可能为 null，或者基础绑定还未填充数据源（即使在表达式级别）。  
  
### <a name="loaded"></a>已加载  
 <xref:System.Windows.FrameworkElement.Loaded> 下一次引发。 <xref:System.Windows.FrameworkElement.Loaded>事件是在最终呈现之前引发的，但在布局系统已计算所有必要的呈现值之后。 <xref:System.Windows.FrameworkElement.Loaded> 要求元素包含在中的逻辑树完成，并连接到提供 HWND 和呈现图面的表示源。  (绑定到本地源的标准数据绑定，如) 将在之前发生的其他属性或直接定义的数据源 <xref:System.Windows.FrameworkElement.Loaded> 。 可能已发生异步数据绑定（外部或动态源），但是根据其异步特性的定义不能保证已发生异步数据绑定。  
  
 引发事件的机制与 <xref:System.Windows.FrameworkElement.Loaded> 不同 <xref:System.Windows.FrameworkElement.Initialized> 。 <xref:System.Windows.FrameworkElement.Initialized>事件由元素引发，而不直接与已完成的元素树进行协调。 与此相反， <xref:System.Windows.FrameworkElement.Loaded> 事件是在整个元素树中以协调的方式引发的， (具体而言，逻辑树) 。 当树中的所有元素都处于被视为已加载的状态时，将 <xref:System.Windows.FrameworkElement.Loaded> 首先在根元素上引发事件。 <xref:System.Windows.FrameworkElement.Loaded>然后，每个子元素连续引发一次事件。  
  
> [!NOTE]
> 这种行为看起来可能类似于路由事件的隧道。 但是，未将任何信息在事件之间传送。 每个元素始终有机会处理其 <xref:System.Windows.FrameworkElement.Loaded> 事件，并将事件数据标记为已处理不会影响该元素。  
  
### <a name="unloaded"></a>已卸载  
 <xref:System.Windows.FrameworkElement.Unloaded> 最后引发，并由表示源或要删除的可视父级启动。 当 <xref:System.Windows.FrameworkElement.Unloaded> 引发并处理时，作为事件源父级 (的元素（由 <xref:System.Windows.FrameworkElement.Parent%2A> 属性) 确定或在逻辑树或可视化树中向上向上的任何给定元素）可能已取消设置，这意味着，数据绑定、资源引用和样式可能未设置为其正常或上一个已知的运行时值。  
  
<a name="application_model_elements"></a>
## <a name="lifetime-events-application-model-elements"></a>生存期事件应用程序模型元素  
 在元素的常见生存期事件上生成是以下应用程序模型元素： <xref:System.Windows.Application> 、 <xref:System.Windows.Window> 、 <xref:System.Windows.Controls.Page> 、 <xref:System.Windows.Navigation.NavigationWindow> 和 <xref:System.Windows.Controls.Frame> 。 这些与特定用途相关的额外事件扩充了常见的生存期事件。 将在以下位置详细介绍这些内容：  
  
- <xref:System.Windows.Application>： [应用程序管理概述](../app-development/application-management-overview.md)。  
  
- <xref:System.Windows.Window>： [WPF 窗口概述](../app-development/wpf-windows-overview.md)。  
  
- <xref:System.Windows.Controls.Page>、 <xref:System.Windows.Navigation.NavigationWindow> 和 <xref:System.Windows.Controls.Frame> ： [导航概述](../app-development/navigation-overview.md)。  
  
## <a name="see-also"></a>请参阅

- [依赖项属性值优先级](dependency-property-value-precedence.md)
- [路由事件概述](routed-events-overview.md)
