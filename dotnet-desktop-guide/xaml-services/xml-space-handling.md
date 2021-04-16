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
# <a name="xmlspace-handling-in-xaml"></a>XAML 中的 xml:space 处理

`xml:space`特性是一个 XML 定义的特性，用于声明对象元素内的有效空白处理行为。 此行为与在声明的元素中包含的所有内容 (内部文本) 相关 `xml:space` ，同时还适用于子元素。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object xml:space="preserve" />
```

 \- 或 -

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a>注解

`xml:space`XAML 中的特性的定义（包括其两个可能的值 `xml:space` ）是由 W3C for XML 规范定义为的 "特殊特性"。

该属性的默认值 `xml:space` 为文本值 `"default"` 。 对于值 `"default"` ，或者如果 `xml:space` 根本没有指示，则有效的空白分析的行为是默认处理，如在 [XAML 中的空白处理](white-space-processing.md)中定义的那样。

若要保留对象元素内容中的空格，请 `xml:space="preserve"` 在该对象元素上指定。

在大多数解释下，属性 `xml:space` 效果和属性的值的范围限定为子元素。

有关 XAML 中的空白处理的完整讨论，请参阅 [xaml 中的空白处理](white-space-processing.md)。

## <a name="see-also"></a>另请参阅

- [XAML 中的空白处理](white-space-processing.md)
- [XAML 概述 (WPF .NET)](../net/wpf/xaml/index.md)
