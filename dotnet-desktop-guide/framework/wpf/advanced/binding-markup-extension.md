---
title: 绑定标记扩展
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: e31439f453111fb8ff76ddf10e6f969509ab6081
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666220"
---
# <a name="binding-markup-extension"></a>绑定标记扩展
将属性值延迟为数据绑定值，创建中间表达式对象并在运行时解释应用于该元素及其绑定的数据上下文。  
  
## <a name="binding-expression-usage"></a>绑定表达式使用情况  
  
```xaml  
<object property="{Binding}" .../>  
-or-  
<object property="{Binding  bindProp1=value1[, bindPropN=valueN]*}" ...  
/>  
-or-  
<object property="{Binding path}" .../>  
-or  
<object property="{Binding path[, bindPropN=valueN]*}" .../>  
```  
  
## <a name="syntax-notes"></a>语法说明  
 在这些语法中， `[]` 和不 `*` 是文本。 它们是表示法的一部分，用于指示可以使用零个或多个 *bindProp* `=` *值* 对，其中 `,` 分隔符和前面的 *bindProp* `=` *值* 对。  
  
 可以改为使用对象元素的属性设置 "可以使用绑定扩展设置的绑定属性" 部分中列出的任何属性 <xref:System.Windows.Data.Binding> 。 但是，这并不是真正的标记扩展用法 <xref:System.Windows.Data.Binding> ，只是用于设置 CLR 类的属性的属性的常规 XAML 处理 <xref:System.Windows.Data.Binding> 。 换句话说， `<Binding` *bindProp1* `="` *value1* `"[` *bindPropN* `="` *valueN* `"]*/>` 是对象元素用法的属性的等效语法， <xref:System.Windows.Data.Binding> 而不是 `Binding` 表达式用法。 若要了解的特定属性的 XAML 特性用法 <xref:System.Windows.Data.Binding> ，请参阅 .NET Framework 类库中的相关属性的 "Xaml 特性用法" 部分 <xref:System.Windows.Data.Binding> 。  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|<xref:System.Windows.Data.Binding>要设置的或属性的名称 <xref:System.Windows.Data.BindingBase> 。 并非所有 <xref:System.Windows.Data.Binding> 属性都可以使用扩展进行设置 `Binding` ，并且某些属性 `Binding` 只能通过使用更多嵌套标记扩展在表达式中设置。 请参阅 "绑定可通过绑定扩展进行设置的属性" 一节。|  
|`value1, valueN`|要将属性设置为的值。 特性值的处理最终特定于所设置的特定属性的类型和逻辑 <xref:System.Windows.Data.Binding> 。|  
|`path`|设置隐式属性的路径字符串 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 。 另请参阅 [PROPERTYPATH XAML 语法](propertypath-xaml-syntax.md)。|  
  
## <a name="unqualified-binding"></a>非限定 {Binding}  
 `{Binding}`"绑定表达式使用情况" 中显示的用法使用 <xref:System.Windows.Data.Binding> 默认值创建一个对象，该对象包含的初始 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> `null` 。 这在许多情况下仍有用，因为创建的 <xref:System.Windows.Data.Binding> 可能依赖于关键数据绑定属性，如 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> 在运行时数据上下文中设置。 有关数据上下文概念的详细信息，请参阅 [数据绑定](/dotnet/desktop-wpf/data/data-binding-overview)。  
  
