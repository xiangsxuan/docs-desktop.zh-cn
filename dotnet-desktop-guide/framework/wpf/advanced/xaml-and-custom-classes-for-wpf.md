---
title: XAML 和自定义类
ms.date: 03/30/2017
helpviewer_keywords:
- custom classes in XAML [WPF]
- XAML [WPF], custom classes
- classes [WPF], custom classes in XAML
ms.assetid: e7313137-581e-4a64-8453-d44e15a6164a
ms.openlocfilehash: 86d3c01e6080a0c6f4f7f7d687d70a074b9adc88
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667442"
---
# <a name="xaml-and-custom-classes-for-wpf"></a>XAML 及 WPF 的自定义类
在公共语言运行时中实现的 XAML (CLR) 框架支持在任何公共语言运行时 (CLR) 语言中定义自定义类或结构，然后使用 XAML 标记访问该类。 通常通过将自定义类型映射到 XAML 命名空间前缀，可在同一标记文件中混合使用 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 定义类型和自定义类型。 本主题讨论将自定义类用作 XAML 元素必须满足的要求。  

<a name="Custom_Classes_in_Applications_vs__in_Assemblies"></a>
## <a name="custom-classes-in-applications-or-assemblies"></a>应用程序或程序集中的自定义类  
 XAML 中使用的自定义类可通过两种不同的方式进行定义：在代码隐藏或其他生成主 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 应用程序的代码内，或者在单独程序集中作为类（例如用作类库的可执行文件或 DLL）。 这些方法各有特定的优点和缺点。  
  
- 创建类库的优点在于可在多个不同的应用程序间共享任意此类自定义类。 通过使用单独的库，更易于控制应用程序的版本控制问题，并可简化类创建过程，在此过程中，所需的类用法是作为 XAML 页面上的根元素。  
  
- 在应用程序中定义自定义类的优点在于此方法相对轻量，可减少在主应用程序可执行文件外引入单独程序集时遇到的部署和测试问题。  
  
- 无论定义在相同还是不同的程序集中，自定义类若要在 XAML 中用作元素，都需要在 CLR 命名空间和 XML 命名空间之间进行映射。 请参阅 [WPF XAML 的 XAML 命名空间和命名空间映射](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。  
  
<a name="Requirements_for_a_Custom_Class_as_a_XAML_Element"></a>
## <a name="requirements-for-a-custom-class-as-a-xaml-element"></a>将自定义类用作 XAML 元素的要求  
 为能够实例化为对象元素，类必须满足以下要求：  
  
- 自定义类必须是公共的且支持默认（无参数）公共构造函数。 （有关结构注释，请参阅下节内容。）  
  
- 自定义类不得为嵌套类。 嵌套类及其常规 CLR 使用语法中的“点”会干扰其他 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 和/或 XAML 功能（例如附加属性）。  
  
 除启用对象元素语法外，对象定义还会对任何其他将该对象作为值类型的公共属性启用属性元素语法。 这是因为对象现在可被实例化为对象元素，且可填充此类属性的属性元素值。  
  
### <a name="structures"></a>結構  
 你定义为自定义类型的结构始终能够在中的 XAML 中构造 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。这是因为 CLR 编译器会为结构隐式创建一个无参数的构造函数，该构造函数将所有属性值初始化为其默认值。 某些情况下，结构并不需要默认构造行为和/或对象元素用法。 这可能是因为结构需要通过概念方式将值和函数作为联合来填充，其中包含的值可能具有互斥的解释，因而其不存在任何可设置属性。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]此类结构的一个示例是 <xref:System.Windows.GridLength> 。 通常情况下，此类结构应实现类型转换器，以便可通过属性形式表达值，方法是使用创建结构值的不同解释或模式的字符串约定。 结构还应通过非参数构造函数公开代码构造的类似行为。  
  
<a name="Requirements_for_Properties_of_a_Custom_Class_as_XAML"></a>
## <a name="requirements-for-properties-of-a-custom-class-as-xaml-attributes"></a>将自定义类属性用作 XAML 特性的要求  
 属性必须引用按值类型 (例如基元) ，或使用具有可参数构造函数或 XAML 处理器可以访问的专用类型转换器的类型的类。 在 CLR XAML 实现中，XAML 处理器通过对语言基元的本机支持或通过应用 <xref:System.ComponentModel.TypeConverterAttribute> 到后备类型定义中的类型或成员查找此类转换器  
  
 或者，属性可引用抽象类类型或接口。 对于抽象类或接口，XAML 分析的所需条件是必须用实现接口的实际类实例或派生自抽象类的类型实例填充属性值。  
  
 属性可在抽象类上声明，但仅可在派生自抽象类的实际类上设置。 这是因为，为类创建对象元素根本需要类的公共无参数构造函数。  
  
