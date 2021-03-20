---
title: PresentationOptions:Freeze 特性
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d4cd4b727338fdb3e6c6e4872c25b323aebe144e
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667143"
---
# <a name="presentationoptionsfreeze-attribute"></a>PresentationOptions:Freeze 特性
将 <xref:System.Windows.Freezable.IsFrozen%2A> 包含元素的状态设置为 `true` <xref:System.Windows.Freezable> 。 如果未指定属性，则的默认行为是 <xref:System.Windows.Freezable> `PresentationOptions:Freeze` <xref:System.Windows.Freezable.IsFrozen%2A> `false` 在加载时，并且依赖于 <xref:System.Windows.Freezable> 运行时的常规行为。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`PresentationOptions`|XML 命名空间前缀，可以是每个 XML 1.0 规范的任何有效的前缀字符串。 `PresentationOptions`在本文档中，前缀用于标识目的。|  
|`freezableElement`|一个实例化的任何派生类的元素 <xref:System.Windows.Freezable> 。|  
  
## <a name="remarks"></a>备注  
 `Freeze`特性是在 XML 命名空间中定义的唯一特性或其他编程元素 `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` 。 `Freeze`此特殊命名空间中存在属性，因此可将其指定为可忽略，并使用[mc：可忽略属性](mc-ignorable-attribute.md)作为根元素声明的一部分。 `Freeze`必须能够被忽略的原因是，并非所有 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器实现都能够 <xref:System.Windows.Freezable> 在加载时冻结; 此功能不是规范的组成部分 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。  
  
 处理属性的功能 `Freeze` 专门内置于 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 已编译应用程序的处理器。 任何类都不支持该特性，且特性语法不可扩展或可修改。 如果要实现自己的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器，可以选择在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 加载时并行处理元素上的属性时，并行处理处理器的冻结行为 `Freeze` <xref:System.Windows.Freezable> 。  
  
 `Freeze`除 `true` (不区分大小写) 以外的其他属性值会生成加载时错误。  (将 `Freeze` 属性指定为 `false` 不是错误，但已是默认值，则将设置为 `false` 不会) 。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Freezable>
- [Freezable 对象概述](freezable-objects-overview.md)
- [mc:Ignorable 特性](mc-ignorable-attribute.md)