## <a name="implicit-path"></a>隐式路径  
 `Binding`标记扩展将 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 用作概念 "默认属性"，其中 `Path=` 无需出现在表达式中。 如果 `Binding` 使用隐式路径指定表达式，则隐式路径必须出现在表达式中的第一个位置，然后再将 `bindProp` = `value` 该 <xref:System.Windows.Data.Binding> 属性指定为名称。 例如： `{Binding PathString}` ，其中 `PathString` 是一个字符串，其计算结果为 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 标记扩展用法所创建的中的值 <xref:System.Windows.Data.Binding> 。 可以在逗号分隔符后面追加具有其他命名属性的隐式路径，例如 `{Binding LastName, Mode=TwoWay}` 。  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>可通过绑定扩展进行设置的绑定属性  
 本主题中所示的语法使用通用 `bindProp` = `value` 近似值，因为 <xref:System.Windows.Data.BindingBase> <xref:System.Windows.Data.Binding> 可以通过 `Binding` 标记扩展/表达式语法设置或的多个读/写属性。 它们可以按任意顺序进行设置，但隐式除外 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 。  (您可以选择显式指定 `Path=` ，在这种情况下，可以按任意顺序) 设置。 基本上，可以使用 `bindProp` = 以逗号分隔的对，在下面的列表中设置零个或多个属性 `value` 。  
  
 其中一些属性值需要对象类型，这些对象类型不支持 XAML 中的文本语法的本机类型转换，因此需要标记扩展才能设置为属性值。 有关详细信息，请查看每个属性的 .NET Framework 类库中的 XAML 特性用法部分;用于带有或不带进一步标记扩展用法的 XAML 属性语法的字符串基本上与你在表达式中指定的值相同，只是 `Binding` 你不会 `bindProp` = `value` 在表达式中的每个中放置引号 `Binding` 。  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>：一个字符串，用于标识可能的绑定组。 这是一个相对较高级的绑定概念;请参阅的参考页 <xref:System.Windows.Data.BindingBase.BindingGroupName%2A> 。  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>：布尔值，可以是 `true` 或 `false` 。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.Converter%2A>：可 `bindProp` = `value` 在表达式中设置为字符串，但要执行此操作，需要对值使用对象引用，如[StaticResource 标记扩展](staticresource-markup-extension.md)。 在此示例中，值是自定义转换器类的实例。  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>：可在表达式中设置为基于标准的标识符;请参阅的参考主题 <xref:System.Windows.Data.Binding.ConverterCulture%2A> 。  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>：可以设置为 `bindProp` = `value` 表达式中的字符串，但这取决于传递的参数的类型。 如果传递值的引用类型，则此用法需要对象引用，例如嵌套的 [StaticResource 标记扩展](staticresource-markup-extension.md)。  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>：互相排斥与 <xref:System.Windows.Data.Binding.RelativeSource%2A> 和 <xref:System.Windows.Data.Binding.Source%2A> ; 每个绑定属性都表示一个特定的绑定方法。 请参阅 [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)。  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>：可以设置为 `bindProp` = `value` 表达式中的字符串，但这取决于所传递的值的类型。 如果传递引用类型，则需要对象引用，例如嵌套的 [StaticResource 标记扩展](staticresource-markup-extension.md)。  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>：布尔值，可以是 `true` 或 `false` 。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.Mode%2A>： *值* 是来自枚举的常量名称 <xref:System.Windows.Data.BindingMode> 。 例如 `{Binding Mode=OneWay}`。  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>：布尔值，可以是 `true` 或 `false` 。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>：布尔值，可以是 `true` 或 `false` 。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>：布尔值，可以是 `true` 或 `false` 。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.Path%2A>：描述数据对象或常规对象模型的路径的字符串。 格式为遍历对象模型提供了几种不同的约定，此约定在本主题中无法充分介绍。 请参阅 [PROPERTYPATH XAML 语法](propertypath-xaml-syntax.md)。  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>：与 <xref:System.Windows.Data.Binding.ElementName%2A> 和和互相排斥 <xref:System.Windows.Data.Binding.Source%2A> ; 每个绑定属性都表示一个特定的绑定方法。 请参阅 [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)。 要求使用嵌套的 [RelativeSource MarkupExtension](relativesource-markupextension.md) ，以指定值。  
  
