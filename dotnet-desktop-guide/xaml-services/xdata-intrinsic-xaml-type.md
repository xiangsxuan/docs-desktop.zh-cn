---
title: x:XData 内部 XAML 类型
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: 89bdae68608db235b76d6a9b210c77f97bcebe00
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970930"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="7d146-102">x:XData 内部 XAML 类型</span><span class="sxs-lookup"><span data-stu-id="7d146-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="7d146-103">启用 XML 数据岛在 XAML 生产中的放置。</span><span class="sxs-lookup"><span data-stu-id="7d146-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="7d146-104">`x:XData`XAML 处理器不应处理中的 XML 元素，就好像它们是正在操作的默认 xaml 命名空间或任何其他 XAML 命名空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="7d146-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="7d146-105">`x:XData` 可以包含任意格式正确的 XML。</span><span class="sxs-lookup"><span data-stu-id="7d146-105">`x:XData` can contain arbitrary well-formed XML.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="7d146-106">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="7d146-106">XAML Object Element Usage</span></span>

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a><span data-ttu-id="7d146-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="7d146-107">XAML Values</span></span>

|||
|-|-|
|`elementDataRoot`|<span data-ttu-id="7d146-108">括起来的数据岛的单个根元素。</span><span class="sxs-lookup"><span data-stu-id="7d146-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="7d146-109">对于最终使用者而言，没有单个根的 XML 被视为无效。</span><span class="sxs-lookup"><span data-stu-id="7d146-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="7d146-110">特别是，如果要 `x:XData` 用作 WPF 的 xml 数据源，或使用 xml 源进行数据绑定的许多其他技术，则需要单个根。</span><span class="sxs-lookup"><span data-stu-id="7d146-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|
|`[elementData]`|<span data-ttu-id="7d146-111">可选。</span><span class="sxs-lookup"><span data-stu-id="7d146-111">Optional.</span></span> <span data-ttu-id="7d146-112">表示 XML 数据的 XML。</span><span class="sxs-lookup"><span data-stu-id="7d146-112">XML that represents the XML data.</span></span> <span data-ttu-id="7d146-113">可以将任意数量的元素包含为元素数据，嵌套元素可以包含在其他元素中;但是，XML 的一般规则是适用的。</span><span class="sxs-lookup"><span data-stu-id="7d146-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7d146-114">备注</span><span class="sxs-lookup"><span data-stu-id="7d146-114">Remarks</span></span>

<span data-ttu-id="7d146-115">对象中的 XML 元素 `x:XData` 可以在数据中重新声明包含 XMLDOM 的所有可能的命名空间和前缀。</span><span class="sxs-lookup"><span data-stu-id="7d146-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>

<span data-ttu-id="7d146-116">可以通过类以编程方式访问 XML 数据和 `x:XData` 内部 xaml 类型 <xref:System.Windows.Markup.XData> 。</span><span class="sxs-lookup"><span data-stu-id="7d146-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="7d146-117">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="7d146-117">WPF Usage Notes</span></span>

<span data-ttu-id="7d146-118">`x:XData`对象主要用作的子对象 <xref:System.Windows.Data.XmlDataProvider> ，或者作为 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> (在 XAML 中的属性的子对象，这通常用属性元素语法) 来表示。</span><span class="sxs-lookup"><span data-stu-id="7d146-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>

<span data-ttu-id="7d146-119">通常，数据会将数据岛中的基本 XML 命名空间重新定义为新的默认 XML 命名空间 (设置为空字符串) 。</span><span class="sxs-lookup"><span data-stu-id="7d146-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="7d146-120">对于简单的数据岛，这是最简单的，因为 <xref:System.Windows.Data.Binding.XPath%2A> 用于引用和绑定到数据的表达式可避免包含前缀。</span><span class="sxs-lookup"><span data-stu-id="7d146-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="7d146-121">更复杂的数据岛可能会为数据定义多个前缀，并在根处为 XML 命名空间使用特定的前缀。</span><span class="sxs-lookup"><span data-stu-id="7d146-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="7d146-122">在这种情况下，所有 <xref:System.Windows.Data.Binding.XPath%2A> 表达式引用应包括相应的命名空间映射前缀。</span><span class="sxs-lookup"><span data-stu-id="7d146-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="7d146-123">有关详细信息，请参阅 [数据绑定概述](../net/wpf/data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7d146-123">For more information, see [Data Binding Overview](../net/wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="7d146-124">从技术上讲， `x:XData` 可以用作类型的任何属性的内容 <xref:System.Xml.Serialization.IXmlSerializable> 。</span><span class="sxs-lookup"><span data-stu-id="7d146-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="7d146-125">不过， <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 是唯一的主要实现。</span><span class="sxs-lookup"><span data-stu-id="7d146-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d146-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d146-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="7d146-127">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="7d146-127">Data Binding Overview</span></span>](../net/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="7d146-128">绑定标记扩展</span><span class="sxs-lookup"><span data-stu-id="7d146-128">Binding Markup Extension</span></span>](../framework/wpf/advanced/binding-markup-extension.md)
