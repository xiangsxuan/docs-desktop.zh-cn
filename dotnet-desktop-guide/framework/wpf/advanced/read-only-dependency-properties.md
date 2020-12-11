---
title: 只读依赖项属性
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], read-only
- read-only dependency properties [WPF]
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
ms.openlocfilehash: cabe3f0789ffd0efbdcae8c497cc483f8f667b57
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973867"
---
# <a name="read-only-dependency-properties"></a>只读依赖项属性
本主题介绍只读依赖属性，包括现有只读依赖属性、创建自定义只读依赖属性的方案和技术。  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>先决条件  
 本主题假定你了解实现依赖属性的基本方案，以及如何将元数据应用于自定义依赖属性。 有关上下文，请参阅[自定义依赖属性](custom-dependency-properties.md)和[依赖属性元数据](dependency-property-metadata.md)。  
  
<a name="existing"></a>
## <a name="existing-read-only-dependency-properties"></a>现有只读依赖属性  
 在 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 框架中定义的某些依赖属性是只读的。 指定只读依赖属性的一般原因如下：这些属性应该用于状态确定，但是有多种因素影响该状态，从用户界面设计的角度看，仅将属性设置为该状态并不能达到预期的效果。 例如，属性 <xref:System.Windows.UIElement.IsMouseOver%2A> 实际上只是从鼠标输入中确定的状态。 任何通过避开实际的鼠标输入以编程方式设置此值的尝试都是不可预期的，并将导致不一致。  
  
 由于其不可设置性，只读依赖属性不适用于依赖属性通常为其提供一个解决方案（即：数据绑定，直接样式化为某个值、验证、动画和继承）的多种方案。 尽管不可设置，但只读依赖属性仍具有一些由属性系统中的依赖属性支持的其他功能。 只读依赖属性仍可以用作样式中的属性触发器，这是其他功能中最重要的功能。 不能使用正常的公共语言运行时 (CLR) 属性启用触发器;它需要是依赖属性。 前面提到的 <xref:System.Windows.UIElement.IsMouseOver%2A> 属性是一种很好的方案，在此方案中，为控件定义样式可能非常有用，在此情况下，当用户将鼠标放在控件的某个已定义区域上时，控件中复合元素的某个可见属性（如背景、前景或类似属性）将发生变化。 只读依赖属性中的更改还可以由属性系统的固有失效进程检测并报告，这实际上是在内部支持属性触发器功能。  
  
<a name="new"></a>
## <a name="creating-custom-read-only-dependency-properties"></a>创建自定义只读依赖属性  
 请务必阅读上一节中有关只读依赖属性为何不适用于许多典型依赖属性方案的内容。 但是如果有适当的方案，可能需要创建自己的只读依赖属性。  
  
 创建只读依赖属性的大多数过程与[自定义依赖属性](custom-dependency-properties.md)和[实现依赖属性](how-to-implement-a-dependency-property.md)主题中介绍的过程相同。 但有三个重要的差异：  
  
- 注册属性时，请调用 <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> 方法，而不是正常 <xref:System.Windows.DependencyProperty.Register%2A> 方法进行属性注册。  
  
- 实现 CLR "包装器" 属性时，请确保该包装也没有集实现，这样公开的公共包装的只读状态不会造成不一致。  
  
- 只读注册返回的对象是 <xref:System.Windows.DependencyPropertyKey> 而不是 <xref:System.Windows.DependencyProperty> 。 仍应将该字段存储为成员，但通常不将其设置为类型的公共成员。  
  
 无论你具有什么专用字段或值，可使用你确定的任何逻辑来完全编写对只读依赖属性的支持。 不过，最初或作为运行时逻辑的一部分设置属性的最直接方法是使用属性系统的 Api，而不是绕过属性系统并直接设置私有支持字段。 特别是，有一个接受类型为的参数的签名 <xref:System.Windows.DependencyObject.SetValue%2A> <xref:System.Windows.DependencyPropertyKey> 。 在应用程序逻辑中以编程方式设置此值的方式和位置将影响你在 <xref:System.Windows.DependencyPropertyKey> 首次注册依赖属性时，如何对创建的设置进行访问。 如果完全在专有类中处理此逻辑，或者如果要求从程序集的其他部分对其进行设置，可以在内部进行设置。 一种方法是 <xref:System.Windows.DependencyObject.SetValue%2A> 在相关事件的类事件处理程序中调用，该事件通知类实例存储的属性值需要更改。 另一种方法是在 <xref:System.Windows.PropertyChangedCallback> 注册期间使用成对的和 <xref:System.Windows.CoerceValueCallback> 回调作为这些属性的元数据的一部分来关联依赖属性。  
  
 由于 <xref:System.Windows.DependencyPropertyKey> 是私有的，而不是由代码之外的属性系统传播的，因此，只读依赖项属性确实比读写依赖属性具有更好的设置安全性。 对于读写依赖属性，标识字段是显式或隐式公用的，因此该属性可广泛设置。 有关更多详细信息，请参阅[依赖属性的安全性](dependency-property-security.md)。  
  
## <a name="see-also"></a>另请参阅

- [依赖项属性概述](dependency-properties-overview.md)
- [自定义依赖项属性](custom-dependency-properties.md)
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
