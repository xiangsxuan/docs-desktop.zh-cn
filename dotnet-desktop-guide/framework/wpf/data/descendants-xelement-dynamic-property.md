---
title: 子代（XElement 动态属性）
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 8d14b0a94d1a2028a56f649a574f157264ba50fa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970405"
---
# <a name="descendants-xelement-dynamic-property"></a>子代（XElement 动态属性）

获取一个索引器，用于检索与指定扩展名匹配的当前元素的所有子代元素。

## <a name="syntax"></a>语法

```xaml
elem.Descendants[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>属性值/返回值

一个类型为 `IEnumerable<XElement> Item(String expandedName)` 的索引器。 此索引器获取指定子代元素的扩展名，并返回 <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` 集合中的匹配子元素。

## <a name="remarks"></a>备注

此属性等效于 <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> 类的 <xref:System.Xml.Linq.XContainer> 方法。

返回集合中的元素按 XML 源文档顺序排列。

此属性使用延迟执行。

## <a name="see-also"></a>另请参阅

- [XElement 类动态属性](attribute-xelement-dynamic-property.md)
- [元素](elements-xelement-dynamic-property.md)
