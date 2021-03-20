---
title: 如何：注册附加属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF], registering
- registering attached properties [WPF]
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
ms.openlocfilehash: 4793111e5aca841f63aa479924a3c8c6d020423f
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665856"
---
# <a name="how-to-register-an-attached-property"></a>如何：注册附加属性
此示例演示如何注册附加属性和提供公共访问器，以便可以在 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 和代码中使用该属性。 附加属性是由 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 定义的语法概念。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 类型的大多数附加属性还作为依赖属性实现。 可以对任何类型使用依赖属性 <xref:System.Windows.DependencyObject> 。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用方法将附加属性注册为依赖属性 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 。 在其他类上使用属性时，提供程序类可以选择为适用的属性提供默认元数据，除非该类会重写元数据。 在此示例中，`IsBubbleSource` 属性的默认值设置为 `false`。  
  
 附加属性（即使未注册为依赖属性）的提供程序类必须提供遵循 `Set`*[附加属性名称]* 和 `Get`*[附加属性名称]* 命名约定的静态 get 和 set 访问器。 需要这些访问器目的是生效的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 读取器可以在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中将属性识别为特性，并解析相应的类型。  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.DependencyProperty>
- [依赖项属性概述](dependency-properties-overview.md)
- [自定义依赖项属性](custom-dependency-properties.md)
- [操作指南主题](properties-how-to-topics.md)
