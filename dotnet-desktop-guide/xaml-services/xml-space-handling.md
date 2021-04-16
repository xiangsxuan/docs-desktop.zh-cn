---
title: XAML 中的 xml:space 处理
description: 介绍 xml： space 特性及其如何影响对象元素中的空白处理行为。
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 7496349a2c815adaf15308eb0bce458ebc1951da
ms.sourcegitcommit: 32616f61a7b001efcc8567fee5fdf01f83da76cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "107560229"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="a8d3c-103">XAML 中的 xml:space 处理</span><span class="sxs-lookup"><span data-stu-id="a8d3c-103">xml:space Handling in XAML</span></span>

<span data-ttu-id="a8d3c-104">`xml:space`特性是一个 XML 定义的特性，用于声明对象元素内的有效空白处理行为。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-104">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="a8d3c-105">此行为与在声明的元素中包含的所有内容 (内部文本) 相关 `xml:space` ，同时还适用于子元素。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-105">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="a8d3c-106">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="a8d3c-106">XAML Attribute Usage</span></span>

```xaml
<object xml:space="preserve" />
```

 <span data-ttu-id="a8d3c-107">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="a8d3c-107">\- or -</span></span>

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a><span data-ttu-id="a8d3c-108">注解</span><span class="sxs-lookup"><span data-stu-id="a8d3c-108">Remarks</span></span>

<span data-ttu-id="a8d3c-109">`xml:space`XAML 中的特性的定义（包括其两个可能的值 `xml:space` ）是由 W3C for XML 规范定义为的 "特殊特性"。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-109">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>

<span data-ttu-id="a8d3c-110">该属性的默认值 `xml:space` 为文本值 `"default"` 。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-110">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="a8d3c-111">对于值 `"default"` ，或者如果 `xml:space` 根本没有指示，则有效的空白分析的行为是默认处理，如在 [XAML 中的空白处理](white-space-processing.md)中定义的那样。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-111">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](white-space-processing.md).</span></span>

<span data-ttu-id="a8d3c-112">若要保留对象元素内容中的空格，请 `xml:space="preserve"` 在该对象元素上指定。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-112">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>

<span data-ttu-id="a8d3c-113">在大多数解释下，属性 `xml:space` 效果和属性的值的范围限定为子元素。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-113">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>

<span data-ttu-id="a8d3c-114">有关 XAML 中的空白处理的完整讨论，请参阅 [xaml 中的空白处理](white-space-processing.md)。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-114">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](white-space-processing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a8d3c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8d3c-115">See also</span></span>

- [<span data-ttu-id="a8d3c-116">XAML 中的空白处理</span><span class="sxs-lookup"><span data-stu-id="a8d3c-116">White-space processing in XAML</span></span>](white-space-processing.md)
- [<span data-ttu-id="a8d3c-117">XAML 概述 (WPF .NET)</span><span class="sxs-lookup"><span data-stu-id="a8d3c-117">XAML overview (WPF .NET)</span></span>](../net/wpf/xaml/index.md)
