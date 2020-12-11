---
title: x:Null 标记扩展
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: 7f7c4cd44448b6e4e8b8934a63b56b910ce0428a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970912"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="d8c99-102">x:Null 标记扩展</span><span class="sxs-lookup"><span data-stu-id="d8c99-102">x:Null Markup Extension</span></span>

<span data-ttu-id="d8c99-103">指定 `null` 作为 XAML 成员的值。</span><span class="sxs-lookup"><span data-stu-id="d8c99-103">Specifies `null` as a value for a XAML member.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="d8c99-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="d8c99-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a><span data-ttu-id="d8c99-105">备注</span><span class="sxs-lookup"><span data-stu-id="d8c99-105">Remarks</span></span>

<span data-ttu-id="d8c99-106">C # 和 c + + 中的空引用的关键字为 null。</span><span class="sxs-lookup"><span data-stu-id="d8c99-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="d8c99-107">Microsoft Visual Basic 关键字用于空引用 `Nothing` ，但你始终使用 `{x:Null}` 作为 xaml 用法，而不考虑与 xaml 关联的代码隐藏语言。</span><span class="sxs-lookup"><span data-stu-id="d8c99-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>

<span data-ttu-id="d8c99-108">`x:Null`标记扩展没有可设置的属性。</span><span class="sxs-lookup"><span data-stu-id="d8c99-108">The `x:Null` markup extension has no settable properties.</span></span>

<span data-ttu-id="d8c99-109">Null 用法通常与 CLR 值的 XAML 成员公开关联 <xref:System.Nullable%601> 。</span><span class="sxs-lookup"><span data-stu-id="d8c99-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>

<span data-ttu-id="d8c99-110">`x:Null`标记扩展与所有 XAML 标记扩展一样，都使用大括号 (`{,}`) 将属性值的处理转义为非文本或事件处理程序引用。</span><span class="sxs-lookup"><span data-stu-id="d8c99-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="d8c99-111">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="d8c99-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="d8c99-112">对象元素语法 `<x:Null />` 在技术上是可行的，但很少使用，因为 `x:Null` 标记扩展没有位置参数或构造参数。</span><span class="sxs-lookup"><span data-stu-id="d8c99-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>

<span data-ttu-id="d8c99-113">有关标记扩展的信息，请参阅 [标记扩展和 WPF XAML](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c99-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>

<span data-ttu-id="d8c99-114">在 .NET XAML 服务中，对此标记扩展的处理由类定义 <xref:System.Windows.Markup.NullExtension> 。</span><span class="sxs-lookup"><span data-stu-id="d8c99-114">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="d8c99-115">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="d8c99-115">WPF Usage Notes</span></span>

<span data-ttu-id="d8c99-116">请注意， `null` 不一定是引用类型依赖属性的初始未设置值。</span><span class="sxs-lookup"><span data-stu-id="d8c99-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="d8c99-117">对于每个依赖属性，初始默认值可能有所不同，并且可以基于特定于属性的元数据。</span><span class="sxs-lookup"><span data-stu-id="d8c99-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="d8c99-118">许多依赖属性 `null` 由于其验证回调实现而不接受作为值。</span><span class="sxs-lookup"><span data-stu-id="d8c99-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="d8c99-119">有关依赖项属性的详细信息，请参阅[依赖项属性概述](../framework/wpf/advanced/dependency-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c99-119">For more information about dependency properties, see [Dependency Properties Overview](../framework/wpf/advanced/dependency-properties-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d8c99-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8c99-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="d8c99-121">WPF)  (XAML 概述 </span><span class="sxs-lookup"><span data-stu-id="d8c99-121">XAML Overview (WPF)</span></span>](../net/wpf/fundamentals/xaml.md)
- [<span data-ttu-id="d8c99-122">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="d8c99-122">Markup Extensions and WPF XAML</span></span>](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
