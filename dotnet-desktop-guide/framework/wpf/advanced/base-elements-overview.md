---
title: 基元素概述
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: fe0427b144efacb2f6b8e56adbe00decedc1c0cf
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666415"
---
# <a name="base-elements-overview"></a>基元素概述
中的类的高百分比 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 派生自四个类，这些类通常在 SDK 文档中称为基元素类。 这些类包括 <xref:System.Windows.UIElement> 、 <xref:System.Windows.FrameworkElement> 、 <xref:System.Windows.ContentElement> 和 <xref:System.Windows.FrameworkContentElement> 。 <xref:System.Windows.DependencyObject>类也是相关的，因为它是和的公共基类。 <xref:System.Windows.UIElement><xref:System.Windows.ContentElement>  

<a name="base_apis"></a>
## <a name="base-element-apis-in-wpf-classes"></a>WPF 类中的基元素 API  
 <xref:System.Windows.UIElement>和 <xref:System.Windows.ContentElement> 都是从派生的，它们的 <xref:System.Windows.DependencyObject> 路径不同。 此级别的拆分涉及如何 <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement> 在用户界面中使用或，以及它们在应用程序中的用途。 <xref:System.Windows.UIElement> 此外 <xref:System.Windows.Media.Visual> ，它是类层次结构中的，它是一个公开底层图形支持的类 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。 <xref:System.Windows.Media.Visual> 通过定义独立的矩形屏幕区域来提供呈现框架。 在实践中， <xref:System.Windows.UIElement> 是针对将支持更大对象模型的元素，旨在呈现为可被描述为矩形屏幕区域的区域，并且内容模型有意更开放，以允许元素的不同组合。 <xref:System.Windows.ContentElement> 不是从派生的 <xref:System.Windows.Media.Visual> ; 其模型是，将 <xref:System.Windows.ContentElement> 由其他一些对象使用，如读取器或查看器，然后将对元素进行解释并生成完整 <xref:System.Windows.Media.Visual> 的以供 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 使用。 某些 <xref:System.Windows.UIElement> 类旨在作为内容宿主：它们提供一个或多个类的宿主和呈现 <xref:System.Windows.ContentElement> (<xref:System.Windows.Controls.DocumentViewer> 是此类) 的一个示例。 <xref:System.Windows.ContentElement> 用作具有更小对象模型的元素的基类，并且更多地处理可能在中承载的文本、信息或文档内容 <xref:System.Windows.UIElement> 。  
  
### <a name="framework-level-and-core-level"></a>框架级别和核心级别  
 <xref:System.Windows.UIElement> 用作的基类 <xref:System.Windows.FrameworkElement> ，并充当的 <xref:System.Windows.ContentElement> 基类 <xref:System.Windows.FrameworkContentElement> 。 此级别的下一级别的原因是支持独立于 WPF 框架级别的 WPF 核心级别，此外，此分部还存在于 Api 在 PresentationCore 和 PresentationFramework 程序集之间划分的方式。 WPF 框架级别表示一种更完整的解决方案，以满足基本应用程序需求，其中包括实现演示文稿的布局管理器。 WPF 核心级别可提供一种方法，使你能够充分利用 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]，而无需使用其他程序集的开销。 这三种级别之间的区别对于大多数典型的应用程序开发方案而言非常罕见，一般情况下，您应将这些 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] api 视为一个整体，而不考虑 wpf 框架级别与 wpf 核心级别之间的差异。 如果应用程序设计选择替换大量 WPF 框架级别功能，建议了解级别差异，例如，整体解决方案是否已有其自己的 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 组合和布局的实现。  
  
<a name="subclassing_elements"></a>
## <a name="choosing-which-element-to-derive-from"></a>选择要从其中派生的元素  
 若要创建扩展 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 的自定义类，最实用的方法是派生自 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 类之一，你可在其中通过现有类层次结构获得尽可能多的所需功能。 本节列出了以下三个最重要的元素类附带的功能，以帮助决定要从其中继承的类。  
  
 如果要实现控件（这是从类派生的一个更常见的原因） [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，则可能需要从属于实际控件、控件族基类的类派生，或至少从 <xref:System.Windows.Controls.Control> 基类派生。 有关指导和实际示例，请参阅[控件创作概述](../controls/control-authoring-overview.md)。  
  
 如果没有创建控件且需要派生自位于层次结构中较高层次的类，以下各节可用于指导在每个基元素类中定义哪些特征。  
  
 如果创建派生自的类 <xref:System.Windows.DependencyObject> ，则将继承以下功能：  
  
- <xref:System.Windows.DependencyObject.GetValue%2A> 和 <xref:System.Windows.DependencyObject.SetValue%2A> 支持以及常规属性系统支持。  
  
- 能够使用依赖属性和实现为依赖属性的附加属性。  
  
 如果创建派生自的类 <xref:System.Windows.UIElement> ，除了提供的功能外，还将继承以下功能 <xref:System.Windows.DependencyObject> ：  
  
- 对已动画处理的属性值的基本支持。 有关详细信息，请参阅 [动画概述](../graphics-multimedia/animation-overview.md)。  
  
- 基本输入事件支持以及命令支持。 有关详细信息，请参阅[输入概述](input-overview.md)和[命令概述](commanding-overview.md)。  
  
- 可进行替代以便介绍布局系统的虚拟方法。  
  
 如果创建派生自的类 <xref:System.Windows.FrameworkElement> ，除了提供的功能外，还将继承以下功能 <xref:System.Windows.UIElement> ：  
  
- 样式和情节提要支持。 有关详细信息，请参阅 <xref:System.Windows.Style> 和 [情节提要概述](../graphics-multimedia/storyboards-overview.md)。  
  
- 数据绑定支持。 有关详细信息，请参阅 [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)。  
  
- 动态资源引用支持。 有关详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)。  
  
