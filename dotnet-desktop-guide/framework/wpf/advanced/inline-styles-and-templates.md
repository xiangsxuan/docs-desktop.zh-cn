---
title: 内联样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: bc28c25aa7acfa93ddd2b095762093ad9378744a
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665700"
---
# <a name="inline-styles-and-templates"></a>内联样式和模板
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 提供 <xref:System.Windows.Style> (子类) 的对象和模板对象，以便在 <xref:System.Windows.FrameworkTemplate> 资源中定义元素的可视外观，使其可多次使用。 出于此原因，中的特性 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 采用类型 <xref:System.Windows.Style> ， <xref:System.Windows.FrameworkTemplate> 几乎总是对现有样式和模板进行资源引用，而不是以内联方式定义新样式和模板。  
  
## <a name="limitations-of-inline-styles-and-templates"></a>内联样式和模板的限制  
 在中 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，样式和模板属性在技术上可以通过以下两种方式之一进行设置。 您可以使用特性语法来引用资源中定义的样式，例如 `<` *对象* `Style="{StaticResource` *myResourceKey* `}" .../>` 。 或者，可以使用属性元素语法来定义内联样式，例如：  
  
 `<`*对象*`>`  
  
 `<`*对象*`.Style>`  
  
 `<` `Style`  `.../>`  
  
 `</`*对象*`.Style>`  
  
 `</`*对象*`>`  
  
 特性用法更常见。 在资源中以内联方式定义且未在资源中定义的样式必须仅限于包含元素，因为它没有资源键，所以不能轻易地重新使用。 通常，资源定义的样式更通用并且有用，更多的是将 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 程序逻辑与代码中的程序逻辑分离在标记中的常规编程模型原则。  
  
 通常，即使只是要在该位置使用该样式或模板，也没有理由设置样式或模板。 大多数可以采用样式或模板的元素也支持 content 属性和内容模型。 如果只使用通过样式设置或模板化一次创建的任何逻辑树，只需在直接标记中使用等效的子元素填充该内容属性即可。 这会完全跳过样式和模板机制。  
  
 对于样式和模板，也可以通过返回对象的标记扩展启用其他语法。 可能的两种扩展插件都包含 [TemplateBinding](templatebinding-markup-extension.md) 和 <xref:System.Windows.Data.Binding> 。  
  
## <a name="see-also"></a>请参阅

- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
