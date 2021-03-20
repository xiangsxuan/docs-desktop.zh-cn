---
title: 框架属性元数据
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: 33ed083a3ad26d52f3ffed8b757719f21d8bae32
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665453"
---
# <a name="framework-property-metadata"></a>框架属性元数据
对于 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 体系结构中被视为 WPF 框架级的对象元素的属性，将报告框架属性元数据选项。 通常，WPF 框架级别的指定要求呈现 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] api 和可执行文件处理呈现、数据绑定和属性系统优化等功能。 这些系统对框架属性元数据进行查询，以便为特定的元素属性确定特定于功能的特征。  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>必备条件  
 本主题假定你从 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 类的现有依赖属性的使用者角度了解依赖属性，并且已阅读[依赖属性概述](dependency-properties-overview.md)。 另外，应当已阅读[依赖属性元数据](dependency-property-metadata.md)。  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>
## <a name="what-is-communicated-by-framework-property-metadata"></a>框架属性元数据传达的信息  
 框架属性元数据分为以下类别：  
  
- 报表 (、) 影响元素的布局 <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> 属性 <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A> 。 如果属性影响到各个方面，则可以在元数据中设置这些标志，还可以实现 <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 类中的方法，以向布局系统提供特定的呈现行为和信息。 通常，如果在属性元数据中有布局属性为 true，则此类实现会在依赖属性中检查属性是否无效，并且只有无效属性才必须请求新的布局处理过程。  
  
- 报告影响元素的父元素的布局属性 (<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A> ， <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>) 。 默认情况下，设置这些标志的一些示例为 <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType> 。  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>. 默认情况下，依赖属性不会继承值。 <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> 允许将继承的路径传递到可视化树，这对于某些控件组合方案是必需的。  
  
    > [!NOTE]
    > 属性值上下文中的术语“继承”指特定于依赖属性的情况；它意味着由于存在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 属性系统的 WPF 框架级功能，子元素可以从父元素继承实际的依赖属性值。 它与通过派生类型的托管代码类型和成员继承没有直接关系。 有关详细信息，请参阅[属性值继承](property-value-inheritance.md)。  
  
- 报表数据绑定特征 (<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A> ， <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>) 。 默认情况下，框架中的依赖属性支持具有单向绑定行为的数据绑定。 如果没有 (的方案，则可以禁用数据绑定，因为它们的用途是灵活且可扩展的，所以在默认 api) 中没有很多示例 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 你可以将绑定设置为具有两种默认值，用于在其组件部分之间绑定控件行为的属性 (<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> 是一个示例) 或者，双向绑定是用户 (的 <xref:System.Windows.Controls.TextBox.Text%2A> 一个示例) 。 更改与数据绑定相关的元数据只会影响默认值；始终可以根据各个绑定更改此默认值。 若要详细了解常规的绑定模式和绑定，请参阅[数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)。  
  
- 报告是否应按支持日记 () 的应用程序或服务记录属性 <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A> 。 对于一般的元素，默认情况下不会启用日记记录功能，但可针对特定用户输入控件有选择性地启用。 此属性专门由日记记录的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 实现等日记记录服务读取，并且通常针对用户控件（例如用户在列表中选择的应在各导航步骤中保留的控件）设置此属性。 有关日记的信息，请参阅[导航概述](../app-development/navigation-overview.md)。  
  
<a name="Reading_FrameworkPropertyMetadata"></a>
## <a name="reading-frameworkpropertymetadata"></a>读取 FrameworkPropertyMetadata  
 以上链接的每个属性都是 <xref:System.Windows.FrameworkPropertyMetadata> 添加到其直接基类的特定属性 <xref:System.Windows.UIPropertyMetadata> 。 默认情况下，这些属性都为 `false`。 在知道这些属性的值的情况下，属性的元数据请求应尝试将返回的元数据强制转换为 <xref:System.Windows.FrameworkPropertyMetadata> ，然后根据需要检查各个属性的值。  
  
