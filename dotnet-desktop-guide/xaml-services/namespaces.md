---
title: .NET XAML 服务的 XAML 命名空间
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: 2ae57d08fade85c59fea2a54b653a2f775b57415
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972871"
---
# <a name="xaml-namespaces-for-net-xaml-services"></a>.NET XAML 服务的 XAML 命名空间
XAML 命名空间是扩展 XML 命名空间的定义的概念。 与 XML 命名空间类似，你可以在标记中使用特性定义 XAML 命名空间 `xmlns` 。 Xaml 命名空间还在 XAML 节点流和其他 XAML 服务 Api 中表示。 本主题定义了 XAML 命名空间概念，并介绍了 xaml 命名空间的定义，以及 XAML 架构上下文和 .NET XAML 服务的其他方面的使用方法。  
  
## <a name="xml-namespace-and-xaml-namespace"></a>XML 命名空间和 XAML 命名空间  
 XAML 命名空间是专用 XML 命名空间，正如 XAML 是一种专用形式的 XML，并为其标记使用基本 XML 窗体。 在标记中，可通过应用于元素的特性声明 XAML 命名空间及其映射 `xmlns` 。 `xmlns`声明可以对在其中声明 XAML 命名空间的相同元素进行。 对元素所做的 XAML 命名空间声明对该元素、该元素的所有属性以及该元素的所有子级都有效。 特性可以使用与包含特性的元素不同的 XAML 命名空间，只要特性名称本身在标记中引用前缀作为其特性名称的一部分。  
  
 XAML 命名空间与 XML 命名空间的区别在于，XML 命名空间可用于引用架构或只是区分实体。 对于 XAML，XAML 中使用的类型和成员最终必须解析为支持类型，并且 XML 架构概念不适用于此功能。 XAML 命名空间包含 XAML 架构上下文必须提供的信息，以便执行此类型映射。  
  
