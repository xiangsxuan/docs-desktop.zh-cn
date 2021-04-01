---
title: TypeConverters 和 XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], TypeConverter class
ms.assetid: f6313e4d-e89d-497d-ac87-b43511a1ae4b
ms.openlocfilehash: caf218cc5eb2854ad51efbd321a8c42b8de0bb16
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974009"
---
# <a name="typeconverters-and-xaml"></a>TypeConverters 和 XAML
本主题介绍将从字符串进行的类型转换作为常规 XAML 语言功能的用途。 在 .NET Framework 中， <xref:System.ComponentModel.TypeConverter> 类将特定用途作为托管自定义类的实现的一部分提供，可用作 XAML 特性用法中的属性值。 如果你编写自定义类，并且希望类的实例可以用作 XAML 可设置属性值，则你可能需要将应用 <xref:System.ComponentModel.TypeConverterAttribute> 到你的类，编写自定义 <xref:System.ComponentModel.TypeConverter> 类，或同时使用这两者。  

## <a name="type-conversion-concepts"></a>类型转换概念  
  
### <a name="xaml-and-string-values"></a>XAML 和字符串值  
 在 XAML 文件中设置特性值时，该值的初始类型是纯文本形式的字符串。 甚至其他基元（如） <xref:System.Double> 最初是文本字符串到 XAML 处理器。  
  
 XAML 处理器需要两条信息来处理特性值。 第一条信息是所设置的属性的值类型。 定义特性值以及在 XAML 中进行处理的任何字符串都必须最终转换或解析为该类型的值。 如果值是 XAML 分析器可理解的基元（如数值），则会尝试直接转换字符串。 如果值是枚举，则字符串用于检查是否存在与该枚举中的命名常量匹配的名称。 如果值既不是分析器可理解的基元，也不是枚举，则所讨论的类型必须能够基于转换后的字符串提供类型的实例或值。 可通过指示类型转换器类达到此目的。 类型转换器实际上是提供其他类的值的帮助器类，可用于的 XAML 方案和 .NET 代码中的代码调用。  
  
### <a name="using-existing-type-conversion-behavior-in-xaml"></a>在 XAML 中使用现有的类型转换行为  
 你可能已经在基础应用程序 XAML 中使用了类型转换行为，只是你还不知道，具体取决于你对基础 XAML 概念的熟悉程度。 例如，WPF 定义了数百个采用类型值的属性 <xref:System.Windows.Point> 。 <xref:System.Windows.Point>是描述二维坐标空间中的坐标的值，它实际上只具有两个重要属性： <xref:System.Windows.Point.X%2A> 和 <xref:System.Windows.Point.Y%2A> 。 当您在 XAML 中指定一个点时，可以将其指定为带有分隔符的字符串 (通常是在提供的和值之间使用逗号) <xref:System.Windows.Point.X%2A> <xref:System.Windows.Point.Y%2A> 。 例如：`<LinearGradientBrush StartPoint="0,0" EndPoint="1,1"/>`。  
  
 甚至此简单类型的 <xref:System.Windows.Point> 和它在 XAML 中的简单用法都涉及类型转换器。 在这种情况下，为类 <xref:System.Windows.PointConverter> 。  
  
 <xref:System.Windows.Point>在类级别定义的类型转换器可简化所采用的所有属性的标记用法 <xref:System.Windows.Point> 。 如果没有类型转换器，那么对于前面显示的同一示例，将需要更冗长的标记，如下所示：  

```xaml
<LinearGradientBrush>
  <LinearGradientBrush.StartPoint>
    <Point X="0" Y="0"/>
  </LinearGradientBrush.StartPoint>
  <LinearGradientBrush.EndPoint>
    <Point X="1" Y="1"/>
  </LinearGradientBrush.EndPoint>
</LinearGradientBrush>
 ```
  
 使用类型转换字符串或使用更复杂的等效语法通常是编码风格的选择。 XAML 工具工作流也可能会影响值的设置方式。 某些 XAML 工具可能会生成最复杂的标记窗体，以便更容易往返于设计器视图或其自身的序列化机制。  
  
 通常可以在 WPF 和 .NET Framework 类型上发现现有类型转换器，方法是检查类 (或属性) 是否存在已应用的 <xref:System.ComponentModel.TypeConverterAttribute> 。 此属性将对支持类型转换器转换类型的值的类进行命名，用于 XAML 或其他可能的用途。  
  
