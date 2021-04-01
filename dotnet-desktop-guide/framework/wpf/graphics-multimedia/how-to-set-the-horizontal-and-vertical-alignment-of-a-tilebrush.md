---
title: 如何：设置 TileBrush 的水平对齐方式和垂直对齐方式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], alignment of
- vertical alignment of TileBrushes [WPF]
- aligning [WPF], TileBrushes
- horizontal alignment of Tilebrushes [WPF]
ms.assetid: 65ae89bd-9246-4c9e-bde4-2fb991d4060d
ms.openlocfilehash: e3bfb2b209e40c435c3a321c874dfbd7a9a2fd50
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971014"
---
# <a name="how-to-set-the-horizontal-and-vertical-alignment-of-a-tilebrush"></a>如何：设置 TileBrush 的水平对齐方式和垂直对齐方式
本示例演示如何控制平铺内容的水平对齐方式和垂直对齐方式。 若要控制的水平和垂直对齐方式 <xref:System.Windows.Media.TileBrush> ，请使用其 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 和 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 属性。  
  
 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 如果满足以下任一条件，则使用的和属性 <xref:System.Windows.Media.TileBrush> ：  
  
- <xref:System.Windows.Media.TileBrush.Stretch%2A>属性为 <xref:System.Windows.Media.Stretch.Uniform> 或 <xref:System.Windows.Media.Stretch.UniformToFill> ， <xref:System.Windows.Media.TileBrush.Viewbox%2A> 且和 <xref:System.Windows.Media.TileBrush.Viewport%2A> 具有不同的纵横比。  
  
- <xref:System.Windows.Media.TileBrush.Stretch%2A>属性为 <xref:System.Windows.Media.Stretch.None> ， <xref:System.Windows.Media.TileBrush.Viewbox%2A> 并且和的 <xref:System.Windows.Media.TileBrush.Viewport%2A> 大小不同。  
  
## <a name="example"></a>示例  
 下面的示例将的内容（即 <xref:System.Windows.Media.DrawingBrush> 类型 <xref:System.Windows.Media.TileBrush> ）与磁贴的左上角对齐。 为了对齐内容，该示例将 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 的属性设置 <xref:System.Windows.Media.DrawingBrush> 为 <xref:System.Windows.Media.AlignmentX.Left> ，并将 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 属性设置为 <xref:System.Windows.Media.AlignmentY.Top> 。 本示例生成以下输出。  
  
 ![左上角对齐的 TileBrush](./media/graphicsmm-tilebrushalignmentexampletopleft.png "graphicsmm_TileBrushAlignmentExampleTopLeft")  
内容与左上角对齐的 TileBrush  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmentinline)]  
  
## <a name="example"></a>示例  
 下面的示例 <xref:System.Windows.Media.DrawingBrush> 通过将 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 属性设置为 <xref:System.Windows.Media.AlignmentX.Right> 并将属性设置为，将的内容与其磁贴的右下角对齐 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> <xref:System.Windows.Media.AlignmentY.Bottom> 。 该示例生成以下输出。  
  
 ![右下角对齐的 TileBrush](./media/graphicsmm-tilebrushalignmentexamplebottomright.png "graphicsmm_TileBrushAlignmentExampleBottomRight")  
内容与右下角对齐的 TileBrush  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
## <a name="example"></a>示例  
 下面的示例 <xref:System.Windows.Media.DrawingBrush> 通过将 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 属性设置为 <xref:System.Windows.Media.AlignmentX.Left> 并将属性设置为，将的内容与其磁贴的左上角对齐 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> <xref:System.Windows.Media.AlignmentY.Top> 。 它还会设置的 <xref:System.Windows.Media.TileBrush.Viewport%2A> 和， <xref:System.Windows.Media.TileBrush.TileMode%2A> <xref:System.Windows.Media.DrawingBrush> 以生成平铺模式。 该示例生成以下输出。  
  
 ![左上角对齐的平铺 TileBrush](./media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "graphicsmm_TileBrushAlignmentExampleTopLeftTiled")  
内容与基本平铺图案的左上角对齐的平铺图案  
  
 上图突出显示了基本平铺图案，以便显示其内容的对齐方式。 请注意，该 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 设置不起作用，因为的内容会 <xref:System.Windows.Media.DrawingBrush> 水平完全填充基本磁贴。  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmenttiledinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmenttiledinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmenttiledinline)]  
  
## <a name="example"></a>示例  
 最终的示例 <xref:System.Windows.Media.DrawingBrush> 通过将 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 属性设置为 <xref:System.Windows.Media.AlignmentX.Right> ，并将属性设置为，将平铺的内容对齐到其基本图块的右下方 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> <xref:System.Windows.Media.AlignmentY.Bottom> 。 该示例生成以下输出。  
  
 ![右下角对齐的平铺 TileBrush](./media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "graphicsmm_TileBrushAlignmentExampleBottomRightTiled")  
内容与基本平铺图案的右下角对齐的平铺图案  
  
 同样，该 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 设置不起作用，因为的内容会在 <xref:System.Windows.Media.DrawingBrush> 水平方向上完全填充基本磁贴。  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
 这些示例使用 <xref:System.Windows.Media.DrawingBrush> 对象来演示如何 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 使用和 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 属性。 这些属性对于所有图块画笔的行为都是相同的： <xref:System.Windows.Media.DrawingBrush> 、 <xref:System.Windows.Media.ImageBrush> 和 <xref:System.Windows.Media.VisualBrush> 。 有关平铺画笔的详细信息，请参阅[使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.VisualBrush>
- [使用图像、图形和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
