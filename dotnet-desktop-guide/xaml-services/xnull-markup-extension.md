---
title: x:Null 标记扩展
description: 说明 XAML 如何处理 x:Null 标记扩展。
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
ms.openlocfilehash: ad204ff850343d5893a3952105a007c236e07e3f
ms.sourcegitcommit: 32616f61a7b001efcc8567fee5fdf01f83da76cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "107560354"
---
# <a name="xnull-markup-extension"></a>x:Null 标记扩展

指定 `null` 作为 XAML 成员的值。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a>注解

C # 和 c + + 中的空引用的关键字为 null。 Microsoft Visual Basic 关键字用于空引用 `Nothing` ，但你始终使用 `{x:Null}` 作为 xaml 用法，而不考虑与 xaml 关联的代码隐藏语言。

`x:Null`标记扩展没有可设置的属性。

Null 用法通常与 CLR 值的 XAML 成员公开关联 <xref:System.Nullable%601> 。

`x:Null`标记扩展与所有 XAML 标记扩展一样，都使用大括号 (`{,}`) 将属性值的处理转义为非文本或事件处理程序引用。 特性语法是最常用于该标记扩展的语法。 对象元素语法 `<x:Null />` 在技术上是可行的，但很少使用，因为 `x:Null` 标记扩展没有位置参数或构造参数。

有关标记扩展的信息，请参阅 [标记扩展和 WPF XAML](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。

在 .NET XAML 服务中，对此标记扩展的处理由类定义 <xref:System.Windows.Markup.NullExtension> 。

## <a name="wpf-usage-notes"></a>WPF 用法说明

请注意， `null` 不一定是引用类型依赖属性的初始未设置值。 对于每个依赖属性，初始默认值可能有所不同，并且可以基于特定于属性的元数据。 许多依赖属性 `null` 由于其验证回调实现而不接受作为值。 有关依赖项属性的详细信息，请参阅[依赖项属性概述](../framework/wpf/advanced/dependency-properties-overview.md)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [XAML 概述 (WPF .NET)](../net/wpf/xaml/index.md)
- [标记扩展和 WPF XAML](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