- <xref:System.Windows.Data.Binding.Source%2A>：互相排斥与 <xref:System.Windows.Data.Binding.RelativeSource%2A> 和 <xref:System.Windows.Data.Binding.ElementName%2A> ; 每个绑定属性都表示一个特定的绑定方法。 请参阅 [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)。 要求使用嵌套扩展用法，通常是一个 [StaticResource 的标记扩展](staticresource-markup-extension.md) ，它从键控资源字典引用对象数据源。  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>：一个字符串，描述绑定数据的字符串格式约定。 这是一个相对较高级的绑定概念;请参阅的参考页 <xref:System.Windows.Data.BindingBase.StringFormat%2A> 。  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>：可以设置为 `bindProp` = `value` 表达式中的字符串，但这取决于传递的参数的类型。 如果传递值的引用类型，则需要对象引用，例如嵌套的 [StaticResource 标记扩展](staticresource-markup-extension.md)。  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>： *值* 是来自枚举的常量名称 <xref:System.Windows.Data.UpdateSourceTrigger> 。 例如 `{Binding UpdateSourceTrigger=LostFocus}`。 对于此绑定属性，特定控件可能具有不同的默认值。 请参阅 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>。  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>：布尔值，可以是 `true` 或 `false` 。 默认值为 `false`。 请参阅“备注”。  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>：布尔值，可以是 `true` 或 `false` 。 默认值为 `false`。 请参阅“备注”。  
  
- <xref:System.Windows.Data.Binding.XPath%2A>：描述 XML 数据源的 XMLDOM 路径的字符串。 请参阅 [使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。  
  
 以下是 <xref:System.Windows.Data.Binding> 无法使用 `Binding` 标记扩展/ `{Binding}` 表达式窗体设置的属性。  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>：此属性需要对回调实现的引用。 不能在 XAML 语法中引用事件处理程序以外的回调/方法。  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>：属性采用对象的泛型集合 <xref:System.Windows.Controls.ValidationRule> 。 这可以表示为对象元素中的属性元素 <xref:System.Windows.Data.Binding> ，但没有任何可用于表达式中的用法的属性分析技术 `Binding` 。 请参阅参考主题 <xref:System.Windows.Data.Binding.ValidationRules%2A> 。  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>备注  
  
> [!IMPORTANT]
> 就依赖属性优先级而言， `Binding` 表达式等效于本地设置的值。 如果为先前具有表达式的属性设置本地值，则将 `Binding` `Binding` 完全删除。 有关详细信息，请参阅[依赖属性值优先级](dependency-property-value-precedence.md)。  
  
 本主题不涉及在基本级别描述数据绑定。 请参阅 [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)。  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding> 和 <xref:System.Windows.Data.PriorityBinding> 不支持 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 扩展语法。 您将改用属性元素。 请参阅和的参考主题 <xref:System.Windows.Data.MultiBinding> <xref:System.Windows.Data.PriorityBinding> 。  
  
 XAML 的布尔值不区分大小写。 例如，可以指定 `{Binding NotifyOnValidationError=true}` 或 `{Binding NotifyOnValidationError=True}` 。  
  
 涉及数据验证的绑定通常由显式 `Binding` 元素（而不是 `{Binding ...}` 表达式）指定，而表达式中的设置 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 或 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 不常见。 这是因为 <xref:System.Windows.Data.Binding.ValidationRules%2A> 不能在表达式窗体中轻松设置伴生属性。 有关详细信息，请参阅 [实现绑定验证](../data/how-to-implement-binding-validation.md)。  
  
 `Binding` 是标记扩展。 通常在要求转义特性值时，通常会实现标记扩展，而不是文本值或处理程序名称，并且该要求比在某些类型或属性上指定的类型转换器更全局性。 XAML 中的所有标记扩展在 `{` `}` 其特性语法中使用和字符，这是 xaml 处理器识别标记扩展必须处理字符串内容的约定。 有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
 `Binding` 是一个非典型的标记扩展，因为 <xref:System.Windows.Data.Binding> 实现 WPF XAML 实现扩展功能的类还实现了一些与 XAML 无关的其他方法和属性。 其他成员旨在创建 <xref:System.Windows.Data.Binding> 更通用和独立的类，这些类可用于处理除作为 XAML 标记扩展以外的许多数据绑定方案。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.Binding>
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