### <a name="typeconverter-enabled-attribute-syntax"></a>启用 TypeConverter 的特性语法  
 如果提供类级别的专用特性化类型转换器，则应用的类型转换会对需实例化该类型的任何属性启用特性语法。 类型转换器不启用类型的对象元素用法;只有该类型的无参数构造函数才会启用对象元素用法。 因此，启用类型转换器的属性通常不适用于属性语法，除非类型本身也支持对象元素语法。 此规则存在一个例外，即可指定属性元素语法，但使属性元素包含一个字符串。 这种用法实质上相当于属性语法用法，因此，这种用法并不常见，除非需要对特性值进行更可靠的空白处理。 例如，以下是一个采用字符串的属性元素用法以及一个特性用法等效项：  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe)]  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe2)]  
  
 允许使用特性语法的属性的示例，但不允许通过 XAML 使用包含对象元素的属性元素语法，这是采用类型的各种属性 <xref:System.Windows.Input.Cursor> 。 <xref:System.Windows.Input.Cursor>类具有专用的类型转换器 <xref:System.Windows.Input.CursorConverter> ，但不公开无参数构造函数，因此， <xref:System.Windows.FrameworkElement.Cursor%2A> 只能通过特性语法来设置属性，即使实际 <xref:System.Windows.Input.Cursor> 类型是引用类型。  
  
### <a name="per-property-type-converters"></a>按属性类型转换器  
 或者，属性本身可能声明属性级别的类型转换器。 这将启用 "微型语言"，它通过将属性的传入字符串值作为基于适当类型的操作的输入处理，来实例化内联属性类型的对象 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> 。 此操作的目的通常是提供方便的访问器，且这不是在 XAML 中启用属性设置的唯一方式。 但是，也可以将类型转换器用于要使用不提供无参数构造函数或特性化类型转换器的现有 CLR 类型的特性。 API 中的示例 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 是采用类型的某些属性 <xref:System.Globalization.CultureInfo> 。 在这种情况下， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 使用现有的 Microsoft .NET 框架 <xref:System.Globalization.CultureInfo> 类型可以更好地解决在早期版本的框架中使用的兼容性和迁移方案，但该 <xref:System.Globalization.CultureInfo> 类型不支持作为 XAML 属性值直接使用所需的构造函数或类型级别类型转换。  
  
 每当公开具有 XAML 用法的属性时，特别是对于控件作者，应特别考虑使用依赖属性支持此属性。 如果你使用 XAML 处理器的现有实现，则这一点尤其重要 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] ，因为你可以使用后备来提高性能 <xref:System.Windows.DependencyProperty> 。 依赖属性将对用户针对 XAML 可访问属性所需的属性公开属性系统功能。 这包括动画、数据绑定和样式支持等功能。 有关详细信息，请参阅[自定义依赖属性](custom-dependency-properties.md)和 [XAML 加载和依赖属性](xaml-loading-and-dependency-properties.md)。  
  
### <a name="writing-and-attributing-a-type-converter"></a>编写和特性化类型转换器  
 偶尔需要编写自定义 <xref:System.ComponentModel.TypeConverter> 派生类，以便为属性类型提供类型转换。 有关如何从派生并创建可支持 XAML 用法的类型转换器以及如何应用的说明， <xref:System.ComponentModel.TypeConverterAttribute> 请参阅 [TYPECONVERTERS 和 XAML](typeconverters-and-xaml.md)。  
  
<a name="Requirements_for_Events_of_a_Custom_Class_as_XAML"></a>
## <a name="requirements-for-xaml-event-handler-attribute-syntax-on-events-of-a-custom-class"></a>自定义类事件上 XAML 事件处理程序特性语法的要求  
 若要用作 CLR 事件，事件必须作为支持无参数构造函数的类上的公共事件公开，或在可在派生类上访问事件的抽象类上公开。 为了方便地用作路由事件，CLR 事件应该实现显式 `add` 和 `remove` 方法，这些方法可为 CLR 事件签名添加和删除处理程序，并将这些处理程序转发给 <xref:System.Windows.UIElement.AddHandler%2A> 和 <xref:System.Windows.UIElement.RemoveHandler%2A> 方法。 这些方法添加或删除事件所附加到的实例上的路由事件处理程序存储的处理程序。  
  
> [!NOTE]
> 可以使用为路由事件直接注册处理程序 <xref:System.Windows.UIElement.AddHandler%2A> ，并特意不定义公开路由事件的 CLR 事件。 通常不建议采用此操作，因为事件不会启用 XAML 特性语法用于附加处理程序，并且生成类提供的类型功能的 XAML 视图透明度较低。  
  
<a name="Collection_Properties"></a>
## <a name="writing-collection-properties"></a>编写集合属性  
 采用集合类型的属性所具有的 XAML 语法使你可指定添加到集合的对象。 此语法具有两个重要功能。  
  
- 无需在对象元素语法中指定作为集合对象的对象。 无论何时在采用集合类型的 XAML 中指定属性，该集合类型的状态总是隐式。  
  
