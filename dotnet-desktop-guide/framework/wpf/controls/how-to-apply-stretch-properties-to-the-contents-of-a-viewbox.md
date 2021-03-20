---
title: 如何：向 Viewbox 的内容应用 Stretch 属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
ms.openlocfilehash: ecd2aa2ffac772232d6a06c08e76074393b153e9
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104663997"
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a>如何：向 Viewbox 的内容应用 Stretch 属性
## <a name="example"></a>示例  
 此示例演示如何更改的和属性的值 <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> <xref:System.Windows.Controls.Viewbox.Stretch%2A> <xref:System.Windows.Controls.Viewbox> 。  
  
 第一个示例使用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 定义 <xref:System.Windows.Controls.Viewbox> 元素。 它分配一个 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 和 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 400。 该示例将嵌套 <xref:System.Windows.Controls.Image> 中的一个元素 <xref:System.Windows.Controls.Viewbox> 。 <xref:System.Windows.Controls.Button> 与和枚举的属性值相对应的 <xref:System.Windows.Controls.Viewbox.Stretch%2A> 元素 <xref:System.Windows.Controls.StretchDirection> 处理嵌套的拉伸行为 <xref:System.Windows.Controls.Image> 。  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 下面的代码隐藏文件处理前面的 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 示例定义的事件 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Viewbox>
- <xref:System.Windows.Media.Stretch>
- <xref:System.Windows.Controls.StretchDirection>
