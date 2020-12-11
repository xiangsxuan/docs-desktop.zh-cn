---
title: x:Reference 标记扩展
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970910"
---
# <a name="xreference-markup-extension"></a>x:Reference 标记扩展

引用在 XAML 标记中其他位置声明的实例。 引用引用元素的 `x:Name` 。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a>XAML 对象元素用法

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|`instancexName`|`x:Name`值 (或 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> 被引用的实例的标识属性) 的值。|

## <a name="remarks"></a>备注

`x:Reference` 为在特定框架（如 WPF）中实现的元素引用概念提供 XAML 语言级支持。

## <a name="xreference-and-wpf"></a>x:Reference 和 WPF

在 WPF 和 XAML 2006 中，元素引用由绑定的框架级功能寻址 <xref:System.Windows.Data.Binding.ElementName%2A> 。 对于大多数 WPF 应用程序和方案， <xref:System.Windows.Data.Binding.ElementName%2A> 仍应使用绑定。 此常规指南的例外情况可能包括：数据上下文或其他范围注意事项，这些注意事项使数据绑定不切实际，不涉及标记编译。

`x:Reference` 是在 XAML 2009 中定义的构造。 在 WPF 中，可以使用 XAML 2009 功能，但仅针对未进行 WPF 标记编译的 XAML。 标记编译的 XAML 以及 BAML 形式的 XAML 当前不支持 XAML 2009 语言关键字和功能。
