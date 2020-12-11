---
title: XAML 中的 xml:space 处理
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: b05fb396850316c76721c72276ebb97f7e805ed3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970922"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="63149-102">XAML 中的 xml:space 处理</span><span class="sxs-lookup"><span data-stu-id="63149-102">xml:space Handling in XAML</span></span>

<span data-ttu-id="63149-103">`xml:space`特性是一个 XML 定义的特性，用于声明对象元素内的有效空白处理行为。</span><span class="sxs-lookup"><span data-stu-id="63149-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="63149-104">此行为与在声明的元素中包含的所有内容 (内部文本) 相关 `xml:space` ，同时还适用于子元素。</span><span class="sxs-lookup"><span data-stu-id="63149-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="63149-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="63149-105">XAML Attribute Usage</span></span>

```xaml
<object xml:space="preserve" />
```

 <span data-ttu-id="63149-106">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="63149-106">\- or -</span></span>

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a><span data-ttu-id="63149-107">备注</span><span class="sxs-lookup"><span data-stu-id="63149-107">Remarks</span></span>

<span data-ttu-id="63149-108">`xml:space`XAML 中的特性的定义（包括其两个可能的值 `xml:space` ）是由 W3C for XML 规范定义为的 "特殊特性"。</span><span class="sxs-lookup"><span data-stu-id="63149-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>

<span data-ttu-id="63149-109">该属性的默认值 `xml:space` 为文本值 `"default"` 。</span><span class="sxs-lookup"><span data-stu-id="63149-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="63149-110">对于值 `"default"` ，或者如果 `xml:space` 根本没有指示，则有效的空白分析的行为是默认处理，如在 [XAML 中的空白处理](white-space-processing.md)中定义的那样。</span><span class="sxs-lookup"><span data-stu-id="63149-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](white-space-processing.md).</span></span>

<span data-ttu-id="63149-111">若要保留对象元素内容中的空格，请 `xml:space="preserve"` 在该对象元素上指定。</span><span class="sxs-lookup"><span data-stu-id="63149-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>

<span data-ttu-id="63149-112">在大多数解释下，属性 `xml:space` 效果和属性的值的范围限定为子元素。</span><span class="sxs-lookup"><span data-stu-id="63149-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>

<span data-ttu-id="63149-113">有关 XAML 中的空白处理的完整讨论，请参阅 [xaml 中的空白处理](white-space-processing.md)。</span><span class="sxs-lookup"><span data-stu-id="63149-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](white-space-processing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="63149-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63149-114">See also</span></span>

- [<span data-ttu-id="63149-115">XAML 中的空白处理</span><span class="sxs-lookup"><span data-stu-id="63149-115">White-space processing in XAML</span></span>](white-space-processing.md)
- [<span data-ttu-id="63149-116">WPF)  (XAML 概述 </span><span class="sxs-lookup"><span data-stu-id="63149-116">XAML Overview (WPF)</span></span>](../net/wpf/fundamentals/xaml.md)