- 属性值继承支持，以及元数据中的其他标记，这些标记有助于报告关于框架服务属性的情况，例如数据绑定、样式或布局的框架实现。 有关详细信息，请参阅[框架属性元数据](framework-property-metadata.md)。  
  
- 逻辑树概念。 有关详细信息，请参见 [WPF 中的树](trees-in-wpf.md)。  
  
- 支持布局系统的实际 WPF 框架级别的实现，包括 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 可检测影响布局的属性更改的重写。  
  
 如果创建派生自的类 <xref:System.Windows.ContentElement> ，除了提供的功能外，还将继承以下功能 <xref:System.Windows.DependencyObject> ：  
  
- 支持动画。 有关详细信息，请参阅 [动画概述](../graphics-multimedia/animation-overview.md)。  
  
- 基本输入事件支持以及命令支持。 有关详细信息，请参阅[输入概述](input-overview.md)和[命令概述](commanding-overview.md)。  
  
 如果创建派生自的类 <xref:System.Windows.FrameworkContentElement> ，除了提供的功能外，还会获得以下功能 <xref:System.Windows.ContentElement> ：  
  
- 样式和情节提要支持。 有关详细信息，请参阅 <xref:System.Windows.Style> 和 [动画概述](../graphics-multimedia/animation-overview.md)。  
  
- 数据绑定支持。 有关详细信息，请参阅 [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)。  
  
- 动态资源引用支持。 有关详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)。  
  
- 属性值继承支持，以及元数据中的其他标记，这些标记有助于报告关于框架服务属性的情况，例如数据绑定、样式或布局的框架实现。 有关详细信息，请参阅[框架属性元数据](framework-property-metadata.md)。  
  
- 您不会继承对布局系统修改的访问 (如 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>) 。 布局系统实现仅在上可用 <xref:System.Windows.FrameworkElement> 。 但是，你可以继承一个 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 替代，该替代可检测影响布局的属性的更改，并将其报告给任何内容宿主。  
  
 针对各种类记录内容模型。 如果想要查找相应的类进行派生，类的内容模型是应该考虑的一个可能因素。 有关详细信息，请参阅 [WPF 内容模型](../controls/wpf-content-model.md)。  
  
<a name="other_base_classes"></a>
## <a name="other-base-classes"></a>其他基类  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject> 提供对 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 线程模型的支持，并启用为与关联的应用程序创建的所有对象 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Threading.Dispatcher> 。 即使你不是从、或派生的， <xref:System.Windows.UIElement> <xref:System.Windows.DependencyObject> <xref:System.Windows.Media.Visual> 也应考虑从派生，以便 <xref:System.Windows.Threading.DispatcherObject> 获得此线程模型支持。 有关详细信息，请参阅[线程模型](threading-model.md)。  
  
### <a name="visual"></a>视觉对象  
 <xref:System.Windows.Media.Visual> 实现一个二维对象的概念，该对象通常要求在大约矩形区域中显示视觉对象。 的实际呈现 <xref:System.Windows.Media.Visual> 发生在其他类中， (它不是自包含) ，但是 <xref:System.Windows.Media.Visual> 该类提供了一个已知类型，该类型由在不同级别呈现进程使用。 <xref:System.Windows.Media.Visual> 实现命中测试，但不公开报告命中测试误报 (这些事件处于) 中的事件 <xref:System.Windows.UIElement> 。 有关详细信息，请参阅[可视化层编程](../graphics-multimedia/visual-layer-programming.md)。  
  
### <a name="freezable"></a>Freezable  
 <xref:System.Windows.Freezable> 由于性能原因，在需要不可变对象时生成对象的副本，从而模拟可变对象中的非永久性。 <xref:System.Windows.Freezable>类型为某些图形元素（如几何图形和画笔）以及动画提供了一个通用基础。 特别要注意的是，不是 <xref:System.Windows.Freezable> <xref:System.Windows.Media.Visual> ; 它可以保存在 <xref:System.Windows.Freezable> 应用来填充另一个对象的属性值时变成子属性的属性，并且这些子属性可能会影响呈现。 有关详细信息，请参阅 [Freezable 对象概述](freezable-objects-overview.md)。  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable> 是一个 <xref:System.Windows.Freezable> 派生类，它专门添加动画控件层和一些实用工具成员，以便可以与未属性区分当前的动画属性。  
  
### <a name="control"></a>控制  
 <xref:System.Windows.Controls.Control> 是不同称为控件或组件的对象类型的目标基类，具体取决于技术。 一般情况下，[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件类可直接表示 UI 控件或积极参与控件组合。 启用的主要功能 <xref:System.Windows.Controls.Control> 是控件模板化。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Control>
- [依赖项属性概述](dependency-properties-overview.md)
- [控件创作概述](../controls/control-authoring-overview.md)
- [WPF 体系结构](wpf-architecture.md)
