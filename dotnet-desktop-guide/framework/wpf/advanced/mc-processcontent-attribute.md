---
title: mc:ProcessContent 特性
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: 60906c4f5082a0d5989f744b73f5f90324aeccc7
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665375"
---
# <a name="mcprocesscontent-attribute"></a>mc:ProcessContent 特性

指定哪些 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 元素仍应由相关的父元素处理内容，即使 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 因为指定了 [Mc：可忽略属性](mc-ignorable-attribute.md)，处理程序可以忽略直接父元素。 `mc:ProcessContent`特性支持用于自定义命名空间映射和版本控制的标记兼容性 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|*ignorablePrefix*|根据 XML 1.0 规范的任何有效的前缀字符串。|  
|*ignorableUri*|根据 XML 1.0 规范指定命名空间的任何有效 URI。|  
|*ThisElementCanBeIgnored*|[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)]如果基础类型无法解析，则处理器实现可忽略的元素。|  
|*content*|*ThisElementCanBeIgnored* 被标记为可忽略。 如果处理器忽略该元素，则 *[content]* 由 *对象* 处理。|  
  
## <a name="remarks"></a>备注  

 默认情况下， [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器将忽略忽略元素内的内容。 您可以通过指定特定元素 `mc:ProcessContent` ， [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器将继续处理被忽略元素内的内容。 如果内容嵌套在多个标记中，则通常会使用此方法，其中至少一个标记为可忽略，其中至少有一个不可忽略。  
  
 可以使用空格分隔符在属性中指定多个前缀，例如： `mc:ProcessContent="ignore:Element1 ignore:Element2"` 。  
  
 `http://schemas.openxmlformats.org/markup-compatibility/2006`命名空间定义 SDK 的此区域中未记录的其他元素和特性。 有关详细信息，请参阅 [XML 标记兼容性规范](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification)。  
  
## <a name="see-also"></a>请参阅

- [mc:Ignorable 特性](mc-ignorable-attribute.md)
- [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)
