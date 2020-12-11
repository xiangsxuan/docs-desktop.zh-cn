---
title: 如何：对 FrameworkElement 的大小进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
ms.openlocfilehash: d1995deec5ab2c9bf405911af43b4d242d599119
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971927"
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a>如何：对 FrameworkElement 的大小进行动画处理
若要对的大小进行动画处理 <xref:System.Windows.FrameworkElement> ，可以对其和属性进行动画处理， <xref:System.Windows.FrameworkElement.Width%2A> 也可以 <xref:System.Windows.FrameworkElement.Height%2A> 使用动画 <xref:System.Windows.Media.ScaleTransform> 。  
  
 在下面的示例中，使用这两种方法对两个按钮的大小进行动画处理。 通过对一个按钮的属性进行动画处理来调整其大小 <xref:System.Windows.FrameworkElement.Width%2A> ，并通过 <xref:System.Windows.Media.ScaleTransform> 对应用于其属性的应用进行动画处理，从而调整 <xref:System.Windows.UIElement.RenderTransform%2A> 每个按钮都包含一些文本。 最初，这两个按钮中的文本在外观上都是相同的，但在调整按钮的大小时，第二个按钮中的文本会变为扭曲。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformanimations_snip#1](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 转换元素时，将转换整个元素及其内容。 当直接更改元素的大小时，如第一个按钮时，元素的内容不会调整大小，除非它们的大小和位置取决于其父元素的大小。  
  
 通过对元素的属性应用动态转换来对该元素的大小进行动画处理 <xref:System.Windows.UIElement.RenderTransform%2A> 可提供比动态和直接动画更好的性能 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> ，因为 <xref:System.Windows.UIElement.RenderTransform%2A> 属性不会触发布局处理过程。  
  
 有关对属性进行动画处理的详细信息，请参阅 [动画概述](../graphics-multimedia/animation-overview.md)。 有关转换的详细信息，请参阅 [转换概述](../graphics-multimedia/transforms-overview.md)。
