---
title: XAML 中的泛型
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9354f74b978652c36df28a91a6b9db5cfff4bb1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974018"
---
# <a name="generics-in-xaml"></a>XAML 中的泛型

中实现的 .NET XAML 服务为 <xref:System.Xaml?displayProperty=fullName> 使用泛型 CLR 类型提供支持。 此支持包括将泛型的约束指定为类型参数，并通过 `Add` 为泛型集合事例调用适当的方法来强制执行约束。 本主题介绍在 XAML 中使用和引用泛型类型的各个方面。

## <a name="xtypearguments"></a>x：TypeArguments

`x:TypeArguments` 是由 XAML 语言定义的指令。 当它用作泛型类型支持的 XAML 类型的成员时，会将 `x:TypeArguments` 泛型的约束类型参数传递到后备构造函数。 有关适用于的 .NET XAML 服务使用的引用语法 `x:TypeArguments` （包括语法示例），请参阅 [x:TypeArguments 指令](xtypearguments-directive.md)。

由于 `x:TypeArguments` 采用了一个字符串，并且具有类型转换器的支持，因此通常在 XAML 使用中将其声明为属性。

在 XAML 节点流中， `x:TypeArguments` 可以从 <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> 节点流中的位置获取由声明的信息 `StartObject` 。 的返回值 <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> 是一个 <xref:System.Xaml.XamlType> 值列表。 通过调用来确定 XAML 类型是否表示泛型类型 <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType> 。

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>XAML 中泛型的规则和语法约定

在 XAML 中，泛型类型必须始终表示为约束泛型。 不受约束的泛型永远不会出现在 XAML 类型系统或 XAML 节点流中，也不能在 XAML 标记中表示。 在 XAML 特性语法中，可以引用泛型，这种情况下，它是所引用的泛型的嵌套类型约束 `x:TypeArguments` ，或者对于 `x:Type` 提供泛型类型的 CLR 类型引用的情况。 通过 <xref:System.Xaml.Schema.XamlTypeTypeConverter> .NET XAML 服务定义的类支持引用泛型。

启用的 XAML 特性语法窗体 <xref:System.Xaml.Schema.XamlTypeTypeConverter> 改变了典型的 MSIL/CLR 语法约定，该约定将尖括号用于泛型的类型和约束，而不是用括号替换约束容器。 有关示例，请参阅 [X:TypeArguments 指令](xtypearguments-directive.md)。

## <a name="generics-and-xaml-2009-features"></a>泛型和 XAML 2009 功能

如果使用 XAML 2009 而不是映射 CLR 基类型来获取公共语言基元的 XAML 类型，则可以在中使用 [xaml 2009 内置类型](types-for-primitives.md) 作为信息项 `x:TypeArguments` 。 例如，您可以声明以下 (前缀映射，但 `x` 它是 xaml 2009) 的 xaml 语言 xaml 命名空间：

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a>WPF 中的泛型支持

对于专用于 WPF 的 XAML 2006 用法， [](xclass-directive.md)还必须在与相同的元素上提供 x：Class `x:TypeArguments` ，并且该元素必须是 XAML 文档中的根元素。 根元素必须映射到至少具有一个类型参数的泛型类型。 例如 <xref:System.Windows.Navigation.PageFunction%601>。

支持泛型用法的可能的解决方法包括定义可返回泛型类型的自定义标记扩展，或提供从泛型类型派生的包装类定义，但在其自身的类定义中平展泛型约束。

在 WPF 中，你可以将 XAML 2009 功能与一起使用 `x:TypeArguments` ，但仅适用于未进行标记编译) 的松散 xaml (xaml。 WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。

.NET Framework 3.5 的 Windows Workflow Foundation 中的自定义工作流不支持泛型 XAML 用法。

## <a name="see-also"></a>另请参阅

- [x:TypeArguments 指令](xtypearguments-directive.md)
- [x:Class 指令](xclass-directive.md)
- [常见 XAML 语言基元的内置类型](types-for-primitives.md)
