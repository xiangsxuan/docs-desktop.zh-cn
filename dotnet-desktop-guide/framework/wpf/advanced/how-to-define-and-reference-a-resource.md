---
title: 如何：定义和引用资源
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: b7c7c7a06837750e77c313f50a6dd4f61029f892
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665934"
---
# <a name="how-to-define-and-reference-a-resource"></a>如何：定义和引用资源

此示例演示如何使用中的属性定义资源并对其进行引用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。

## <a name="example"></a>示例

下面的示例定义了两种类型的资源： <xref:System.Windows.Media.SolidColorBrush> 资源和多个 <xref:System.Windows.Style> 资源。 <xref:System.Windows.Media.SolidColorBrush>资源 `MyBrush` 用于提供多个属性的值，每个属性都采用 <xref:System.Windows.Media.Brush> 类型值。 <xref:System.Windows.Style>资源 `PageBackground` ， `TitleText` `Label` 每个目标为特定的控件类型。 样式在目标控件上设置各种不同的属性，当该样式资源由资源键引用并用于设置 <xref:System.Windows.FrameworkElement.Style%2A> 中定义的多个特定控件元素的属性时 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。

请注意，样式的资源库中的一个属性 `Label` 也引用 `MyBrush` 前面定义的资源。 这是一种常见的技术，但请务必记住，按给定顺序对资源进行分析并将其输入到资源字典中。 如果使用 [StaticResource 标记扩展](staticresource-markup-extension.md) 在其他资源内引用资源，则还会按字典中找到的顺序请求资源。 请确保所引用的任何资源先前在资源集合中定义的资源超出了该资源的请求位置。 如有必要，可以通过使用 [DynamicResource 标记扩展](dynamicresource-markup-extension.md) 在运行时引用资源来解决资源引用的严格创建顺序，但应注意，这种 DynamicResource 方法会产生性能后果。 有关详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)。

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a>请参阅

- [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
