---
title: x:Type 标记扩展
description: 介绍如何在 XAML 中使用 x:Type 标记扩展。 X:Type 标记扩展指定 CLR 对象。
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: 73b45d8c8ec10c133549755492663dcab1b2c454
ms.sourcegitcommit: 32616f61a7b001efcc8567fee5fdf01f83da76cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "107560165"
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="5a948-104">x:Type 标记扩展</span><span class="sxs-lookup"><span data-stu-id="5a948-104">x:Type Markup Extension</span></span>

<span data-ttu-id="5a948-105">提供作为 <xref:System.Type> 指定 XAML 类型的基础类型的 CLR 对象。</span><span class="sxs-lookup"><span data-stu-id="5a948-105">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="5a948-106">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="5a948-106">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Type prefix:typeNameValue}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="5a948-107">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="5a948-107">XAML Object Element Usage</span></span>

```xaml
<x:Type TypeName="prefix:typeNameValue"/>
```

## <a name="xaml-values"></a><span data-ttu-id="5a948-108">XAML 值</span><span class="sxs-lookup"><span data-stu-id="5a948-108">XAML Values</span></span>

| <span data-ttu-id="5a948-109">值</span><span class="sxs-lookup"><span data-stu-id="5a948-109">Value</span></span> | <span data-ttu-id="5a948-110">说明</span><span class="sxs-lookup"><span data-stu-id="5a948-110">Description</span></span> |
|-|-|
|`prefix`|<span data-ttu-id="5a948-111">可选。</span><span class="sxs-lookup"><span data-stu-id="5a948-111">Optional.</span></span> <span data-ttu-id="5a948-112">映射非默认 XAML 命名空间的前缀。</span><span class="sxs-lookup"><span data-stu-id="5a948-112">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="5a948-113">通常不需要指定前缀。</span><span class="sxs-lookup"><span data-stu-id="5a948-113">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="5a948-114">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="5a948-114">See Remarks.</span></span>|
|`typeNameValue`|<span data-ttu-id="5a948-115">必需。</span><span class="sxs-lookup"><span data-stu-id="5a948-115">Required.</span></span> <span data-ttu-id="5a948-116">可解析为当前默认 XAML 命名空间的类型名称;如果提供，则为指定的映射前缀 `prefix` 。</span><span class="sxs-lookup"><span data-stu-id="5a948-116">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5a948-117">注解</span><span class="sxs-lookup"><span data-stu-id="5a948-117">Remarks</span></span>

<span data-ttu-id="5a948-118">`x:Type`标记扩展的函数与 `typeof()` c # 中的运算符或 `GetType` Microsoft Visual Basic 中的运算符类似。</span><span class="sxs-lookup"><span data-stu-id="5a948-118">The `x:Type` markup extension has a similar function to the `typeof()` operator in C# or the `GetType` operator in Microsoft Visual Basic.</span></span>

<span data-ttu-id="5a948-119">`x:Type`标记扩展为采用该类型的属性提供 from 字符串转换行为 <xref:System.Type> 。</span><span class="sxs-lookup"><span data-stu-id="5a948-119">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="5a948-120">输入为 XAML 类型。</span><span class="sxs-lookup"><span data-stu-id="5a948-120">The input is a XAML type.</span></span> <span data-ttu-id="5a948-121">输入 XAML 类型和输出 CLR 之间的关系 <xref:System.Type> 是 <xref:System.Type> <xref:System.Xaml.XamlType.UnderlyingType%2A> <xref:System.Xaml.XamlType> ， <xref:System.Xaml.XamlType> 在根据 XAML 架构上下文和上下文提供的服务查找必需的后，输出为输入的 <xref:System.Windows.Markup.IXamlTypeResolver> 。</span><span class="sxs-lookup"><span data-stu-id="5a948-121">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="5a948-122">在 .NET XAML 服务中，对此标记扩展的处理由类定义 <xref:System.Windows.Markup.TypeExtension> 。</span><span class="sxs-lookup"><span data-stu-id="5a948-122">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>

<span data-ttu-id="5a948-123">在特定的框架实现中，一些 <xref:System.Type> 作为值使用的属性可以直接接受 (类型) 的字符串值的类型名称 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="5a948-123">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="5a948-124">但是，实现此行为是一种复杂的方案。</span><span class="sxs-lookup"><span data-stu-id="5a948-124">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="5a948-125">有关示例，请参阅后面的 "WPF 用法说明" 部分。</span><span class="sxs-lookup"><span data-stu-id="5a948-125">For examples, see the "WPF Usage Notes" section that follows.</span></span>

<span data-ttu-id="5a948-126">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="5a948-126">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="5a948-127">在 `x:Type` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 扩展类的 <xref:System.Windows.Markup.TypeExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="5a948-127">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="5a948-128">在基于 CLR 类型的 .NET XAML 服务的默认 XAML 架构上下文下，此特性的值是 <xref:System.Reflection.MemberInfo.Name%2A> 所需类型的，或者包含 <xref:System.Reflection.MemberInfo.Name%2A> 前面带有非默认 XAML 命名空间映射前缀的。</span><span class="sxs-lookup"><span data-stu-id="5a948-128">Under the default XAML schema context for .NET XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>

<span data-ttu-id="5a948-129">`x:Type`标记扩展可用于对象元素语法。</span><span class="sxs-lookup"><span data-stu-id="5a948-129">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="5a948-130">在这种情况下，需要指定属性的值 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 才能正确地初始化扩展。</span><span class="sxs-lookup"><span data-stu-id="5a948-130">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>

