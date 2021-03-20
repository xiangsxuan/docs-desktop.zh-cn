---
title: ComponentResourceKey 标记扩展
ms.date: 03/30/2017
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
ms.openlocfilehash: 1400f506789ded13ffd79640c1b10184a9322765
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666116"
---
# <a name="componentresourcekey-markup-extension"></a>ComponentResourceKey 标记扩展
定义和引用从外部程序集加载的资源的键。 这使得资源查找可以在程序集中指定目标类型，而不是在程序集或类中指定显式资源字典。  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>XAML 特性用法 (设置键，compact)   
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" ... />  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>XAML 特性用法 (设置键，详细)   
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" ... />  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>XAML 特性用法 (请求资源，compact)   
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" ... />  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>XAML 特性用法 (请求资源，详细)   
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" ... />  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`targetTypeName`|公共公共语言运行时的名称 (CLR) 类型（在资源程序集中定义）。|  
|`targetID`|资源的键。 查找资源时， `targetID` 将类似于资源的 " [X：Key" 指令](/dotnet/desktop-wpf/xaml-services/xkey-directive) 。|  
  
## <a name="remarks"></a>备注  
 如以上用法中所示， `ComponentResourceKey` 可在以下两个位置找到 {} 标记扩展用法：  
  
- 主题资源字典中的键的定义，由控件作者提供。  
  
- 在重新模板化控件时访问程序集中的主题资源，但需要使用由控件主题提供的资源提供的属性值。  
  
 对于引用来自主题的组件资源，通常建议使用 `{DynamicResource}` 而不是 `{StaticResource}` 。 用法中显示了这种情况。 `{DynamicResource}` 建议使用，因为用户可以更改主题本身。 如果希望组件资源与控件作者为支持主题最匹配，则应使组件资源引用也是动态的。  
  
 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>标识在实际定义资源的目标程序集中存在的类型。 `ComponentResourceKey`可以定义和使用独立于确切了解定义的位置 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> ，但最终必须通过引用的程序集解析类型。  
  
 的一个常见用途 <xref:System.Windows.ComponentResourceKey> 是定义随后作为类的成员公开的键。 对于此用法，使用 <xref:System.Windows.ComponentResourceKey> 类构造函数，而不是标记扩展。 有关详细信息，请参阅 <xref:System.Windows.ComponentResourceKey> 或主题 [控件创作概述](../controls/control-authoring-overview.md)的 "定义和引用主题资源的键" 一节。  
  
 对于建立密钥和引用键控资源，特性语法通常用于 `ComponentResourceKey` 标记扩展。  
  
 所示的压缩语法依赖于 <xref:System.Windows.ComponentResourceKey.%23ctor%2A> 标记扩展的构造函数签名和位置参数用法。 给定和的顺序非常 `targetTypeName` `targetID` 重要。 详细语法依赖于 <xref:System.Windows.ComponentResourceKey.%23ctor%2A> 无参数的构造函数，然后以与 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> <xref:System.Windows.ComponentResourceKey.ResourceId%2A> object 元素上的 true 特性语法类似的方式来设置和。 在详细语法中，设置属性的顺序并不重要。 主题 [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)中更详细地介绍了这两种备选方法的关系和机制 (简洁和详细) 。  
  
 从技术上来说，的值 `targetID` 可以是任何对象，不一定是字符串。 不过，WPF 最常见的用法是将 `targetID` 值与字符串形式的窗体进行对齐，在 [XamlName 语法](/dotnet/desktop-wpf/xaml-services/xamlname-grammar)中，此类字符串有效。  
  
 `ComponentResourceKey` 可以在对象元素语法中使用。 在这种情况下， <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 需要指定和属性的值 <xref:System.Windows.ComponentResourceKey.ResourceId%2A> 才能正确地初始化扩展。  
  
 在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 读取器实现中，对此标记扩展的处理由类定义 <xref:System.Windows.ComponentResourceKey> 。  
  
 `ComponentResourceKey` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。 有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [控件创作概述](../controls/control-authoring-overview.md)
- [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
