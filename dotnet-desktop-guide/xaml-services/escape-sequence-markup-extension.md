---
title: '{} 转义序列-标记扩展'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974021"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="25d46-102">{} 转义序列/标记扩展</span><span class="sxs-lookup"><span data-stu-id="25d46-102">{} Escape sequence / markup extension</span></span>

<span data-ttu-id="25d46-103">提供特性值的 XAML 转义序列。</span><span class="sxs-lookup"><span data-stu-id="25d46-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="25d46-104">转义序列允许将属性中的后续值解释为文本。</span><span class="sxs-lookup"><span data-stu-id="25d46-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="25d46-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="25d46-105">XAML Attribute Usage</span></span>

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a><span data-ttu-id="25d46-106">XAML 属性元素用法</span><span class="sxs-lookup"><span data-stu-id="25d46-106">XAML Property Element Usage</span></span>

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="25d46-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="25d46-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="25d46-108">*literalValue*</span><span class="sxs-lookup"><span data-stu-id="25d46-108">*literalValue*</span></span>|<span data-ttu-id="25d46-109">位于转义序列后面的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="25d46-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="25d46-110">通常，此字符串包含左大括号或右大括号 ( {或} ) 。</span><span class="sxs-lookup"><span data-stu-id="25d46-110">Typically this string contains an open or close brace ({ or }).</span></span>|

## <a name="remarks"></a><span data-ttu-id="25d46-111">备注</span><span class="sxs-lookup"><span data-stu-id="25d46-111">Remarks</span></span>

<span data-ttu-id="25d46-112">使用转义序列 ({}) ，以便可在 XAML 中将左大括号 ( {) 用作文本字符。</span><span class="sxs-lookup"><span data-stu-id="25d46-112">The escape sequence ({}) is used so that an open brace ({) can be used as a literal character in XAML.</span></span>

<span data-ttu-id="25d46-113">XAML 读取器通常使用左大括号 ( {) 来表示标记扩展的入口点; 但是，它们首先会检查下一个字符，以确定它是否为右大括号 (} ) 。</span><span class="sxs-lookup"><span data-stu-id="25d46-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="25d46-114">仅当两个大括号 ({}) 相邻时，它们是否被视为转义序列。</span><span class="sxs-lookup"><span data-stu-id="25d46-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>

<span data-ttu-id="25d46-115">如果遇到转义序列，XAML 读取器应以字符串的形式处理字符串的其余部分。</span><span class="sxs-lookup"><span data-stu-id="25d46-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="25d46-116">但是，如果将转义序列应用于具有类型转换器的成员，则在 XAML 编写器解释该字符串时，可能会经历类型转换。</span><span class="sxs-lookup"><span data-stu-id="25d46-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>

<span data-ttu-id="25d46-117">转义序列不是标记扩展，并且不受类支持。</span><span class="sxs-lookup"><span data-stu-id="25d46-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="25d46-118">但是，XAML 读取器 (包括) 应遵循的自定义 XAML 读取器这一约定。</span><span class="sxs-lookup"><span data-stu-id="25d46-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>

<span data-ttu-id="25d46-119">不能以这种方式将引号 ( ") 用作转义序列。</span><span class="sxs-lookup"><span data-stu-id="25d46-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="25d46-120">如果需要将引号设置为 noncontent 属性的属性值，请使用属性元素语法，并将引号放置为属性元素内的字符串，或使用 XML 字符实体。</span><span class="sxs-lookup"><span data-stu-id="25d46-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="25d46-121">对于内容属性，引号可以是整个内容。</span><span class="sxs-lookup"><span data-stu-id="25d46-121">For a content property, the quotation mark can be the entire content.</span></span>

<span data-ttu-id="25d46-122">在 {} 指定 XML 类型时，如果 XML 类型必须在可能出现 XAML 标记扩展的位置中包含命名空间限定符，则通常需要使用转义序列 () 。</span><span class="sxs-lookup"><span data-stu-id="25d46-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="25d46-123">此位置包括 XAML 特性值的开头，并且在标记扩展中紧跟在等号 (=) 之后。</span><span class="sxs-lookup"><span data-stu-id="25d46-123">This location includes the start of a XAML attribute value, and in a markup extension immediately after an equal sign (=).</span></span> <span data-ttu-id="25d46-124">下面的示例演示在 XAML 特性值开始时显示的 XML 命名空间的转义序列。</span><span class="sxs-lookup"><span data-stu-id="25d46-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a><span data-ttu-id="25d46-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25d46-125">See also</span></span>

- [<span data-ttu-id="25d46-126">XAML 的类型转换器和标记扩展</span><span class="sxs-lookup"><span data-stu-id="25d46-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions.md)
- [<span data-ttu-id="25d46-127">XML 字符实体和 XAML</span><span class="sxs-lookup"><span data-stu-id="25d46-127">XML Character Entities and XAML</span></span>](xml-character-entities.md)