### <a name="type-converters-and-markup-extensions"></a>类型转换器和标记扩展  
 标记扩展和类型转换器根据 XAML 处理器行为及其应用场景来实现正交角色。 尽管上下文可用于标记扩展用途，但通常不会在标记扩展实现中检查属性的类型转换行为（其中标记扩展提供了一个值）。 换言之，即使标记扩展返回一个文本字符串作为其 `ProvideValue` 输出，该字符串上应用于特定属性或属性值类型的类型转换行为也不会被调用。通常，标记扩展的目的是在不调用任何类型转换器的情况下，处理字符串和返回对象。  
  
 需要标记扩展而不是类型转换器的一种常见情况是使对已存在的对象进行引用。 无状态类型转换器最多只能生成新实例，这可能并不理想。 若要深入了解标记扩展，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
### <a name="native-type-converters"></a>本机类型转换器  
 在 XAML 分析器的 WPF 和 .NET XAML 实现中，某些特定类型具有本机类型转换处理，但在传统上可能不会将这些类型视为基元。 这种类型的一个示例是 <xref:System.DateTime>。 这种情况的原因取决于 .NET Framework 体系结构的工作原理：类型 <xref:System.DateTime> 在 mscorlib 中定义，这是 .net 中最基本的库。 <xref:System.DateTime> 不允许使用来自其他程序集的特性进行特性化，而该程序集引入了依赖项 (<xref:System.ComponentModel.TypeConverterAttribute> 来自系统) ，因此不能支持通过特性化进行的正常类型转换器发现机制。 相反，XAML 分析器具有需要此类本机处理的类型的列表，它可通过与真正基元的处理方式类似的方式来处理这些类型。 在这种情况下 (<xref:System.DateTime> 涉及调用 <xref:System.DateTime.Parse%2A> 。 )   
  
<a name="Implementing_a_Type_Converter"></a>
## <a name="implementing-a-type-converter"></a>实现类型转换器  
  
### <a name="typeconverter"></a>TypeConverter  
 在 <xref:System.Windows.Point> 前面给出的示例中， <xref:System.Windows.PointConverter> 提到了类。 对于 XAML 的 .NET 实现，用于 XAML 用途的所有类型转换器都是从基类派生的类 <xref:System.ComponentModel.TypeConverter> 。 <xref:System.ComponentModel.TypeConverter>类存在于 XAML 存在之前的 .NET Framework 版本中，它的原始用法之一是在可视化设计器中为属性对话框提供字符串转换。 对于 XAML，的角色 <xref:System.ComponentModel.TypeConverter> 会扩展为包括：作为字符串的基类和允许分析字符串属性值的字符串转换，并可能将特定对象属性的运行时值处理回字符串，以便作为属性进行序列化。  
  
 <xref:System.ComponentModel.TypeConverter> 定义了四个成员，它们与用于在 XAML 处理目的中转换为字符串和从字符串进行转换的成员相关：  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>  
  
 其中，最重要的方法是 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> 。 此方法将输入字符串转换为所需的对象类型。 严格地说， <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> 可以实现此方法以将范围更广泛的类型转换为转换器的预期目标类型，从而为超出 xaml （如支持运行时转换）的目的提供支持，但对于 xaml 而言，这只是可以处理 <xref:System.String> 重要输入的代码路径。  
  
 下一个最重要的方法是 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> 。 如果将应用程序转换为标记表示形式 (例如，如果它作为文件) 保存到 XAML， <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> 则负责生成标记表示形式。 在这种情况下，对 XAML 重要的代码路径是传递 `destinationType` 的 <xref:System.String> 。  
  
 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> 和 <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> 是在服务查询 <xref:System.ComponentModel.TypeConverter> 实现的功能时使用的支持方法。 必须实现这些方法以便为转换器的等效转换方法支持的特定于类型的情况返回 `true` 。 对于 XAML 用途，这通常意味着 <xref:System.String> 类型。  
  
