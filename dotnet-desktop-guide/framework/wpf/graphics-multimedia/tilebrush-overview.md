---
title: TileBrush 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF]
- brushes [WPF], TileBrush
ms.assetid: aa4a7b7e-d09d-44c2-8d61-310c50e08d68
ms.openlocfilehash: 99bcc8695206030a381d71df2dda495867d3e9c7
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972744"
---
# <a name="tilebrush-overview"></a>TileBrush 概述
<xref:System.Windows.Media.TileBrush> 通过对象，您可以很好地控制如何使用图像、或来绘制区域 <xref:System.Windows.Media.Drawing> <xref:System.Windows.Media.Visual> 。 本主题介绍如何使用 <xref:System.Windows.Media.TileBrush> 功能来更好地控制 <xref:System.Windows.Media.ImageBrush> 、 <xref:System.Windows.Media.DrawingBrush> 或绘制区域的方式 <xref:System.Windows.Media.VisualBrush> 。  

<a name="prerequisite"></a>
## <a name="prerequisites"></a>先决条件  
 若要了解本主题，了解如何使用 <xref:System.Windows.Media.ImageBrush> 、或类的基本功能很有帮助 <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> 。 有关这些类型的介绍，请参阅 [使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。  
  
<a name="tilebrush"></a>
## <a name="painting-an-area-with-tiles"></a>使用图块绘制区域  
 <xref:System.Windows.Media.ImageBrush>是 <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> 对象的类型 <xref:System.Windows.Media.TileBrush> 。 使用平铺画笔，可以非常自如地控制如何使用图像、绘图或视觉对象来绘制区域。 例如，不使用单个拉伸图像绘制区域，而是使用创建图案的一系列平铺图像绘制区域。  
  
 使用平铺画笔绘制区域涉及三个组成部分：内容、基本图块和输出区域。  
  
 ![TileBrush 组成部分](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
具有单个图块的 TileBrush 的组成部分  
  
 ![已平铺的 TileBrush 组件](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
已指定图块的 TileMode 的 TileBrush 的组成部分  
  
 输出区域是要绘制的区域，如的或的 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Button> 。 下一部分介绍了的其他两个组件 <xref:System.Windows.Media.TileBrush> 。  
  
<a name="brushcontent"></a>
## <a name="brush-content"></a>画笔内容  
 有三种不同类型 <xref:System.Windows.Media.TileBrush> ，每个都使用不同的内容类型进行绘制。  
  
- 如果画笔为，则 <xref:System.Windows.Media.ImageBrush> 此内容为图像， <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 属性指定的内容 <xref:System.Windows.Media.ImageBrush> 。  
  
- 如果画笔为 <xref:System.Windows.Media.DrawingBrush> ，则此内容为绘图。 <xref:System.Windows.Media.DrawingBrush.Drawing%2A>属性指定的内容 <xref:System.Windows.Media.DrawingBrush> 。  
  
- 如果画笔为，则 <xref:System.Windows.Media.VisualBrush> 此内容为视觉对象。 <xref:System.Windows.Media.VisualBrush.Visual%2A>属性指定的内容 <xref:System.Windows.Media.VisualBrush> 。  
  
 可以通过使用属性来指定内容的位置和尺寸 <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.TileBrush.Viewbox%2A> ，不过，通常将 <xref:System.Windows.Media.TileBrush.Viewbox%2A> 设置为其默认值。 默认情况下， <xref:System.Windows.Media.TileBrush.Viewbox%2A> 配置为完全包含画笔的内容。 有关配置的详细信息 <xref:System.Windows.Controls.Viewbox> ，请参阅 <xref:System.Windows.Controls.Viewbox> 属性页。  
  
<a name="thebasetile"></a>
## <a name="the-base-tile"></a>基本图块  
 将 <xref:System.Windows.Media.TileBrush> 其内容投影到基本图块。 <xref:System.Windows.Media.TileBrush.Stretch%2A>属性控制如何 <xref:System.Windows.Media.TileBrush> 拉伸内容以填充基本图块。 <xref:System.Windows.Media.TileBrush.Stretch%2A>属性接受由枚举定义的下列值 <xref:System.Windows.Media.Stretch> ：  
  
- <xref:System.Windows.Media.Stretch.None>：不拉伸画笔的内容来填充磁贴。  
  
- <xref:System.Windows.Media.Stretch.Fill>：缩放画笔的内容以适应磁贴。 由于内容的高度和宽度独立进行缩放，因此内容的原始纵横比可能不会保留。 也就是说，为了完全填充输出图块，画笔的内容可能会弯曲。  
  
- <xref:System.Windows.Media.Stretch.Uniform>：缩放画笔的内容，使其完全适合磁贴。 内容的纵横比会保留。  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>：缩放画笔的内容，使其完全填充输出区域，同时保留内容的原始纵横比。  
  
 下图演示了不同的 <xref:System.Windows.Media.TileBrush.Stretch%2A> 设置。  
  
 ![不同的 TileBrush 拉伸设置](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
  
 在下面的示例中，将设置的内容， <xref:System.Windows.Media.ImageBrush> 使其不会拉伸以填充输出区域。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 默认情况下， <xref:System.Windows.Media.TileBrush> 会在基本图块 (生成单个磁贴) 并拉伸该磁贴以完全填充输出区域。 可以通过设置和属性来更改基本图块的大小和位置 <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 。  
  
<a name="basetilesize"></a>
### <a name="base-tile-size"></a>基本图块大小  
 <xref:System.Windows.Media.TileBrush.Viewport%2A>属性确定基本图块的大小和位置， <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 属性确定 <xref:System.Windows.Media.TileBrush.Viewport%2A> 是使用绝对坐标还是相对坐标来指定。 如果坐标是相对坐标，则它们相对于输出区域的大小。 点 (0,0) 表示输出区域的左上角，(1,1) 表示输出区域的右下角。 若要指定 <xref:System.Windows.Media.TileBrush.Viewport%2A> 属性使用绝对坐标，请将 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 属性设置为 <xref:System.Windows.Media.BrushMappingMode.Absolute> 。  
  
 下图显示了 <xref:System.Windows.Media.TileBrush> 与相对和绝对之间的输出之间的差异 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 。 请注意每个图都显示了一种图块图案；下一节介绍如何指定图块图案。  
  
 ![绝对和相对视区单位](./media/absolute-and-relative-viewports.png "absolute_and_relative_viewports")  
  
 在下面的示例中，使用一幅图像来创建一个宽度和高度均为 50% 的图块。 基本图块位于输出区域的 (0,0) 处。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 下一个示例将的平铺设置 <xref:System.Windows.Media.ImageBrush> 为25个与设备无关的像素。 因为 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 是绝对的，所以 <xref:System.Windows.Media.ImageBrush> 磁贴始终为 25 x 25 像素，而不考虑所绘制区域的大小。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>
### <a name="tiling-behavior"></a>平铺行为  
 <xref:System.Windows.Media.TileBrush>当其基本图块未完全填充输出区域，并且指定了平铺模式时，将生成平铺模式 <xref:System.Windows.Media.TileMode.None> 。 当图块画笔磁贴未完全填充输出区域时，它的 <xref:System.Windows.Media.TileBrush.TileMode%2A> 属性指定是否应重复基本图块来填充输出区域，如果是，则应复制基本图块。 <xref:System.Windows.Media.TileBrush.TileMode%2A>属性接受由枚举定义的下列值 <xref:System.Windows.Media.TileMode> ：  
  
- <xref:System.Windows.Media.TileMode.None>：仅绘制基本图块。  
  
- <xref:System.Windows.Media.TileMode.Tile>：绘制基本图块，并通过重复基本图块来填充剩余区域，以便一个图块的右边缘与下一个图块的左边缘相邻，并类似于下图和顶部。  
  
- <xref:System.Windows.Media.TileMode.FlipX>：与相同 <xref:System.Windows.Media.TileMode.Tile> ，但磁贴的交替列水平翻转。  
  
- <xref:System.Windows.Media.TileMode.FlipY>：与相同 <xref:System.Windows.Media.TileMode.Tile> ，但磁贴的交替行被垂直翻转。  
  
- <xref:System.Windows.Media.TileMode.FlipXY>：和的组合 <xref:System.Windows.Media.TileMode.FlipX> <xref:System.Windows.Media.TileMode.FlipY> 。  
  
 下图阐释了不同的平铺模式。  
  
 ![不同的 TileBrush TileMode 设置](./media/img-mmgraphics-tilemodes.gif "img_mmgraphics_tilemodes")  
  
 在下面的示例中，使用一个图像来绘制宽度为 100 像素并且高度为 100 像素的矩形。 通过将画笔的设置 <xref:System.Windows.Media.TileBrush.Viewport%2A> 设置为0，0，0.25，0.25，画笔的基本图块将变为1/4 输出区域。 画笔的 <xref:System.Windows.Media.TileBrush.TileMode%2A> 设置为 <xref:System.Windows.Media.TileMode.FlipXY> 。 这样它便可以用图块行来填充矩形。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [使用图像、图形和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
- [操作指南主题](brushes-how-to-topics.md)
- [Freezable 对象概述](../advanced/freezable-objects-overview.md)
- [ImageBrush 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [VisualBrush 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