<a name="Specifying_Metadata"></a>
## <a name="specifying-metadata"></a>指定元数据  
 当你创建新的元数据实例以将元数据应用于新的依赖属性注册时，你可以选择要使用的元数据类：基 <xref:System.Windows.PropertyMetadata> 或一些派生类（如） <xref:System.Windows.FrameworkPropertyMetadata> 。 通常情况下，应使用 <xref:System.Windows.FrameworkPropertyMetadata> ，特别是在属性与属性系统和 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 功能（如布局和数据绑定）交互的情况下。 对于更复杂的方案，另一个选项是从派生 <xref:System.Windows.FrameworkPropertyMetadata> ，以创建自己的元数据报告类，并在其成员中携带额外的信息。 或者，你可以使用 <xref:System.Windows.PropertyMetadata> 或 <xref:System.Windows.UIPropertyMetadata> 来传达实现的功能的支持程度。  
  
 对于 (<xref:System.Windows.DependencyProperty.AddOwner%2A> 或调用) 的现有属性 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> ，应始终使用初始注册使用的元数据类型重写。  
  
 如果创建的是 <xref:System.Windows.FrameworkPropertyMetadata> 实例，可以通过两种方式来使用传达框架属性特征的特定属性的值来填充元数据：  
  
1. 使用 <xref:System.Windows.FrameworkPropertyMetadata> 允许使用参数的构造函数 `flags` 签名。 应为此参数填充枚举标志的所有所需的组合值 <xref:System.Windows.FrameworkPropertyMetadataOptions> 。  
  
2. 使用不带参数的其中一个签名 `flags` ，然后将每个报告的布尔属性设置为，以 <xref:System.Windows.FrameworkPropertyMetadata> `true` 针对每个所需的特征更改。 为此，必须在构造具有此依赖属性的任何元素之前对这些属性进行设置；布尔属性是可读写属性，以允许此项避免 `flags` 参数的行为，同时仍然可以填充元数据，但元数据必须在属性使用之前进行有效密封。 因此，尝试在请求元数据之后设置属性是无效操作。  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>
## <a name="framework-property-metadata-merge-behavior"></a>框架属性元数据合并行为  
 重写框架属性元数据时，会合并或替换不同的元数据特征。  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 合并。 如果添加新 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 的，则该回调将存储在元数据中。 如果未 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 在重写中指定，则的值 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 将从在元数据中指定的最接近的上级中升级为引用。  
  
- 的实际属性系统行为 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 是：在层次结构中的所有元数据所有者的实现将被保留并添加到表中，属性系统执行顺序是先调用最深层派生类的回调。 继承的回叫仅运行一次，当将这些回叫放置在元数据中的类占有时计数。  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 被替换。 如果未 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 在重写中指定，则的值来自在 <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 元数据中指定它的最近上级。  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 替换实现。 如果添加新 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 的，则该回调将存储在元数据中。 如果未 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 在重写中指定，则的值 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 将从在元数据中指定的最接近的上级中升级为引用。  
  
- 属性系统行为是只 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 调用直接元数据中的。 不 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 会保留对层次结构中的其他实现的引用。  
  
- 枚举的标志 <xref:System.Windows.FrameworkPropertyMetadataOptions> 合并为按位 "或" 运算。  如果指定 <xref:System.Windows.FrameworkPropertyMetadataOptions> ，则不会覆盖原始选项。  若要更改选项，请在上设置相应的属性 <xref:System.Windows.FrameworkPropertyMetadata> 。 例如，如果原始 <xref:System.Windows.FrameworkPropertyMetadata> 对象设置了 <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> 标志，则可以通过将设置为来更改该标志 <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> `false` 。  
  
 此行为由实现 <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A> ，并且可在派生的元数据类上重写。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [依赖项属性元数据](dependency-property-metadata.md)
- [依赖项属性概述](dependency-properties-overview.md)
- [自定义依赖项属性](custom-dependency-properties.md)
