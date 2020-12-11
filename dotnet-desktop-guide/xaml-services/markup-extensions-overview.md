---
title: XAML 的标记扩展概述
ms.date: 03/30/2017
helpviewer_keywords:
- markup extensions [XAML Services], custom
- XAML [XAML Services], markup extensions
ms.assetid: 261b2b11-2dc0-462f-8c66-55b8c9c6e436
ms.openlocfilehash: 69f9d899b9a33d3de2fd7762990925138a47767c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972872"
---
# <a name="overview-of-markup-extensions-for-xaml"></a>XAML 的标记扩展概述

标记扩展是一种用于获取非基元或特定 XAML 类型的值的 XAML 方法。 对于特性用法，标记扩展使用已知的左大括号 `{` 字符序列输入标记扩展范围，并使用右大括号 `}` 退出。 使用 .NET XAML 服务时，可以使用来自 system.exception 程序集的某些预定义 XAML 语言标记扩展。 还可以使用 <xref:System.Windows.Markup.MarkupExtension> 类（在 System.Xaml 中定义）的子类，并定义自己的标记扩展。 或者，如果您已在引用框架，则可以使用由特定框架定义的标记扩展。

访问标记扩展用法时，XAML 对象编写器可以通过 <xref:System.Windows.Markup.MarkupExtension> 重写中的服务连接点向自定义 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A?displayProperty=nameWithType> 类提供服务。 服务可以用于获取有关用法的上下文、对象编写器的特定功能、XAML 架构上下文等。

## <a name="xaml-defined-markup-extensions"></a>XAML 定义的标记扩展

.NET XAML 服务为 XAML 语言支持实现了几个标记扩展。 这些标记扩展与作为一种语言的 XAML 规范各部分相对应。 这些扩展通常在语法中可由 `x:` 前缀进行标识（如常见用法中所见）。 这些 XAML 语言元素的 .NET XAML 服务实现都派生自  <xref:System.Windows.Markup.MarkupExtension> 基类。

> [!NOTE]
> `x:` 前缀用于 XAML 语言命名空间中的典型 XAML 命名空间映射（在 XAML 生成的根元素中）。 例如，用于各种特定框架的 Visual Studio 项目和页面模板会使用此映射启动一个 XAML 文件 `x:` 。 可以在自己的 XAML 命名空间映射中选择不同的前缀标记，但是本文档采用默认值 `x:` 映射来标识作为 XAML 语言 XAML 命名空间的已定义部分的实体，而不是采用特定框架的默认 XAML 命名空间或其他任意 CLR 或 XML 命名空间。

### <a name="xtype"></a>x:Type

`x:Type` 为命名类型提供 <xref:System.Type> 对象。 此功能最常在使用基础 CLR 类型和类型派生作为分组名字对象或标识符的延迟机制中使用。 WPF 样式和模板以及其 `TargetType` 属性的用法是一个具体示例。 有关详细信息，请参阅 [x:Type Markup Extension](xtype-markup-extension.md)。

### <a name="xstatic"></a>x:Static

`x:Static` 从值-类型代码实体生成静态值，它们不直接是属性值的类型，但可以计算为该类型。 这可用于将已存在的值指定为类型定义中的已知常量。 有关详细信息，请参阅 [x:Static Markup Extension](xstatic-markup-extension.md)。

### <a name="xnull"></a>x:Null

`x:Null` 指定 `null` 作为 XAML 成员的值。 根据特定类型的设计或更大框架概念， `null` 并不总是属性的默认值，或是空字符串特性的隐式值。 有关详细信息，请参阅 [x:Null Markup Extension](xnull-markup-extension.md)。

### <a name="xarray"></a>x:Array

`x:Array` 支持采用 XAML 语法创建常规数组，以防出现故意不使用由基元素和控件模型提供的集合支持的情况。 有关更多信息，请参见 [x:Array Markup Extension](xarray-markup-extension.md)。 具体而言，在 XAML 2009 中，数组是作为语言基元而不是作为扩展进行访问。 有关更多信息，请参见 [XAML 2009 Language Features](xaml-2009-language-features.md)。

### <a name="xreference"></a>x:Reference

