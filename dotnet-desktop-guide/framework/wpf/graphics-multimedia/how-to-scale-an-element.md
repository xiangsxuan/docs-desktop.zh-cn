---
title: 如何：缩放元素
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973216"
---
# <a name="how-to-scale-an-element"></a>如何：缩放元素
此示例演示如何使用 <xref:System.Windows.Media.ScaleTransform> 缩放元素。  
  
 使用 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 和 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 属性，按指定的因子调整元素的大小。 例如，如果 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 值为1.5，则将元素拉伸到其原始宽度的150%。 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>值0.5 将元素的高度缩减50%。  
  
 使用 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 和 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 属性来指定缩放操作的中心点。 默认情况下，在 <xref:System.Windows.Media.ScaleTransform> (0，0) 点居中，这对应于矩形的左上角。 这会使元素移动并使其显得更大，因为当应用时 <xref:System.Windows.Media.Transform> ，将更改对象所在的坐标空间。  
  
 下面的示例使用将 <xref:System.Windows.Media.ScaleTransform> 50 50 的大小加倍 <xref:System.Windows.Shapes.Rectangle> 。 的 <xref:System.Windows.Media.ScaleTransform> 值为 0 (和的默认) <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 通常情况下，将 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 和设置 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 为缩放的对象中心： (<xref:System.Windows.FrameworkElement.Width%2A> /2， <xref:System.Windows.FrameworkElement.Height%2A> /2) 。  
  
 下面的示例演示另一种 <xref:System.Windows.Shapes.Rectangle> 大小为两倍的; 但是， <xref:System.Windows.Media.ScaleTransform> 对于 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 和 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> （对应于矩形的中心），此值的值为25。  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 下图显示了这两个操作之间的差异 <xref:System.Windows.Media.ScaleTransform> 。 虚线显示的是矩形在缩放之前的大小和位置。  
  
 ![以不同中心点进行的 2 倍缩放](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")  
两个具有相同 ScaleX 和 ScaleY 值但中心不同的 ScaleTransform 操作  
  
 有关完整示例，请参阅 [2D 转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [转换概述](transforms-overview.md)
- [操作指南主题](transformations-how-to-topics.md)
