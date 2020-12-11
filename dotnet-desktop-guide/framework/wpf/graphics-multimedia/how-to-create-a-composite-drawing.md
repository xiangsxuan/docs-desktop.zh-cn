---
title: 如何：创建复合绘图
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: 0af7fbca593627ebe8cd102a02617a27eac50aa5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974128"
---
# <a name="how-to-create-a-composite-drawing"></a>如何：创建复合绘图
此示例演示如何 <xref:System.Windows.Media.DrawingGroup> 通过将多个 <xref:System.Windows.Media.Drawing> 对象组合成单个复合绘图来使用来创建复杂的绘图。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.DrawingGroup> 从和对象创建复合绘图 <xref:System.Windows.Media.GeometryDrawing> <xref:System.Windows.Media.ImageDrawing> 。 下图显示了此示例生成的输出。  
  
 ![具有多个绘图的 DrawingGroup](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
使用 DrawingGroup 创建的复合绘图  
  
 请注意显示绘图边界的灰色边框。  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 你可以使用将 <xref:System.Windows.Media.DrawingGroup> <xref:System.Windows.Media.DrawingGroup.Transform%2A> 、 <xref:System.Windows.Media.DrawingGroup.Opacity%2A> 设置、、或应用 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A> 于 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A> <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> 它包含的绘图。 因为 <xref:System.Windows.Media.DrawingGroup> 也是 <xref:System.Windows.Media.Drawing> ，所以它可以包含其他 <xref:System.Windows.Media.DrawingGroup> 对象。  
  
 下面的示例与前面的示例类似，不同之处在于它使用其他 <xref:System.Windows.Media.DrawingGroup> 对象将位图效果和不透明蒙板应用于其部分绘图。 下图显示了此示例生成的输出。  
  
 ![具有多个绘图的 DrawingGroup](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")  
具有多个 DrawingGroup 对象的复合绘图  
  
 请注意显示绘图边界的灰色边框。  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 有关对象的详细信息 <xref:System.Windows.Media.Drawing> ，请参阅 [绘图对象概述](drawing-objects-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>
- <xref:System.Windows.Media.DrawingGroup.Transform%2A>
- <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>
- <xref:System.Windows.Media.DrawingGroup.Opacity%2A>
- <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>
- <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>
- [Drawing 对象概述](drawing-objects-overview.md)
