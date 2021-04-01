---
title: 如何：使用 Drawing 绘制区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
ms.openlocfilehash: 6b204ae631912181333e2559ebadcdc37e7693b7
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974089"
---
# <a name="how-to-paint-an-area-with-a-drawing"></a>如何：使用 Drawing 绘制区域
本示例演示如何使用 Drawing 绘制一个区域。 若要绘制带有绘图的区域，请使用 <xref:System.Windows.Media.DrawingBrush> 和一个或多个 <xref:System.Windows.Media.Drawing> 对象。   下面的示例使用绘制一个 <xref:System.Windows.Media.DrawingBrush> 具有两个椭圆绘图的对象。  
  
## <a name="example"></a>示例  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 下图显示该示例的输出。  
  
 ![DrawingBrush 的输出](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")  
  
 由于     [控制复合形状的填充](how-to-control-the-fill-of-a-composite-shape.md)中所述的原因， (形状的中心为白色。 )   
  
 通过设置 <xref:System.Windows.Media.DrawingBrush> 对象的 <xref:System.Windows.Media.TileBrush.Viewport%2A> 和 <xref:System.Windows.Media.TileBrush.TileMode%2A> 属性，您可以创建一个重复模式。 以下示例使用基于由两个椭圆组成的 Drawing 创建的图案绘制一个对象。  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 下图显示了平铺的 <xref:System.Windows.Media.DrawingBrush> 输出。  
  
 ![DrawingBrush 的平铺输出](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")  
  
 有关绘制画笔的详细信息，请参阅 [利用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。 有关对象的详细信息 <xref:System.Windows.Media.Drawing> ，请参阅 [绘图对象概述](drawing-objects-overview.md)。
