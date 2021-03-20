---
title: 优化性能：应用程序资源
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
ms.openlocfilehash: f5e99e1566f254c83b7562592690c9c1f334516e
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666857"
---
# <a name="optimizing-performance-application-resources"></a>优化性能：应用程序资源
[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 允许共享应用程序资源，使你能够跨相似类型的元素支持一致的外观或行为。 本主题提供了此方面的几项建议，可帮助您提高应用程序的性能。  
  
 有关资源的详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)。  
  
## <a name="sharing-resources"></a>共享资源  
 如果你的应用程序使用自定义控件并在 <xref:System.Windows.ResourceDictionary> (或 XAML 资源节点) 中定义资源，则建议你在 <xref:System.Windows.Application> 或对象级别定义资源 <xref:System.Windows.Window> ，或者在自定义控件的默认主题中定义这些资源。 在自定义控件中定义资源 <xref:System.Windows.ResourceDictionary> 会对该控件的每个实例产生性能影响。 例如，如果您有一些在自定义控件的资源定义和自定义控件实例的资源定义中定义的性能密集型画笔操作，则应用程序的工作集会显著增加。  
  
 为了说明这一点，请考虑以下事项。 假设您正在使用开发纸牌游戏 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 对于大多数纸牌游戏，需要52个包含52个不同表面的卡。 您决定实现卡片自定义控件，并定义52画笔 (每个画笔表示卡片自定义控件的资源) 。 在主应用程序中，最初创建此卡自定义控件的52实例。 卡自定义控件的每个实例都会生成52个 <xref:System.Windows.Media.Brush> 对象实例，这为您的应用程序提供了总共 52 * 52 <xref:System.Windows.Media.Brush> 对象。 通过将画笔从卡片自定义控件资源移出到 <xref:System.Windows.Application> 或 <xref:System.Windows.Window> 对象级别，或在自定义控件的默认主题中进行定义，可以减少应用程序的工作集，因为现在可以在卡片控件的52实例之间共享52画笔。  
  
## <a name="sharing-a-brush-without-copying"></a>共享画笔而不复制  
 如果有多个使用同一对象的元素 <xref:System.Windows.Media.Brush> ，请将画笔定义为资源并对其进行引用，而不是在 XAML 中以内联方式定义画笔。 此方法将创建一个实例并重复使用它，而在 XAML 中以内联方式定义将为每个元素创建一个新的实例。  
  
 以下标记示例说明了这一点：  
  
 [!code-xaml[Performance#PerformanceSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>尽可能使用静态资源  
 静态资源通过查找对已定义资源的引用来为任何 XAML 属性特性提供一个值。 该资源的查找行为类似于编译时查找。  
  
 另一方面，动态资源将在初始编译期间创建一个临时表达式，从而推迟资源的查找，直到实际需要请求的资源值才能构造对象。 该资源的查找行为类似于运行时查找，这会影响性能。 在应用程序中尽可能使用静态资源，仅在必要时使用动态资源。  
  
 以下标记示例演示如何使用两种类型的资源：  
  
 [!code-xaml[Performance#PerformanceSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a>请参阅

- [优化 WPF 应用程序性能](optimizing-wpf-application-performance.md)
- [规划应用程序性能](planning-for-application-performance.md)
- [利用硬件](optimizing-performance-taking-advantage-of-hardware.md)
- [布局和示例](optimizing-performance-layout-and-design.md)
- [二维图形和图像处理](optimizing-performance-2d-graphics-and-imaging.md)
- [对象行为](optimizing-performance-object-behavior.md)
- [文本](optimizing-performance-text.md)
- [数据绑定](optimizing-performance-data-binding.md)
- [其他性能建议](optimizing-performance-other-recommendations.md)