`x:Reference` 属于 XAML 2009（原始 (2006) 语言集的扩展）。 `x:Reference` 表示对对象图中另一个现有对象的引用。 该对象由其 `x:Name`进行标识。 有关详细信息，请参阅 [x:Reference Markup Extension](xreference-markup-extension.md)。

### <a name="other-x-constructs"></a>其他 x: 构造

还有其他用于支持 XAML 语言功能的 `x:` 构造，不过这些构造并不作为标记扩展而实现。 有关详细信息，请参阅 [XAML 命名空间 (x:)语言功能](namespace-language-features.md)。

## <a name="the-markupextension-base-class"></a>MarkupExtension 基类

若要定义可以与 System.Xaml 中 XAML 读取器和 XAML 编写器的默认实现进行交互的自定义标记扩展，可从抽象 <xref:System.Windows.Markup.MarkupExtension> 类派生类。 该类具有一个用于重写的方法，即 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>。 可能还需要定义其他构造函数来支持用于标记扩展用法和匹配可设置属性的参数。

通过 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> ，自定义标记扩展有权访问一个服务上下文，该服务上下文报告 XAML 处理器调用标记扩展的环境。 在加载路径中，这通常是 <xref:System.Xaml.XamlObjectWriter> 。 在保存路径中，这通常是 <xref:System.Xaml.XamlXmlWriter>。 每项都将服务上下文报告为内部 XAML 服务提供程序上下文类，该类可实现一种服务提供程序模式。 有关可用服务以及它们所表示的含义的详细信息，请参阅 [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md)。

标记扩展类必须使用公共访问级别；XAML 处理器必须始终能够实例化标记扩展的支持类，以便使用其服务。

## <a name="defining-the-support-type-for-a-custom-markup-extension"></a>为自定义标记扩展定义支持类型

使用 .net xaml 服务或在 .NET XAML 服务上构建的框架时，对于如何命名标记扩展支持类型有两种选择。 类型名与 XAML 对象编写器在 XAML 中遇到标记扩展用法时如何尝试访问并调用标记扩展支持类型相关。 使用以下命名策略之一：

- 将类型名命名为与 XAML 标记用法标记完全匹配。 例如，若要支持 `{Collate ...}` 扩展用法，请将支持类型命名为 `Collate`。
- 将类型名命名为用法字符串标记加上后缀 `Extension`。 例如，若要支持 `{Collate ...}` 扩展用法，请将支持类型命名为 `CollateExtension`。

查找顺序是首先查找带 `Extension`后缀的类名，然后查找不带 `Extension` 后缀的类名。

从标记用法的角度来看，在用法中包含 `Extension` 后缀是有效的。 但是，这种方法的行为如同 `Extension` 真正是类名的一部分，如果标记扩展支持类没有 `Extension` 后缀，XAML 对象编写器会无法针对该用法解析支持类。

### <a name="the-parameterless-constructor"></a>无参数构造函数

对于所有标记扩展支持类型，应公开一个公共的无参数构造函数。 对于 XAML 对象编写器从对象元素用法实例化标记扩展的任何情况，都需要一个无参数的构造函数。 支持对象元素用法对于标记扩展是合理预期（特别是对于序列化）。 但是，如果只想支持标记扩展的特性用法，则可以在没有公共构造函数的情况下实现标记扩展。

如果标记扩展用法没有参数，则需要使用无参数构造函数来支持使用。

## <a name="constructor-patterns-and-positional-arguments-for-a-custom-markup-extension"></a>自定义标记扩展的构造函数模式和位置参数

对于具有预期参数用法的标记扩展，公共构造函数必须对应于预期用法的模式。 换句话说，如果标记扩展设计为需要一个位置参数作为有效用法，则应支持一个输入参数采用位置参数的公共构造函数。

例如，假设 `Collate` 标记扩展旨在仅支持以下模式：有一个表示其模式的位置参数，指定为 `CollationMode` 枚举常量。 在这种情况下，应存在具有以下形式的构造函数：

```csharp
public Collate(CollationMode collationMode) {...}
```

在基本级别，传递到标记扩展的参数是字符串，因为它们从标记的特性值进行转发。 可以在该级别创建所有参数字符串并处理输入。 但是，的确可以访问在标记扩展参数传递到支持类之前发生的某些处理。

