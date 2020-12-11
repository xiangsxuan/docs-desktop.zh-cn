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
# <a name="-escape-sequence--markup-extension"></a>{} 转义序列/标记扩展

提供特性值的 XAML 转义序列。 转义序列允许将属性中的后续值解释为文本。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a>XAML 属性元素用法

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|*literalValue*|位于转义序列后面的文本字符串。 通常，此字符串包含左大括号或右大括号 ( {或} ) 。|

## <a name="remarks"></a>备注

使用转义序列 ({}) ，以便可在 XAML 中将左大括号 ( {) 用作文本字符。

XAML 读取器通常使用左大括号 ( {) 来表示标记扩展的入口点; 但是，它们首先会检查下一个字符，以确定它是否为右大括号 (} ) 。 仅当两个大括号 ({}) 相邻时，它们是否被视为转义序列。

如果遇到转义序列，XAML 读取器应以字符串的形式处理字符串的其余部分。 但是，如果将转义序列应用于具有类型转换器的成员，则在 XAML 编写器解释该字符串时，可能会经历类型转换。

转义序列不是标记扩展，并且不受类支持。 但是，XAML 读取器 (包括) 应遵循的自定义 XAML 读取器这一约定。

不能以这种方式将引号 ( ") 用作转义序列。 如果需要将引号设置为 noncontent 属性的属性值，请使用属性元素语法，并将引号放置为属性元素内的字符串，或使用 XML 字符实体。 对于内容属性，引号可以是整个内容。

在 {} 指定 XML 类型时，如果 XML 类型必须在可能出现 XAML 标记扩展的位置中包含命名空间限定符，则通常需要使用转义序列 () 。 此位置包括 XAML 特性值的开头，并且在标记扩展中紧跟在等号 (=) 之后。 下面的示例演示在 XAML 特性值开始时显示的 XML 命名空间的转义序列。

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a>另请参阅

- [XAML 的类型转换器和标记扩展](type-converters-and-markup-extensions.md)
- [XML 字符实体和 XAML](xml-character-entities.md)
