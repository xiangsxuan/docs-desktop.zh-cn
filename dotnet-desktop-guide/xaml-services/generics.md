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
# <a name="generics-in-xaml"></a><span data-ttu-id="b8f9d-102">XAML 中的泛型</span><span class="sxs-lookup"><span data-stu-id="b8f9d-102">Generics in XAML</span></span>

<span data-ttu-id="b8f9d-103">中实现的 .NET XAML 服务为 <xref:System.Xaml?displayProperty=fullName> 使用泛型 CLR 类型提供支持。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-103">.NET XAML Services as implemented in <xref:System.Xaml?displayProperty=fullName> provides support for using generic CLR types.</span></span> <span data-ttu-id="b8f9d-104">此支持包括将泛型的约束指定为类型参数，并通过 `Add` 为泛型集合事例调用适当的方法来强制执行约束。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-104">This support includes specifying the constraints of generics as a type argument and enforcing the constraint by calling the appropriate `Add` method for generic collection cases.</span></span> <span data-ttu-id="b8f9d-105">本主题介绍在 XAML 中使用和引用泛型类型的各个方面。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-105">This topic describes aspects of using and referencing generic types in XAML.</span></span>

## <a name="xtypearguments"></a><span data-ttu-id="b8f9d-106">x：TypeArguments</span><span class="sxs-lookup"><span data-stu-id="b8f9d-106">x:TypeArguments</span></span>

