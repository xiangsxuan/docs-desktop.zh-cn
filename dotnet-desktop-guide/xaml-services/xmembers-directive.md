---
title: x:Members 指令
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: c751a4f1cdea8dce7ef5165f5225ab3a825c7344
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970925"
---
# <a name="xmembers-directive"></a>x:Members 指令
保存一组在标记中定义的成员，这些成员应用于父元素的 X：Class。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object x:Class="className">
<x:Members>
  oneOrMoreMembers
</x:Members
</object>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|`className`|XAML 生产的备用类或分部类的名称。 请参阅“备注”。|
|`oneOrMoreMembers`|一个或多个表示成员定义的对象元素。 通常，这些是 `x:Property` 对象元素。 请参阅“备注”。|

## <a name="remarks"></a>备注

在 .NET XAML 服务实现中，没有支持的后备类或基础成员实现 `x:Members` 。 `x:Members` 是一个特殊的 XAML 成员，可作为任何类型的成员存在。 在 XAML 节点流中， `x:Members` 表示为 `Members` 来自 XAML 语言 xaml 命名空间的名为的成员。 成员 `Members` 包含对象的只读泛型列表 `Member` 。 在典型标记中，将各个成员指定为 `x:Property` 属性元素。 `x:Property` 是特定于类型的属性的更精确的类型，可分配给 `x:Member` 。 有关详细信息，请参阅 [X:Property 指令](xproperty-directive.md)。

若要支持将 `x:Members` 实际用作一种在标记中指定成员定义的方法，成员必须与可修改的类相关联。 预期模型是 `x:Members` 作为指定 `x:Class` 的类型的成员存在。 但是，在 .NET XAML 服务级别不支持关联类型和成员或用于生成动态成员定义的机制。 此功能由具有支持 XAML 的成员定义的应用程序模型的单个框架实现。 通常，需要 MSBUILD 生成操来支持此功能，这些操作以标记编译 XAML 并将其与隐藏代码相集成或者从 XMAL 生成纯程序集。

## <a name="xmembers-for-windows-workflow-foundation"></a>用于 Windows Workflow Foundation 的 x:Members

对于 "Windows Workflow Foundation"， `x:Members` 包含完全在 xaml 中组成的自定义活动的成员，或包含代码隐藏的活动设计器的 XAML 定义的动态成员。 此外，必须在 XAML 生产的根元素上指定 `x:Class`。 这不是 .NET XAML 服务级别的要求，但当 XAML 生产由支持自定义活动和 Windows Workflow Foundation XAML 的 MSBUILD 生成操作加载时，就会成为一项要求。 `x:Members` 必须是声明的对象元素的标记中的第一个子元素 `x:Class` 。
