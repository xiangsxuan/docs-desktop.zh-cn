---
title: XamlName 语法
description: 介绍与 XamlName Grammer 相关的 XAML 语言规范。
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: abc544d9b74f34aa138bba13cc5581554d232607
ms.sourcegitcommit: 32616f61a7b001efcc8567fee5fdf01f83da76cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "107560174"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="c0e66-103">XamlName 语法</span><span class="sxs-lookup"><span data-stu-id="c0e66-103">XamlName Grammar</span></span>

<span data-ttu-id="c0e66-104">XamlName 语法是在 XAML 语言规范 [MS-CHAP] 中定义的一种特定语法，此处将在此处重现此语法。</span><span class="sxs-lookup"><span data-stu-id="c0e66-104">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>

## <a name="from-the-xaml-specification"></a><span data-ttu-id="c0e66-105">从 XAML 规范</span><span class="sxs-lookup"><span data-stu-id="c0e66-105">From the XAML Specification</span></span>

<span data-ttu-id="c0e66-106">[MS-CHAP] 规范定义语法 XamlName，用于标识用于类型和属性的合法符号标识符集。</span><span class="sxs-lookup"><span data-stu-id="c0e66-106">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>

<span data-ttu-id="c0e66-107">XamlName 类型的字符串值必须符合以下语法：</span><span class="sxs-lookup"><span data-stu-id="c0e66-107">String values that are of type XamlName must conform to the following grammar:</span></span>

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

<span data-ttu-id="c0e66-108">它假定 Unicode 字符数据库中定义的以下常规类别值</span><span class="sxs-lookup"><span data-stu-id="c0e66-108">Which assumes the following general category values as defined in the Unicode Character Database</span></span>

| <span data-ttu-id="c0e66-109">Unicode 类别</span><span class="sxs-lookup"><span data-stu-id="c0e66-109">Unicode category</span></span>   | <span data-ttu-id="c0e66-110">说明</span><span class="sxs-lookup"><span data-stu-id="c0e66-110">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="c0e66-111">Lu</span><span class="sxs-lookup"><span data-stu-id="c0e66-111">Lu</span></span>                 | <span data-ttu-id="c0e66-112">字母，大写</span><span class="sxs-lookup"><span data-stu-id="c0e66-112">Letter, Uppercase</span></span>             |
| <span data-ttu-id="c0e66-113">Ll</span><span class="sxs-lookup"><span data-stu-id="c0e66-113">Ll</span></span>                 | <span data-ttu-id="c0e66-114">字母，小写</span><span class="sxs-lookup"><span data-stu-id="c0e66-114">Letter, Lowercase</span></span>             |
| <span data-ttu-id="c0e66-115">Lt</span><span class="sxs-lookup"><span data-stu-id="c0e66-115">Lt</span></span>                 | <span data-ttu-id="c0e66-116">字母，首字母大写</span><span class="sxs-lookup"><span data-stu-id="c0e66-116">Letter, Titlecase</span></span>             |
| <span data-ttu-id="c0e66-117">Lm</span><span class="sxs-lookup"><span data-stu-id="c0e66-117">Lm</span></span>                 | <span data-ttu-id="c0e66-118">字母，修饰符</span><span class="sxs-lookup"><span data-stu-id="c0e66-118">Letter, Modifier</span></span>              |
| <span data-ttu-id="c0e66-119">Lo</span><span class="sxs-lookup"><span data-stu-id="c0e66-119">Lo</span></span>                 | <span data-ttu-id="c0e66-120">字母，其他</span><span class="sxs-lookup"><span data-stu-id="c0e66-120">Letter, Other</span></span>                 |
| <span data-ttu-id="c0e66-121">Mn</span><span class="sxs-lookup"><span data-stu-id="c0e66-121">Mn</span></span>                 | <span data-ttu-id="c0e66-122">标记，非间距</span><span class="sxs-lookup"><span data-stu-id="c0e66-122">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="c0e66-123">Mc</span><span class="sxs-lookup"><span data-stu-id="c0e66-123">Mc</span></span>                 | <span data-ttu-id="c0e66-124">标记，间距组合</span><span class="sxs-lookup"><span data-stu-id="c0e66-124">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="c0e66-125">Nd</span><span class="sxs-lookup"><span data-stu-id="c0e66-125">Nd</span></span>                 | <span data-ttu-id="c0e66-126">Number、Decimal</span><span class="sxs-lookup"><span data-stu-id="c0e66-126">Number, Decimal</span></span>               |
| <span data-ttu-id="c0e66-127">Nl</span><span class="sxs-lookup"><span data-stu-id="c0e66-127">Nl</span></span>                 | <span data-ttu-id="c0e66-128">数字，字母</span><span class="sxs-lookup"><span data-stu-id="c0e66-128">Number, Letter</span></span>                |

<span data-ttu-id="c0e66-129">XAML 定义了第二个语法 DottedXamlName，用于属性和事件限定引用，还用于附加成员。</span><span class="sxs-lookup"><span data-stu-id="c0e66-129">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="c0e66-130">有关详细信息，请参阅 <xref:System.Windows.DependencyProperty> 和 [XAML 概述 (WPF .net) ](../net/wpf/xaml/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c0e66-130">For more information, see <xref:System.Windows.DependencyProperty> and [XAML overview (WPF .NET)](../net/wpf/xaml/index.md).</span></span>

<span data-ttu-id="c0e66-131">DottedXamlName 类型的字符串值必须符合以下语法：</span><span class="sxs-lookup"><span data-stu-id="c0e66-131">String values that are of type DottedXamlName must conform to the following grammar:</span></span>

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a><span data-ttu-id="c0e66-132">注解</span><span class="sxs-lookup"><span data-stu-id="c0e66-132">Remarks</span></span>

<span data-ttu-id="c0e66-133">有关完整规范，请参阅 " [ \[ MS- \] XAML](/previous-versions/msp-n-p/ff650760(v=pandp.10))"。</span><span class="sxs-lookup"><span data-stu-id="c0e66-133">For the complete specification, see [\[MS-XAML\]](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>