### <a name="culture-information-and-type-converters-for-xaml"></a>XAML 的区域性信息和类型转换器  

 每个 <xref:System.ComponentModel.TypeConverter> 实现都可以对构成转换的有效字符串的内容进行自己的解释，还可以使用或忽略作为参数传递的类型说明。 对于区域性和 XAML 类型转换，有一个重要的注意事项。 XAML 完全支持使用可本地化的字符串作为特性值。 但不支持将该可本地化字符串用作具有特定区域性要求的类型转换器输入，因为 XAML 特性值的类型转换器包含一个必要的固定语言分析行为，该行为使用 `en-US` 区域性。 有关此限制的设计原因的详细信息，请参阅 XAML 语言规范 ([ \[ ms-chap \] ](https://download.microsoft.com/download/0/A/6/0A6F7755-9AF5-448B-907D-13985ACCF53E/[MS-XAML].pdf)。  
  
 区域性可能会产生问题的示例之一是，某些区域性使用逗号作为数字的小数点分隔符。 这将与许多 WPF XAML 类型转换器所具有的使用逗号作为分隔符的行为发生冲突（根据常用的 X,Y 形式等过去的先例，或逗号分隔的列表）。 即使在周围的 XAML 中传递区域性（将 `Language` 或 `xml:lang` 设置为 `sl-SI` 区域性，以此方式使用逗号作为小数点的区域性的一个示例）也不能解决此问题。  
  
### <a name="implementing-convertfrom"></a>实现 ConvertFrom  
 若要能够用作支持 XAML 的 <xref:System.ComponentModel.TypeConverter> 实现，该转换器的 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> 方法必须接受字符串作为 `value` 参数。 如果字符串采用有效格式，并且可以由实现进行转换 <xref:System.ComponentModel.TypeConverter> ，则返回的对象必须支持强制转换为属性所需的类型。 否则， <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> 实现必须返回 `null`。  
  
 每个 <xref:System.ComponentModel.TypeConverter> 实现都可以对构成转换的有效字符串的内容进行自己的解释，还可以使用或忽略作为参数传递的类型说明或区域性上下文。 但是，WPF XAML 处理可能不会在所有情况下都将值传递给类型说明上下文，还可能不会基于 `xml:lang` 传递区域性。  
  
> [!NOTE]
> 请勿使用大括号字符（尤其是 {）作为字符串格式的可能元素。 这些字符保留作为标记扩展序列的入口和出口。  
  
### <a name="implementing-convertto"></a>实现 ConvertTo  
 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> 可能用于序列化支持。 通过 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> 为自定义类型及其类型转换器实现的序列化支持不是绝对要求。 但是，如果要实现控件，或使用序列化作为类的功能或设计的一部分，则应实现 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>。  
  
 若要用作 <xref:System.ComponentModel.TypeConverter> 支持 XAML 的实现，该转换器的 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> 方法必须接受 (类型的实例，或接受作为参数) 支持的值 `value` 。 如果 `destinationType` 参数为类型 <xref:System.String> ，则返回的对象必须能够强制转换为 <xref:System.String> 。 返回字符串必须表示 `value` 的序列化值。 理想情况下，如果您选择的序列化格式应能够生成相同的值，则它应能够生成相同的值 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> ，而不会显著丢失信息。  
  
 如果值无法进行序列化，或转换器不支持序列化，则 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> 实现必须返回 `null` ，并且在此情况下允许引发异常。 但是，如果确实引发了异常，则应报告无法使用该转换作为实现的一部分， <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> 以便 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> 支持首先检查以避免异常的最佳做法。  
  
 如果 `destinationType` 参数不属于类型 <xref:System.String> ，则可以选择自己的转换器处理。 通常，会恢复为基实现处理，在方法中将 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> 引发特定异常。  
  
### <a name="implementing-canconvertto"></a>实现 CanConvertTo  
 对于 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> 类型的 `true` ， `destinationType` 实现应返回 <xref:System.String>，否则遵从基实现。  
  
### <a name="implementing-canconvertfrom"></a>实现 CanConvertFrom  
 对于 <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> 类型的 `true` ， `sourceType` 实现应返回 <xref:System.String>，否则遵从基实现。  
  
<a name="Applying_the_TypeConverterAttribute"></a>
## <a name="applying-the-typeconverterattribute"></a>应用 TypeConverterAttribute  
 为了使自定义类型转换器被 XAML 处理器用作自定义类的操作类型转换器，必须将应用于 <xref:System.ComponentModel.TypeConverterAttribute> 类定义。 通过特性指定的 <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A> 必须是自定义类型转换器的类型名。 应用此特性后，当 XAML 处理器处理属性类型使用自定义类类型的值时，它可以输入字符串并返回对象实例。  
  
 还可以基于每个属性提供类型转换器。 不是将应用于 <xref:System.ComponentModel.TypeConverterAttribute> 类定义，而是将其应用于主定义 (属性定义，而不是 `get` / `set`) 中的实现。 属性的类型必须与自定义类型转换器处理的类型匹配。 应用此特性时，当 XAML 处理器处理该属性的值时，它可以处理输入字符串并返回对象实例。 如果选择使用 Microsoft .NET 框架中的属性类型或不能控制类定义并且无法应用此类定义的其他库，则每属性类型转换器方法特别有用 <xref:System.ComponentModel.TypeConverterAttribute> 。  
  
## <a name="see-also"></a>请参阅

- <xref:System.ComponentModel.TypeConverter>
- [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
- [XAML 语法详述](xaml-syntax-in-detail.md)