处理的工作原理在概念上如同标记扩展是要创建的对象，然后设置其成员值。 要设置的每个指定属性的计算方式都类似于如何在分析 XAML 时对创建的对象设置指定成员。 有两个重要的差异：

- 如前所述，标记扩展支持类型不需要具有无参数的构造函数即可在 XAML 中进行实例化。 其对象构造会推迟到文本语法中的可能参数进行词汇切分并计算为位置或命名参数，会在该时间调用适当的构造函数。
- 标记扩展用法可以进行嵌套。 首先计算最内层的标记扩展。 因此，可以采用这类用法，并一个构造参数声明为需要生成值转换器（如标记扩展）的类型。

前面的示例演示了对这类处理的依赖。 .NET XAML 服务 XAML 对象编写器会在本机级别将枚举常量名处理为枚举值。

标记扩展位置参数的文本语法处理还可以依赖于与构造参数中的类型相关联的类型转换器。

这些参数称为位置参数，因为用法中的标记的出现顺序对应于将它们分配给的构造函数参数的位置顺序。 例如，请考虑以下构造函数签名：

```csharp
public Collate(CollationMode collationMode, object collateThis) {...}
```

XAML 处理器对于此标记扩展需要两个位置参数。 如果存在用法 `{Collate AlphaUp,{x:Reference circularFile}}`，则 `AlphaUp` 标记会发送到第一个参数并计算为 `CollationMode` 枚举命名常量。 内部 `x:Reference` 的结果会发送到第二个参数并计算为一个对象。

在用于标记扩展语法和处理的 XAML 指定规则中，逗号是参数之间的分隔符（无论这些参数是位置参数还是命名参数）。

### <a name="duplicate-arity-of-positional-arguments"></a>位置参数的重复 arity

如果 XAML 对象编写器遇到具有位置参数的标记扩展用法，并且有多个采用该数量的参数（重复 Arity）的构造函数参数，则这不一定是错误。 行为取决于可自定义的 XAML 架构上下文设置 <xref:System.Xaml.XamlSchemaContextSettings.SupportMarkupExtensionsWithDuplicateArity%2A>。 如果 <xref:System.Xaml.XamlSchemaContextSettings.SupportMarkupExtensionsWithDuplicateArity%2A> 是 `true`，则 XAML 对象编写器不应仅由于重复 Arity 而引发异常。 未严格定义超越该点的行为。 基本设计假设是架构上下文具有可用于特定参数的类型信息，并且可以尝试与重复候选项匹配的显式强制转换，以查看哪个签名可能是最佳匹配。 如果没有签名可以通过在 XAML 对象编写器上运行的该特定架构上下文施加的测试，则仍可能会引发异常。

默认情况下， <xref:System.Xaml.XamlSchemaContextSettings.SupportMarkupExtensionsWithDuplicateArity%2A> 位于 `false` 基于 CLR <xref:System.Xaml.XamlSchemaContext> 的 For .net XAML 服务中。 因此，如果遇到在后备类型的构造函数中有重复 arity 的标记扩展用法，则默认值 <xref:System.Xaml.XamlObjectWriter> 会引发异常。

## <a name="named-arguments-for-a-custom-markup-extension"></a>自定义标记扩展的命名参数

XAML 指定的标记扩展还可以使用命名参数形式来实现用法。 在第一个词汇切分级别上，文本语法划分为各个参数。 任何参数中存在等号 (=) 都会将参数标识为命名参数。 这类参数还会词汇切分为名称/值对。 这种情况下的名称会命名标记扩展的支持类型的公共可设置属性。 如果要支持命名参数用法，则应提供这些公共可设置属性。 这些属性可以是继承的属性，只要它们仍然是公共属性。

## <a name="accessing-service-provider-context-from-a-markup-extension-implementation"></a>从标记扩展实现访问服务提供程序上下文

可用服务对于任何值转换器都是相同的。 不同之处在于每个值转换器接收服务上下文的方式。 访问服务以及可用服务在主题 [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md)中进行了说明。

## <a name="property-element-usage-of-a-markup-extension"></a>标记扩展的属性元素用法

标记扩展用法方案通常是围绕在特性用法中使用标记扩展来设计的。 但是，还可能可以定义后备类以支持属性元素用法。

