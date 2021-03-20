---
title: XAML 加载和依赖项属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom dependency properties [WPF]
- dependency properties [WPF], XAML loading and
- loading XML data [WPF]
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
ms.openlocfilehash: 8568591296210e6ecff24580c20b4f47cb0b37d5
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667468"
---
# <a name="xaml-loading-and-dependency-properties"></a>XAML 加载和依赖项属性
[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器的当前 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 实现固有地知道依赖属性。 在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 加载 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 作为依赖属性的二进制和处理属性时，处理器使用属性系统方法来处理依赖属性。 这会有效地跳过属性包装器。 实现自定义依赖项属性时，必须考虑此行为，并且应避免将任何其他代码放在属性包装中，而不是属性系统方法 <xref:System.Windows.DependencyObject.GetValue%2A> 和 <xref:System.Windows.DependencyObject.SetValue%2A> 。  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>必备条件  
 本主题假定你已从使用者和创作者角度了解依赖属性，并已阅读[依赖属性概述](dependency-properties-overview.md)和[自定义依赖属性](custom-dependency-properties.md)。 你应也已阅读 [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml) 和 [XAML 语法详述](xaml-syntax-in-detail.md)。  
  
<a name="implementation"></a>
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>WPF XAML 加载程序实现和性能  
 出于实现的原因，将属性标识为依赖属性并访问属性系统 <xref:System.Windows.DependencyObject.SetValue%2A> 方法进行设置，而不是使用属性包装及其 setter，计算开销较低。 这是因为 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器必须仅通过了解由标记结构和多种字符串所指示的类型和成员关系来推断支持代码的整个对象模型。  
  
 该类型通过 xmlns 和程序集特性的组合查找，但标识成员，确定哪些成员可以支持设置为属性，并解析属性值支持的类型，否则需要使用广泛 <xref:System.Reflection.PropertyInfo> 的反射。 由于给定类型上的依赖属性可通过属性系统作为存储表进行访问，因此， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 其处理器的实现将 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 使用此表，并通过 <xref:System.Windows.DependencyObject.SetValue%2A> <xref:System.Windows.DependencyObject> 使用依赖项属性标识符 *ABCProperty*，来推断可以通过在包含派生类型上调用来更有效地设置任何给定的属性 ABC。  
  
<a name="implications"></a>
## <a name="implications-for-custom-dependency-properties"></a>自定义依赖属性的影响  
 由于进行属性设置的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器行为的当前 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 实现会完全跳过包装器，因此对于自定义依赖属性不应将任何其他逻辑放入包装器的设置定义中。 如果将此类逻辑放入设置定义，则在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 而不是代码中设置属性时不会执行逻辑。  
  
 同样，处理器的其他方面 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 也使用从处理获得属性值， [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.DependencyObject.GetValue%2A> 而不是使用包装。 因此，除了调用以外，还应避免定义中的任何附加实现 `get` <xref:System.Windows.DependencyObject.GetValue%2A> 。  
  
 下面的示例是一个建议的依赖属性定义，其中包含包装器，其中的属性标识符存储为 `public` `static` `readonly` 字段， `get` 并且和 `set` 定义不包含除定义依赖属性支持的必要属性系统方法之外的任何代码。  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>请参阅

- [依赖项属性概述](dependency-properties-overview.md)
- [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)
- [依赖项属性元数据](dependency-property-metadata.md)
- [集合类型依赖项属性](collection-type-dependency-properties.md)
- [依赖项属性的安全性](dependency-property-security.md)
- [DependencyObject 的安全构造函数模式](safe-constructor-patterns-for-dependencyobjects.md)