- 标记中集合属性的子元素经处理后变成集合的成员。 对集合成员的代码访问通常通过列表/字典方法（例如 `Add`）或通过索引器执行。 但是，XAML 语法不支持方法和索引器（例外：XAML 2009 可支持这些方法，但使用 XAML 2009 会限制可能的 WPF 用法；请参阅 [XAML 2009 语言功能](/dotnet/desktop-wpf/xaml-services/xaml-2009-language-features)）。 对生成元素树而言，集合显然是非常常见的要求，并且你需要某种方法来填充声明 XAML 中的这些集合。 因此，通过将集合属性的子元素添加到作为集合属性类型值的集合中来对其进行处理。  
  
 .NET Framework XAML 服务实现和 WPF XAML 处理器将以下定义用于组成集合属性的项。 属性的属性类型必须实现以下项之一：  
  
- 实现 <xref:System.Collections.IList>。  
  
- 实现 <xref:System.Collections.IDictionary> 或泛型等效 (<xref:System.Collections.Generic.IDictionary%602>) 。  
  
- 派生自 <xref:System.Array> (有关 XAML 中数组的详细信息，请参阅 [X:Array 标记扩展](/dotnet/desktop-wpf/xaml-services/xarray-markup-extension)。 )   
  
- 实现 <xref:System.Windows.Markup.IAddChild> () 定义的接口 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
 CLR 中这些类型每个都具有 `Add` 方法，创建对象图时，XAML 处理器使用该方法将项添加到基础集合。  
  
> [!NOTE]
> `List` `Dictionary` <xref:System.Collections.Generic.IList%601> <xref:System.Collections.Generic.IDictionary%602> XAML 处理器不支持对泛型和接口 (和) 进行集合检测 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 但是，可以将 <xref:System.Collections.Generic.List%601> 类用作基类，因为它 <xref:System.Collections.IList> 直接实现或 <xref:System.Collections.Generic.Dictionary%602> 作为基类，因为它 <xref:System.Collections.IDictionary> 直接实现。  
  
 声明采用集合的属性时，请注意类型的新实例中如何实例化此属性值。 如果不将此属性实现为依赖属性，则使属性使用调用此集合类型构造函数的支持字段已可满足使用需求。 如果属性为依赖属性，则可能需要将集合属性初始化为默认类型构造函数的一部分。 这是因为依赖属性从元数据获取其默认值，而通常不希望集合属性的初始值为静态共享集合。 每个包含类型实例应具有一个集合实例。 有关详细信息，请参阅[自定义依赖属性](custom-dependency-properties.md)。  
  
 可为集合属性实现自定义集合类型。 由于隐式集合属性处理，自定义集合类型不需要提供无参数的构造函数即可在 XAML 中隐式使用。 但是，您可以选择为集合类型提供无参数的构造函数。 此做法是有用的。 除非提供无参数的构造函数，否则不能将集合显式声明为对象元素。 一些标记作者可能希望看到作为标记样式的显式集合。 此外，在创建将集合类型用作属性值的新对象时，无参数构造函数可以简化初始化要求。  
  
<a name="XAMLCONtent"></a>
## <a name="declaring-xaml-content-properties"></a>声明 XAML 内容属性  
 XAML 语言定义 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 内容属性的概念。 对象语法中可用的每个类仅可具有一个 XAML 内容属性。 若要将属性声明为类的 XAML 内容属性，请将 <xref:System.Windows.Markup.ContentPropertyAttribute> 作为类定义的一部分。 将预期 XAML 内容属性的名称指定为 <xref:System.Windows.Markup.ContentPropertyAttribute.Name%2A> 属性中的。 属性按名称指定为字符串，而不是作为反射构造（如）指定 <xref:System.Reflection.PropertyInfo> 。  
  
 可将集合属性指定为 XAML 内容属性。 这产生一种属性的用法，通过此用法，对象元素可具有一个或多个子元素，不干扰集合对象元素或属性元素标记。 这些元素被视为 XAML 内容属性的值，并添加到支持集合实例中。  
  
 一些现有 XAML 内容属性使用 `Object` 的属性类型。 这将启用 XAML 内容属性，该属性可以采用基元值（如）， <xref:System.String> 也可以采用单个引用对象值。 如果按照此模型，类型负责类型确定以及处理可能的类型。 内容类型的典型原因 <xref:System.Object> 是为了支持将对象内容添加为字符串 (的简单方法，该方法可接收默认的演示处理) ，或者添加对象内容（用于指定非默认的演示文稿或其他数据）的高级方法。  
  
<a name="Serializing"></a>
## <a name="serializing-xaml"></a>序列化 XAML  
 某些情况下（例如对于控件作者），可能还需要确保任何可在 XAML 中实例化的对象演示文稿也可被序列化到等效的 XAML 标记。 本主题中未介绍序列化要求。 请参阅[控件创作概述](../controls/control-authoring-overview.md)和[元素树和序列化](element-tree-and-serialization.md)。  
  
## <a name="see-also"></a>请参阅

- [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)
- [自定义依赖项属性](custom-dependency-properties.md)
- [控件创作概述](../controls/control-authoring-overview.md)
- [基元素概述](base-elements-overview.md)
- [XAML 加载和依赖项属性](xaml-loading-and-dependency-properties.md)
