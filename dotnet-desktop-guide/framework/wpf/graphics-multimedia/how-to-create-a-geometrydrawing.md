---
title: 如何：创建 GeometryDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: f5cdcfdb68ad8030bcbd6c689f45a8baddd000e1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973511"
---
# <a name="how-to-create-a-geometrydrawing"></a>如何：创建 GeometryDrawing
此示例演示如何创建和显示 <xref:System.Windows.Media.GeometryDrawing> 。 利用， <xref:System.Windows.Media.GeometryDrawing> 你可以通过将和与关联来创建具有填充和轮廓的形状 <xref:System.Windows.Media.Pen> <xref:System.Windows.Media.Brush> <xref:System.Windows.Media.Geometry> 。 <xref:System.Windows.Media.GeometryDrawing.Geometry%2A>描述形状的结构， <xref:System.Windows.Media.GeometryDrawing.Brush%2A> 描述形状的填充，并 <xref:System.Windows.Media.GeometryDrawing.Pen%2A> 描述形状的轮廓。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.GeometryDrawing> 来呈现形状。 该形状由 <xref:System.Windows.Media.GeometryGroup> 和两个对象进行描述 <xref:System.Windows.Media.EllipseGeometry> 。 形状的内部将使用绘制 <xref:System.Windows.Media.LinearGradientBrush> ，并使用绘制其轮廓 <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen> 。 <xref:System.Windows.Media.GeometryDrawing>使用 <xref:System.Windows.Media.ImageDrawing> 和 <xref:System.Windows.Controls.Image> 元素显示。  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 下图显示了生成的 <xref:System.Windows.Media.GeometryDrawing> 。  
  
 ![两个椭圆形的 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
  
 若要创建更复杂的绘图，可以使用将多个绘图对象组合成单个复合绘图 <xref:System.Windows.Media.DrawingGroup> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.DrawingGroup>
- [Drawing 对象概述](drawing-objects-overview.md)
- [Geometry 概述](geometry-overview.md)
- [创建复合绘图](how-to-create-a-composite-drawing.md)
