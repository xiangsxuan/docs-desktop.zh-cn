---
title: 默认 XAML 架构上下文和 WPF XAML 架构上下文
ms.date: 03/30/2017
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
ms.openlocfilehash: 2e92372de61230a98a02282cc28fc3f479cd94eb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974023"
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>默认 XAML 架构上下文和 WPF XAML 架构上下文
XAML 架构上下文是一种概念性实体，它限定了使用特定 XAML 词汇的 XAML 生产如何与对象写入行为交互，包括如何解析类型映射、如何加载程序集、如何解释某些读取器和编写器设置。 本主题介绍 .NET XAML 服务的功能和关联的默认 XAML 架构上下文，该上下文基于 CLR 类型系统。 本主题还介绍用于 WPF 的 XAML 架构上下文。

## <a name="default-xaml-schema-context"></a>默认 XAML 架构上下文

.NET XAML 服务都实现并使用默认 XAML 架构上下文。 默认 XAML 架构上下文行为并非始终在类的 API 中完全可见 <xref:System.Xaml.XamlSchemaContext> 。 但是，在许多情况下，默认 XAML 架构上下文影响的行为可通过 XAML 类型系统的公共 API （如或的成员） <xref:System.Xaml.XamlMember> <xref:System.Xaml.XamlType> 或使用默认 xaml 架构上下文的 xaml 读取器和 xaml 编写器中公开的 api 来观察。

可以 <xref:System.Xaml.XamlSchemaContext> 通过调用构造函数来创建封装默认行为的 <xref:System.Xaml.XamlSchemaContext> 。 这会显式创建默认的 XAML 架构上下文。 如果使用未显式采用输入参数的 Api 初始化 XAML 读取器或 XAML 编写器，则将隐式创建相同的默认 XAML 架构上下文 <xref:System.Xaml.XamlSchemaContext> 。

默认 XAML 架构上下文依赖 CLR 反射来实现其类型映射行为。 这包括检查定义 CLR 以及 <xref:System.Type> 相关的 <xref:System.Reflection.PropertyInfo> 或 <xref:System.Reflection.MethodInfo> 。 此外，还使用类型或成员上的 CLR 特性来填写使用 CLR 支持类型的 XAML 类型或 XAML 成员信息的详细信息。 默认 XAML 架构上下文不需要类型系统扩展技术（如 `Invoker` 模式），因为 CLR 类型系统中提供了必需的信息。

对于程序集加载逻辑，默认的 XAML 架构上下文主要依赖于 XAML 命名空间映射中提供的任何程序集值。 此外，还 <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> 可以提示要加载的程序集，对于诸如加载内部类型之类的方案。

## <a name="wpf-xaml-schema-context"></a>WPF XAML 架构上下文

本主题介绍了 WPF XAML 架构上下文，因为 WPF 实现提供了可通过实现非默认 XAML 架构上下文而引入的功能类型的有趣说明。 此外，在对 WPF XAML 进行寻址的 WPF 文档中，XAML 架构上下文概念并不太广泛地讨论;如果与默认 XAML 架构上下文的工作原理进行了集成，则 XAML 架构上下文启用的行为可能会完全理解。 WPF XAML 架构上下文实现以下行为。

**查找替代：** WPF 具有一些 XAML 内容模型，其中有一些 XAML 内容属性在未进行属性化的情况下运行 <xref:System.Windows.Markup.ContentPropertyAttribute> 。 <xref:System.Xaml.XamlType.LookupContentProperty%2A> WPF 的替代实现了此行为。

**延迟 WPF 表达式：** WPF 具有几个延迟某个值的表达式类，直至运行时上下文可用。 此外，模板扩展是依赖于延迟技术的运行时行为。

**类型系统查找优化：** WPF 具有广泛的 XAML 词汇和对象模型，包括继承到数百个 WPF 定义的类的基类成员定义。 而且，WPF 本身分散在多个程序集中。 WPF 使用查找表和其他方法优化其类型查找。 这为默认 XAML 架构上下文及其基于 CLR 的类型查找提供了性能改进。 如果查找表中不存在类型，则行为将使用类似于默认 XAML 架构上下文的 XAML 架构上下文技术。

**XamlType 和 XamlMember 扩展：** WPF 利用依赖属性扩展属性概念，并扩展带有路由事件的事件概念。 为了更好地为这些概念提供 XAML 处理操作的可见性，WPF 扩展 <xref:System.Xaml.XamlType> <xref:System.Xaml.XamlMember> 了和，并添加了报表依赖属性和路由事件特征的内部属性。

### <a name="accessing-the-wpf-xaml-schema-context"></a>访问 WPF XAML 架构上下文