<span data-ttu-id="b8f9d-107">`x:TypeArguments` 是由 XAML 语言定义的指令。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-107">`x:TypeArguments` is a directive defined by the XAML language.</span></span> <span data-ttu-id="b8f9d-108">当它用作泛型类型支持的 XAML 类型的成员时，会将 `x:TypeArguments` 泛型的约束类型参数传递到后备构造函数。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-108">When it is used as a member of a XAML type that is backed by a generic type, `x:TypeArguments` passes constraining type arguments of the generic to the backing constructor.</span></span> <span data-ttu-id="b8f9d-109">有关适用于的 .NET XAML 服务使用的引用语法 `x:TypeArguments` （包括语法示例），请参阅 [x:TypeArguments 指令](xtypearguments-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-109">For reference syntax that pertains to .NET XAML Services use of `x:TypeArguments`, which includes syntax examples, see [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

<span data-ttu-id="b8f9d-110">由于 `x:TypeArguments` 采用了一个字符串，并且具有类型转换器的支持，因此通常在 XAML 使用中将其声明为属性。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-110">Because `x:TypeArguments` takes a string, and has type converter backing, it is typically declared in XAML usage as an attribute.</span></span>

<span data-ttu-id="b8f9d-111">在 XAML 节点流中， `x:TypeArguments` 可以从 <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> 节点流中的位置获取由声明的信息 `StartObject` 。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-111">In the XAML node stream, the information declared by `x:TypeArguments` can be obtained from <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> at a `StartObject` position in the node stream.</span></span> <span data-ttu-id="b8f9d-112">的返回值 <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> 是一个 <xref:System.Xaml.XamlType> 值列表。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-112">The return value of <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> is a list of <xref:System.Xaml.XamlType> values.</span></span> <span data-ttu-id="b8f9d-113">通过调用来确定 XAML 类型是否表示泛型类型 <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-113">Determination of whether a XAML type represents a generic type can be made by calling <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.</span></span>

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a><span data-ttu-id="b8f9d-114">XAML 中泛型的规则和语法约定</span><span class="sxs-lookup"><span data-stu-id="b8f9d-114">Rules and Syntax Conventions for Generics in XAML</span></span>

<span data-ttu-id="b8f9d-115">在 XAML 中，泛型类型必须始终表示为约束泛型。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-115">In XAML, a generic type must always be represented as a constrained generic.</span></span> <span data-ttu-id="b8f9d-116">不受约束的泛型永远不会出现在 XAML 类型系统或 XAML 节点流中，也不能在 XAML 标记中表示。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-116">An unconstrained generic is never present in the XAML type system or a XAML node stream and cannot be represented in XAML markup.</span></span> <span data-ttu-id="b8f9d-117">在 XAML 特性语法中，可以引用泛型，这种情况下，它是所引用的泛型的嵌套类型约束 `x:TypeArguments` ，或者对于 `x:Type` 提供泛型类型的 CLR 类型引用的情况。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-117">A generic can be referenced within XAML attribute syntax for cases where it is a nested type constraint of a generic being referenced by `x:TypeArguments`, or for cases where `x:Type` supplies a CLR type reference for a generic type.</span></span> <span data-ttu-id="b8f9d-118">通过 <xref:System.Xaml.Schema.XamlTypeTypeConverter> .NET XAML 服务定义的类支持引用泛型。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-118">Referencing generics is supported through the <xref:System.Xaml.Schema.XamlTypeTypeConverter> class defined by .NET XAML Services.</span></span>

<span data-ttu-id="b8f9d-119">启用的 XAML 特性语法窗体 <xref:System.Xaml.Schema.XamlTypeTypeConverter> 改变了典型的 MSIL/CLR 语法约定，该约定将尖括号用于泛型的类型和约束，而不是用括号替换约束容器。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-119">The XAML attribute syntax form enabled by <xref:System.Xaml.Schema.XamlTypeTypeConverter> alters the typical MSIL / CLR syntax convention that uses angle brackets for types and constraints of generics, and instead substitutes parentheses for the constraint container.</span></span> <span data-ttu-id="b8f9d-120">有关示例，请参阅 [X:TypeArguments 指令](xtypearguments-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-120">For an example, see [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

## <a name="generics-and-xaml-2009-features"></a><span data-ttu-id="b8f9d-121">泛型和 XAML 2009 功能</span><span class="sxs-lookup"><span data-stu-id="b8f9d-121">Generics and XAML 2009 Features</span></span>

<span data-ttu-id="b8f9d-122">如果使用 XAML 2009 而不是映射 CLR 基类型来获取公共语言基元的 XAML 类型，则可以在中使用 [xaml 2009 内置类型](types-for-primitives.md) 作为信息项 `x:TypeArguments` 。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-122">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [XAML 2009 built-in types](types-for-primitives.md) as information items in `x:TypeArguments`.</span></span> <span data-ttu-id="b8f9d-123">例如，您可以声明以下 (前缀映射，但 `x` 它是 xaml 2009) 的 xaml 语言 xaml 命名空间：</span><span class="sxs-lookup"><span data-stu-id="b8f9d-123">For example, you could declare the following (prefix mappings not shown, but `x` is the XAML language XAML namespace for XAML 2009):</span></span>

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a><span data-ttu-id="b8f9d-124">WPF 中的泛型支持</span><span class="sxs-lookup"><span data-stu-id="b8f9d-124">Generics Support in WPF</span></span>

<span data-ttu-id="b8f9d-125">对于专用于 WPF 的 XAML 2006 用法， [](xclass-directive.md)还必须在与相同的元素上提供 x：Class `x:TypeArguments` ，并且该元素必须是 XAML 文档中的根元素。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-125">For XAML 2006 usage when specifically targeting WPF, [x:Class](xclass-directive.md) must also be provided on the same element as `x:TypeArguments`, and that element must be the root element in a XAML document.</span></span> <span data-ttu-id="b8f9d-126">根元素必须映射到至少具有一个类型参数的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-126">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="b8f9d-127">例如 <xref:System.Windows.Navigation.PageFunction%601>。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-127">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span>

<span data-ttu-id="b8f9d-128">支持泛型用法的可能的解决方法包括定义可返回泛型类型的自定义标记扩展，或提供从泛型类型派生的包装类定义，但在其自身的类定义中平展泛型约束。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-128">Possible workarounds to support generic usages include defining a custom markup extension that can return generic types, or providing a wrapping class definition that derives from a generic type but flattens the generic constraint in its own class definition.</span></span>

<span data-ttu-id="b8f9d-129">在 WPF 中，你可以将 XAML 2009 功能与一起使用 `x:TypeArguments` ，但仅适用于未进行标记编译) 的松散 xaml (xaml。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-129">In WPF you can use XAML 2009 features together with `x:TypeArguments`, but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="b8f9d-130">WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-130">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

<span data-ttu-id="b8f9d-131">.NET Framework 3.5 的 Windows Workflow Foundation 中的自定义工作流不支持泛型 XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="b8f9d-131">Custom workflows in Windows Workflow Foundation for .NET Framework 3.5 do not support generic XAML usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8f9d-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8f9d-132">See also</span></span>

- [<span data-ttu-id="b8f9d-133">x:TypeArguments 指令</span><span class="sxs-lookup"><span data-stu-id="b8f9d-133">x:TypeArguments Directive</span></span>](xtypearguments-directive.md)
- [<span data-ttu-id="b8f9d-134">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="b8f9d-134">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="b8f9d-135">常见 XAML 语言基元的内置类型</span><span class="sxs-lookup"><span data-stu-id="b8f9d-135">Built-in Types for Common XAML Language Primitives</span></span>](types-for-primitives.md)