<span data-ttu-id="5a948-131">`x:Type`标记扩展还可用作详细特性; 但这种用法并不典型：`<object property="{x:Type TypeName=typeNameValue}" .../>`</span><span class="sxs-lookup"><span data-stu-id="5a948-131">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<object property="{x:Type TypeName=typeNameValue}" .../>`</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="5a948-132">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="5a948-132">WPF Usage Notes</span></span>

### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="5a948-133">默认 XAML 命名空间和类型映射</span><span class="sxs-lookup"><span data-stu-id="5a948-133">Default XAML Namespace and Type Mapping</span></span>

<span data-ttu-id="5a948-134">WPF 编程的默认 XAML 命名空间包含典型 XAML 方案所需的大多数 XAML 类型;因此，在引用 XAML 类型值时，通常可以避免前缀。</span><span class="sxs-lookup"><span data-stu-id="5a948-134">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="5a948-135">如果引用的是自定义程序集的类型或存在于 WPF 程序集中的类型，但却来自未映射到默认 XAML 命名空间的 CLR 命名空间，则可能需要映射前缀。</span><span class="sxs-lookup"><span data-stu-id="5a948-135">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="5a948-136">有关前缀、XAML 命名空间和映射 CLR 命名空间的详细信息，请参阅 [WPF xaml 的 XAML 命名空间和命名空间映射](../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="5a948-136">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>

### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="5a948-137">支持类型为字符串的类型属性</span><span class="sxs-lookup"><span data-stu-id="5a948-137">Type Properties That Support Typename-as-String</span></span>

<span data-ttu-id="5a948-138">WPF 支持用于指定类型的某些属性的值的方法， <xref:System.Type> 无需 `x:Type` 使用标记扩展用法。</span><span class="sxs-lookup"><span data-stu-id="5a948-138">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="5a948-139">相反，你可以将值指定为命名类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="5a948-139">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="5a948-140">这是和的 <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> 示例 <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="5a948-140">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5a948-141">不通过类型转换器或标记扩展提供对此行为的支持。</span><span class="sxs-lookup"><span data-stu-id="5a948-141">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="5a948-142">相反，这是通过实现的延迟行为 <xref:System.Windows.FrameworkElementFactory> 。</span><span class="sxs-lookup"><span data-stu-id="5a948-142">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>

<span data-ttu-id="5a948-143">Silverlight 支持类似的约定。</span><span class="sxs-lookup"><span data-stu-id="5a948-143">Silverlight supports a similar convention.</span></span> <span data-ttu-id="5a948-144">事实上，Silverlight 目前不支持 `{x:Type}` 其 XAML 语言支持，并且不接受 `{x:Type}` 旨在支持 WPF-Silverlight XAML 迁移的少数情况下的用法。</span><span class="sxs-lookup"><span data-stu-id="5a948-144">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="5a948-145">因此，类型即字符串行为内置于所有 Silverlight 本机属性评估中，其中 a <xref:System.Type> 是值。</span><span class="sxs-lookup"><span data-stu-id="5a948-145">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>

## <a name="xaml-2009"></a><span data-ttu-id="5a948-146">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="5a948-146">XAML 2009</span></span>

<span data-ttu-id="5a948-147">XAML 2009 提供对泛型类型的其他支持，并修改和的功能行为 `x:TypeArguments` `x:Type` 以提供此支持。</span><span class="sxs-lookup"><span data-stu-id="5a948-147">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>

- <span data-ttu-id="5a948-148">`x:TypeArguments` 与泛型对象实例化关联的对象元素可以位于根以外的元素上。</span><span class="sxs-lookup"><span data-stu-id="5a948-148">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="5a948-149">有关详细信息，请参阅 [X:TypeArguments 指令](xtypearguments-directive.md)的 "XAML 2009" 一节。</span><span class="sxs-lookup"><span data-stu-id="5a948-149">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

- <span data-ttu-id="5a948-150">XAML 2009 支持用于在标记中指定泛型类型的约束的语法。</span><span class="sxs-lookup"><span data-stu-id="5a948-150">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="5a948-151">这可以由 `x:TypeArguments` 、通过 `x:Type` 或两个功能组合使用。</span><span class="sxs-lookup"><span data-stu-id="5a948-151">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>

- <span data-ttu-id="5a948-152">当处理 XAML 2009 for load 时，WPF XAML 实现还会将此功能添加到使用类型的某些框架属性的隐式类型转换行为 <xref:System.Type> 。</span><span class="sxs-lookup"><span data-stu-id="5a948-152">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>

<span data-ttu-id="5a948-153">在 WPF 中，可以使用 XAML 2009 功能，但仅针对未进行标记编译) 的松散 XAML (XAML。</span><span class="sxs-lookup"><span data-stu-id="5a948-153">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="5a948-154">WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="5a948-154">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a948-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a948-155">See also</span></span>

- <xref:System.Windows.Style>
- [<span data-ttu-id="5a948-156">样式和模板 (WPF .NET)</span><span class="sxs-lookup"><span data-stu-id="5a948-156">Styles and templates (WPF .NET)</span></span>](../net/wpf/controls/styles-templates-overview.md)
- [<span data-ttu-id="5a948-157">XAML 概述 (WPF .NET)</span><span class="sxs-lookup"><span data-stu-id="5a948-157">XAML overview (WPF .NET)</span></span>](../net/wpf/xaml/index.md)
- [<span data-ttu-id="5a948-158">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="5a948-158">Markup Extensions and WPF XAML</span></span>](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