如果你使用的是基于 WPF 或的 XAML 方法 <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType> ，则这些 xaml 读取器和 xaml 编写器实现已在使用 wpf XAML 架构上下文。

如果使用的是未使用 WPF XAML 架构上下文初始化的其他 XAML 读取器或 XAML 编写器实现，则可以从获取工作的 WPF XAML 架构上下文 <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType> 。 然后，可以将此值用作使用的其他 API 的初始化 <xref:System.Xaml.XamlSchemaContext> 。 例如，可以调用 <xref:System.Xaml.XamlXmlReader.%23ctor%2A> 初始化并传递 WPF XAML 架构上下文。 或者，您可以使用 XAML 类型系统操作的 WPF XAML 架构上下文。 这可能包括 <xref:System.Xaml.XamlType> 、或调用的构造初始化 <xref:System.Xaml.XamlMember> <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType> 。

请注意，如果从纯 XAML 节点流角度访问 WPF XAML 的某些方面，某些 WPF 框架功能可能尚未操作。 例如，控件的 WPF 模板尚未应用。 因此，如果您访问的属性在运行时可能使用完整的可视化树进行填充，则您可能只能看到引用模板的属性值。 如果在非运行时情况下提供给 WPF 标记扩展提供的服务上下文可能也不准确，并且在尝试编写对象图时可能会导致异常。

## <a name="xaml-and-assembly-loading"></a>XAML 和程序集加载

XAML 和 .NET XAML 服务的程序集加载与 CLR 定义的概念集成 <xref:System.AppDomain> 。 XAML 架构上下文解释如何在运行时或设计时加载程序集或查找类型，具体取决于 <xref:System.AppDomain> 和其他因素。 此逻辑略有不同，具体取决于 xaml 是否为 XAML 读取器的稀疏 XAML、是否通过 XAML 编译为 DLL `XamlBuildTask` ，或由 WPF 的生成的 BAML `PresentationBuildTask` 。

WPF 的 XAML 架构上下文与 WPF 应用程序模型集成，后者又使用 <xref:System.AppDomain> wpf 实现的详细信息和其他因素。

#### <a name="xaml-reader-input-loose-xaml"></a>XAML 读取器输入 (松散 XAML) 

01. XAML 架构上下文循环访问 <xref:System.AppDomain> 应用程序的，并从最近加载的程序集开始，查找与名称的所有方面相匹配的已加载程序集。 如果找到匹配项，则使用该程序集进行解析。

02. 否则，将使用基于 CLR API 的以下技术之一 <xref:System.Reflection.Assembly> 加载程序集：

    - 如果在映射中限定名称，请 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 对限定名称调用。

    - 如果前面的步骤失败，请使用短名称 (和公钥标记（如果) 存在）以调用 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 。

    - 如果名称在映射中不合格，请调用 <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> 。

#### <a name="xamlbuildtask"></a>XamlBuildTask

`XamlBuildTask` 用于 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation。

请注意，通过进行的程序集引用 `XamlBuildTask` 始终是完全限定的。

1. 对 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 限定名称调用。

2. 如果前面的步骤失败，请使用短名称 (和公钥标记（如果) 存在）以调用 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 。

#### <a name="baml-presentationbuildtask"></a>BAML (PresentationBuildTask) 

BAML 的程序集加载有两个方面：加载作为组件包含 BAML 的初始程序集，并为 BAML 生产所引用的任何类型加载支持类型的程序集。

##### <a name="assembly-load-for-initial-markup"></a>初始标记的程序集加载：

对从中加载标记的程序集的引用始终是非限定的。

1. WPF XAML 架构上下文遍历 <xref:System.AppDomain> wpf 应用程序的，并从最近加载的程序集开始，查找与名称的所有方面相匹配的已加载程序集。 如果找到匹配项，则使用该程序集进行解析。

2. 如果前面的步骤失败，请使用短名称 (和公钥标记（如果) 存在）以调用 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 。

##### <a name="assembly-references-by-baml-types"></a>BAML 类型的程序集引用：

BAML 生产中使用的类型的程序集引用始终是完全限定的，作为生成任务的输出。

01. WPF XAML 架构上下文遍历 <xref:System.AppDomain> wpf 应用程序的，并从最近加载的程序集开始，查找与名称的所有方面相匹配的已加载程序集。 如果找到匹配项，则使用该程序集进行解析。

02. 否则，将使用以下方法之一来加载程序集：

    - 对 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 限定名称调用。
  
    - 如果短名称 + 公钥标记组合与从其加载 BAML 的程序集相匹配，则使用该程序集。

    - 使用短名称 + 公钥标记调用 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 。

## <a name="see-also"></a>另请参阅

- [了解 XAML 节点流结构和概念](understanding-xaml-node-stream-structures-and-concepts.md)