## <a name="xaml-namespace-components"></a>XAML 命名空间组件  
 XAML 命名空间定义包含两个组件：前缀和标识符。 如果在标记中声明了 XAML 命名空间，或在 XAML 类型系统中定义了该命名空间，则会出现上述每个组件。  
  
 前缀可以是 [XML 1.0 规范中 W3C 命名空间](https://www.w3.org/TR/REC-xml-names/)允许的任意字符串。 按照约定，前缀通常是短字符串，因为前缀在典型的标记文件中重复多次。 打算在多个 XAML 实现中使用的某些 XAML 命名空间使用特定的传统前缀。 例如，通常使用前缀映射 XAML 语言 XAML 命名空间 `x` 。 您可以定义默认的 XAML 命名空间，其中不在定义中提供前缀，而是在定义或查询 by.NET XAML 服务 API 时表示为空字符串。 通常，特意选择默认的 XAML 命名空间，以便通过 XAML 实现技术及其方案和词汇来提升最大的前缀省略标记量。  
  
 标识符可以是 [XML 1.0 规范中 W3C 命名空间](https://www.w3.org/TR/REC-xml-names/)允许的任意字符串。 按照约定，XML 命名空间或 XAML 命名空间的标识符通常以 URI 形式提供，通常作为协议限定的绝对 URI。 通常，定义特定 XAML 词汇的版本信息隐含为路径字符串的一部分。 XAML 命名空间添加了除 XML URI 约定以外的其他标识符约定。 对于 XAML 命名空间，标识符会传达 XAML 架构上下文所需的信息，以便解析指定为该 XAML 命名空间下的元素的类型，或解析成员的属性。  
  
 为了将信息传递到 XAML 架构上下文，XAML 命名空间的标识符可能仍以 URI 形式提供。 但是，在这种情况下，URI 也被声明为特定程序集或程序集列表中的匹配标识符。 这是通过使用对程序集进行特性化来在程序集中实现的 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 。 .NET XAML 服务中的默认 XAML 架构上下文在属性化程序集中标识 XAML 命名空间并支持基于 CLR 的类型解析行为的这种方法。 更常见的情况是，在 XAML 架构上下文包含 CLR 或基于默认 XAML 架构上下文的情况下使用此约定，这对于从 CLR 程序集读取 CLR 属性是必需的。  
  
 XAML 命名空间还可以通过与 CLR 命名空间和类型定义程序集通信的约定进行标识。 如果包含类型的程序集中不存在任何归属，则使用此约定 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 。 此约定可能比 URI 约定更复杂，而且还可能存在歧义和重复，因为有多种方法可以引用程序集。  
  
 使用 CLR 命名空间和程序集约定的标识符的最基本形式如下：  
  
 `clr-namespace:clrnsName; assembly=assemblyShortName`
  
 `clr-namespace:` 和 `; assembly=` 是语法的文本组件。  
  
 *clrnsName* 是标识 CLR 命名空间的字符串名称。 此字符串名称包含 ( ) 的任何内部点字符，这些字符提供有关 CLR 命名空间及其与其他 CLR 命名空间的关系的提示。
  
 *assemblyShortName* 是定义在 XAML 中有用的类型的程序集的字符串名称。 要通过声明的 XAML 命名空间访问的类型应由程序集定义，并在由 *clrnsName* 指定的 CLR 命名空间中声明。 此字符串名称通常类似于所报告的信息 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> 。  
  
 CLR 命名空间和程序集约定的更完整定义如下所示：  
  
 `clr-namespace:clrnsName; assembly=assemblyName`
  
 *assemblyName* 表示作为输入合法的任何字符串 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 。 此字符串可以包含区域性、公钥或版本信息 (这些概念的定义是在) 的参考主题中定义的 <xref:System.Reflection.Assembly> 。 其他) 重载使用的 COFF 格式和证据 (与 <xref:System.Reflection.Assembly.Load%2A> XAML 程序集加载目的无关; 所有加载信息必须以字符串形式提供。  
  
 为程序集指定公钥是一种适用于 XAML 安全性的有用技术，或者用于删除在使用简单名称加载程序集或在缓存或应用程序域中预先存在的可能存在的多义性。 有关详细信息，请参阅 [XAML 安全注意事项](security-considerations.md)。  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>XAML 服务 API 中的 XAML 命名空间声明  
 在 XAML 服务 API 中，XAML 命名空间声明由 <xref:System.Xaml.NamespaceDeclaration> 对象表示。 如果在代码中声明 XAML 命名空间，则调用 <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> 构造函数。 `ns`和 `prefix` 参数指定为字符串，为这些参数提供的输入对应于本主题前面所述的 xaml 命名空间标识符和 xaml 命名空间前缀的定义。  
  
 如果要将 XAML 命名空间信息作为 XAML 节点流的一部分进行检查，或者通过其他方式访问 XAML 类型系统，则会 <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> 报告 xaml 命名空间标识符，并 <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> 报告 xaml 命名空间前缀。  
  
 在 XAML 节点流中，XAML 命名空间信息可以作为 XAML 节点出现在它所应用到的实体之前。 这包括 XAML 命名空间信息位于 XAML 根元素的之前的情况 `StartObject` 。 有关更多信息，请参见 [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md)。  
  
 对于许多使用 .NET XAML 服务 API 的方案，至少应有一个 XAML 命名空间声明，并且声明必须包含或引用 XAML 架构上下文所需的信息。 XAML 命名空间必须指定要加载的程序集，或帮助解析命名空间和 XAML 架构上下文已经加载或已知的程序集中的特定类型。  
  
 为了生成 XAML 节点流，XAML 类型信息必须可用于 XAML 架构上下文。 如果没有首先为要创建的每个节点确定相关的 XAML 命名空间，则无法确定 XAML 类型信息。 此时，尚未创建类型的实例，但 XAML 架构上下文可能需要从定义程序集和后备类型中查找信息。 例如，为了处理标记 `<Party><PartyFavor/></Party>` ，XAML 架构上下文必须能够确定的的名称和类型 `ContentProperty` `Party` ，因此还必须知道和的 XAML 命名空间信息 `Party` `PartyFavor` 。 对于默认的 XAML 架构上下文，静态反射会报告许多 XAML 类型系统信息，需要在节点流中生成 XAML 类型节点。  
  
 为了从 XAML 节点流生成对象图，XAML 命名空间声明必须存在于原始标记中使用的每个 XAML 前缀，并记录在 XAML 节点流中。 此时，将创建实例，并发生 true 类型映射行为。  
  
 如果您需要预填充 XAML 命名空间信息，则在您打算使用 XAML 架构上下文的 XAML 命名空间未在标记中定义时，可以使用的一种方法是在中声明的 XML 命名空间声明 <xref:System.Xml.XmlParserContext> <xref:System.Xml.XmlReader> 。 然后，将 <xref:System.Xml.XmlReader> 其用作 XAML 读取器构造函数的输入，或 <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType> 。  
  
 .NET XAML 服务中与 XAML 命名空间处理相关的两个其他 Api 是特性 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 和 <xref:System.Windows.Markup.XmlnsPrefixAttribute> 。 这些属性适用于程序集。 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 由 XAML 架构上下文用来解释包含 URI 的任何 XAML 命名空间声明。 <xref:System.Windows.Markup.XmlnsPrefixAttribute> 由发出 XAML 的工具使用，以便可以使用可预测的前缀序列化特定的 XAML 命名空间。 有关详细信息，请参阅 [自定义类型和库的 XAML 相关 CLR 特性](clr-attributes-with-custom-types-and-libraries.md)。  
  
## <a name="see-also"></a>另请参阅

- [了解 XAML 节点流结构和概念](understanding-xaml-node-stream-structures-and-concepts.md)