若要支持标记扩展的属性元素用法，请定义公共无参数构造函数。 这应是实例构造函数，而不是静态构造函数。 这是必需的，因为 XAML 处理器通常必须对它从标记处理的任何对象元素调用无参数的构造函数，并且这包括标记扩展类作为对象元素。 对于高级方案，可以为类定义非默认构造路径。  (有关详细信息，请参阅 [X:FactoryMethod 指令](xfactorymethod-directive.md)。 ) 不过，您不应将这些模式用于标记扩展目的，因为这使得对使用模式的发现更难，同时用于设计人员和用于原始标记的用户。

## <a name="attributing-for-a-custom-markup-extension"></a>自定义标记扩展的特性化

若要支持设计环境和特定 XAML 对象编写器方案，应将标记扩展支持类型归于多个 CLR 特性。 这些特性报告预期标记扩展用法。

 <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute> 为 <xref:System.Type> 返回的对象类型报告 <xref:System.Windows.Markup.ArrayExtension.ProvideValue%2A> 信息。 <xref:System.Windows.Markup.ArrayExtension.ProvideValue%2A> 通过其纯签名返回 <xref:System.Object>。 但各种使用者可能需要更精确的返回类型信息。 这包括：

- 设计器和 IDE，可能能够为标记扩展用法提供可识别类型的支持。
- 目标类上的 `SetMarkupExtension` 处理程序的高级实现，可能依赖于反射来确定标记扩展的返回类型，而不是按名称在特定已知 <xref:System.Windows.Markup.MarkupExtension> 实现上进行分支。

## <a name="serialization-of-markup-extension-usages"></a>标记扩展用法的序列化

XAML 对象编写器处理标记扩展用法和调用 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>时，它以前作为标记扩展用法的上下文仍然保持在 XAML 节点流中，但不在对象图中。 在对象图中，仅保留值。 如果有设计方案或其他原因要将原始标记扩展用法保持到序列化输出中，则必须设计自己的基础结构，用于从加载路径 XAML 节点流跟踪标记扩展用法。 可以实现行为以从加载路径重新创建节点流的元素，并将它们播放回 XAML 编写器以在保存路径中进行序列化，从而取代节点流相应位置中的值。

## <a name="markup-extensions-in-the-xaml-node-stream"></a>XAML 节点流中的标记扩展

如果在加载路径上使用 XAML 节点流，则标记扩展用法会作为对象出现在节点流中。

如果标记扩展用法使用位置参数，则它会表示为具有初始化值的起始对象。 作为大致的文本表示形式，节点流类似于下面这样：

`StartObject` （<xref:System.Xaml.XamlType> 是标记扩展的定义类型，而不是其返回类型）

`StartMember` （ <xref:System.Xaml.XamlMember> 的名称是 `_InitializationText`)

`Value` （值是字符串形式的位置参数，包括中间分隔符）

`EndMember`

`EndObject`

具有命名参数的标记扩展用法会表示为具有相关名称成员的对象（各自使用文本字符串值进行设置）。

实际调用标记扩展的 `ProvideValue` 实现需要 XAML 架构上下文，因为这需要类型映射和创建标记扩展支持类型实例。 这是在默认的 .NET XAML 服务节点流中以这种方式保留标记扩展用法的一个原因-加载路径的读取器部分通常不提供必需的 XAML 架构上下文。

如果在保存路径上使用 XAML 节点流，则对象图表示形式中通常没有任何内容可告知要序列化的对象最初由标记扩展用法和 `ProvideValue` 结果提供。 需要保持标记扩展用法以进行往返，同时还捕获对象图中的其他更改的方案必须设计自己的方法，来保留原始 XAML 输入中有关标记扩展用法的信息。 例如，若要还原标记扩展用法，可能需要在保存路径上使用节点流才能还原标记扩展用法，或在原始 XAML 与往返 XAML 之间执行某种类型的合并。 某些 XAML 实现框架（如 WPF）使用中间类型（表达式）来帮助表示标记扩展用法提供值的情况。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Markup.MarkupExtension>
- [XAML 的类型转换器和标记扩展](type-converters-and-markup-extensions.md)
- [标记扩展和 WPF XAML](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
