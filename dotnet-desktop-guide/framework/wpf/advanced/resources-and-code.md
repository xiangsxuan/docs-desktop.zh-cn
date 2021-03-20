---
title: 资源和代码
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys [WPF], using objects as
- resources [WPF], accessing from procedural code
- procedural code [WPF], creating resources with
- procedural code [WPF], accessing resources from
- resources [WPF], creating with procedural code
ms.assetid: c1cfcddb-e39c-41c8-a7f3-60984914dfae
ms.openlocfilehash: e415bb5e79632efe45fc200c04ec3f14197621d7
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664998"
---
# <a name="resources-and-code"></a>资源和代码
本概述主要介绍如何使用代码（而非 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 语法）来访问或创建 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 资源。 有关常规资源用法以及 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 语法角度的资源的详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)。  

<a name="accessing"></a>
## <a name="accessing-resources-from-code"></a>从代码访问资源  
 用于识别通过 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 定义的资源的键也用于检索特定资源（如果你在代码中请求此资源）。 若要从代码中检索资源，最简单的方法是 <xref:System.Windows.FrameworkElement.FindResource%2A> <xref:System.Windows.FrameworkElement.TryFindResource%2A> 从应用程序中的框架级别对象调用或方法。 这两个方法之间的行为差异在于当未找到所请求的键时所发生的情况。 <xref:System.Windows.FrameworkElement.FindResource%2A> 引发异常; <xref:System.Windows.FrameworkElement.TryFindResource%2A> 不会引发异常，而会返回 `null` 。 每个方法都将资源键作为一个输入参数，并返回一个松散类型化对象。 资源键通常是字符串，但有时也用作非字符串；有关详细信息，请参阅[将对象用作键](#objectaskey)部分。 通常应将返回的对象强制转换为请求资源时设置的属性所要求的类型。 代码资源解析的查找逻辑与动态资源引用 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 情况相同。 对资源的搜索从调用元素开始，然后继续搜索逻辑树中的后续父元素。 如果必要，将继续查找应用程序资源、主题以及系统资源。 资源的代码请求将正确地说明资源字典（可能排在从 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 加载的资源字典之后）中的运行时更改，也将说明实时系统资源更改。  
  
 下面是一个简短的代码示例，它按键查找资源，并使用返回的值来设置作为 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件处理程序实现的属性。  
  
 [!code-csharp[PropertiesOvwSupport#ResourceProceduralGet](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#resourceproceduralget)]
 [!code-vb[PropertiesOvwSupport#ResourceProceduralGet](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#resourceproceduralget)]  
  
 分配资源引用的一种替代方法是 <xref:System.Windows.FrameworkElement.SetResourceReference%2A> 。 该方法采用两个参数：资源的键，以及特定依赖属性（应向其分配资源值的元素实例上的依赖属性）的标识符。 就功能而言，此方法是相同的，且具有无需强制转换任何返回值的优点。  
  
 以编程方式访问资源的另一种方法是以 <xref:System.Windows.FrameworkElement.Resources%2A> 字典形式访问属性的内容。 通过访问该属性包含的字典，还可以向现有集合添加新资源、检查集合中是否已经存在给定的键名称以及执行其他字典/集合操作。 如果 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 完全在代码中编写应用程序，则还可以在代码中创建整个集合，为其分配键，然后将完成的集合分配给已 <xref:System.Windows.FrameworkElement.Resources%2A> 建立的元素的属性。 这将在下一部分介绍。  
  
 您可以 <xref:System.Windows.FrameworkElement.Resources%2A> 使用特定键作为索引在任何给定集合中进行索引，但您应注意，以这种方式访问资源不遵循资源解析的正常运行时规则。 你访问的仅是该特定集合。 如果在请求的键处未找到有效的对象，则资源查找将不会遍历范围直至根或应用程序。 但是，在某些情况下，正因为对键的搜索范围进行了更多的约束，才使得此方法在性能上具有优势。 <xref:System.Windows.ResourceDictionary>有关如何直接使用资源字典的详细信息，请参见类。  
  
<a name="creating"></a>
## <a name="creating-resources-with-code"></a>使用代码创建资源  
 如果要通过代码方式创建整个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序，可能也需要通过代码方式创建该应用程序中的任何资源。 若要实现此目的，请创建一个新的 <xref:System.Windows.ResourceDictionary> 实例，然后使用对的连续调用将所有资源添加到字典中 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 。 然后，使用 <xref:System.Windows.ResourceDictionary> 创建的来设置 <xref:System.Windows.FrameworkElement.Resources%2A> 页面范围中存在的元素的属性或 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 。 你还可以将 <xref:System.Windows.ResourceDictionary> 用作独立对象，而无需将其添加到元素。 但是，如果这样做，必须通过项键来访问其中的资源，就好像它是泛型字典一样。 <xref:System.Windows.ResourceDictionary>未附加到元素属性的不是 `Resources` 元素树的一部分，并且在查找序列中没有可供和相关方法使用的作用域 <xref:System.Windows.FrameworkElement.FindResource%2A> 。  
  
<a name="objectaskey"></a>
## <a name="using-objects-as-keys"></a>将对象用作键  
 大多数资源用法都会将资源的键设置为字符串。 但是，各个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 功能都特意不使用字符串类型来指定键，而是将此参数设置为对象。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 样式和主题支持使用按对象对资源进行键控的功能。 如果主题中的样式是其他非样式控件的默认样式，则这些样式将由 <xref:System.Type> 其应用于的控件的进行键控。 按类型进行键控提供了一种可靠的查找机制，该机制作用于每个控件类型的默认实例，即使派生类型不具有默认样式，也可以通过反射检测到类型，并将类型用于设置派生类的样式。 可以 <xref:System.Type> [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 通过使用 [x:Type 标记扩展](/dotnet/desktop-wpf/xaml-services/xtype-markup-extension)为中定义的资源指定密钥。 对于支持 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 功能的其他非字符串键用法，也存在类似扩展，如 [ComponentResourceKey 标记扩展](componentresourcekey-markup-extension.md)。  
  
## <a name="see-also"></a>请参阅

- [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
