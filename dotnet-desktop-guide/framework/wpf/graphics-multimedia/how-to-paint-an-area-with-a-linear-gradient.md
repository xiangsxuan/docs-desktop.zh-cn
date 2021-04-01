---
title: 如何：绘制带有线性渐变的区域
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 76c491632911c48db34d932ba3895278591378a5
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972078"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>如何：绘制带有线性渐变的区域
此示例演示如何使用 <xref:System.Windows.Media.LinearGradientBrush> 类绘制带有线性渐变的区域。 在下面的示例中，的将 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle> 使用从黄色到红色转换为蓝色到浅绿色的对角线性渐变进行绘制。  
  
## <a name="example"></a>示例  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 下图显示了上一示例创建的渐变。  
  
 ![对角线方向线性渐变](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")  
  
 若要创建水平线性渐变，请将的 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 和更改 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> <xref:System.Windows.Media.LinearGradientBrush> 为 (0，0.5) 并 (1，0.5) 。 在下面的示例中， <xref:System.Windows.Shapes.Rectangle> 使用水平线性渐变绘制。  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 下图显示了上一示例创建的渐变。  
  
 ![水平线性渐变](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")  
  
 若要创建垂直线性渐变，请将 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> 的和更改 <xref:System.Windows.Media.LinearGradientBrush> 为 (0.5，0) 并 (0.5，1) 。 在下面的示例中， <xref:System.Windows.Shapes.Rectangle> 用垂直线性渐变绘制。  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 下图显示了上一示例创建的渐变。  
  
 ![垂直线性渐变](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")  
  
> [!NOTE]
> 本主题中的示例使用默认坐标系统来设置起始点和终结点。 默认坐标系与边界框相关：0指示边界框的0%，1指示边界框的100%。 您可以通过将属性设置为值来更改此坐标系统 <xref:System.Windows.Media.GradientBrush.MappingMode%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType> 。 绝对坐标系与范围框无关。 值直接在本地空间中解释。  
  
 有关其他示例，请参阅 [画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。 有关渐变和其他类型画笔的详细信息，请参阅 [采用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)。
