---
title: 使用图像、图形和视觉对象进行绘制
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- painting [WPF], with images
- painting with visuals [WPF]
- brushes [WPF], painting with images
- brushes [WPF], painting with visuals
ms.assetid: 779aac3f-8d41-49d8-8130-768244aa2240
ms.openlocfilehash: 292f9dcdb6d3ccbb6a3c7192ea6ba44a099ec5d5
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970831"
---
# <a name="painting-with-images-drawings-and-visuals"></a>使用图像、图形和视觉对象进行绘制
本主题说明如何使用 <xref:System.Windows.Media.ImageBrush> 、 <xref:System.Windows.Media.DrawingBrush> 和 <xref:System.Windows.Media.VisualBrush> 对象绘制带有图像、 <xref:System.Windows.Media.Drawing> 或的区域 <xref:System.Windows.Media.Visual> 。  

<a name="prereqs"></a>
## <a name="prerequisites"></a>先决条件  
 要了解本主题，应熟悉 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 提供的不同画笔类型及其基本功能。 有关介绍，请参阅 [WPF 画笔概述](wpf-brushes-overview.md)。  
  
<a name="image"></a>
## <a name="paint-an-area-with-an-image"></a>使用图像绘制区域  
 <xref:System.Windows.Media.ImageBrush>使用绘制区域 <xref:System.Windows.Media.ImageSource> 。 与一起使用的最常见类型 <xref:System.Windows.Media.ImageSource> <xref:System.Windows.Media.ImageBrush> 是 <xref:System.Windows.Media.Imaging.BitmapImage> ，它描述位图图形。 您可以使用 <xref:System.Windows.Media.DrawingImage> 来绘制 <xref:System.Windows.Media.Drawing> 对象，但使用是更简单的方法 <xref:System.Windows.Media.DrawingBrush> 。 有关对象的详细信息 <xref:System.Windows.Media.ImageSource> ，请参阅 [图像处理概述](imaging-overview.md)。  
  
 若要使用绘制 <xref:System.Windows.Media.ImageBrush> ，请创建 <xref:System.Windows.Media.Imaging.BitmapImage> 并使用它来加载位图内容。 然后，使用 <xref:System.Windows.Media.Imaging.BitmapImage> 设置的 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 属性 <xref:System.Windows.Media.ImageBrush> 。 最后，将应用 <xref:System.Windows.Media.ImageBrush> 到要绘制的对象。  在中 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，您还可以将 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 的属性设置 <xref:System.Windows.Media.ImageBrush> 为要加载的图像的路径。  
  
 与所有 <xref:System.Windows.Media.Brush> 对象一样， <xref:System.Windows.Media.ImageBrush> 可用于绘制对象（如形状、面板、控件和文本）。 下图显示了可使用实现的一些效果 <xref:System.Windows.Media.ImageBrush> 。  
  
 ![ImageBrush 输出示例](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
使用 ImageBrush 绘制的对象  
  
 默认情况下， <xref:System.Windows.Media.ImageBrush> 拉伸图像以完全填充要绘制的区域，这可能会使图像在绘制区域与图像的长宽比时扭曲。 可以通过将 <xref:System.Windows.Media.TileBrush.Stretch%2A> 属性从其默认值更改 <xref:System.Windows.Media.Stretch.Fill> 为 <xref:System.Windows.Media.Stretch.None> 、或来更改 <xref:System.Windows.Media.Stretch.Uniform> 此行为 <xref:System.Windows.Media.Stretch.UniformToFill> 。 由于 <xref:System.Windows.Media.ImageBrush> 是的一种类型 <xref:System.Windows.Media.TileBrush> ，因此你可以精确指定图像画笔如何填充输出区域，甚至还可以创建图案。 有关高级功能的详细信息 <xref:System.Windows.Media.TileBrush> ，请参阅 [TileBrush 概述](tilebrush-overview.md)。  
  
<a name="fillingpanelwithimage"></a>
## <a name="example-paint-an-object-with-a-bitmap-image"></a>示例：用位图图像绘制对象  
 下面的示例使用 <xref:System.Windows.Media.ImageBrush> 绘制 <xref:System.Windows.Controls.Panel.Background%2A> 的 <xref:System.Windows.Controls.Canvas> 。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>
## <a name="paint-an-area-with-a-drawing"></a>使用图形绘制区域  
 利用， <xref:System.Windows.Media.DrawingBrush> 您可以使用形状、文本、图像和视频绘制一个区域。 绘图画笔内的形状本身可能使用纯色、渐变、图像甚至另一种颜色进行绘制 <xref:System.Windows.Media.DrawingBrush> 。 下图演示了的某些用法 <xref:System.Windows.Media.DrawingBrush> 。  
  
 ![DrawingBrush 输出示例](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
使用 DrawingBrush 绘制的对象  
  
 <xref:System.Windows.Media.DrawingBrush>使用对象绘制区域 <xref:System.Windows.Media.Drawing> 。 <xref:System.Windows.Media.Drawing>对象描述可见内容，如形状、位图、视频或文本行。 不同类型的图形描述不同类型的内容。 下面是不同类型图形对象的列表。  
  
- <xref:System.Windows.Media.GeometryDrawing> –绘制形状。  
  
- <xref:System.Windows.Media.ImageDrawing> –绘制图像。  
  
- <xref:System.Windows.Media.GlyphRunDrawing> –绘制文本。  
  
- <xref:System.Windows.Media.VideoDrawing> –播放音频或视频文件。  
  
- <xref:System.Windows.Media.DrawingGroup> –绘制其他绘图。 使用图形组将其他图形合并到单个复合图形。  
  
 有关对象的详细信息 <xref:System.Windows.Media.Drawing> ，请参阅 [绘图对象概述](drawing-objects-overview.md)。  
  
 像一样 <xref:System.Windows.Media.ImageBrush> ，会对 <xref:System.Windows.Media.DrawingBrush> 其 <xref:System.Windows.Media.DrawingBrush.Drawing%2A> 进行拉伸以填充其输出区域。 可以通过 <xref:System.Windows.Media.TileBrush.Stretch%2A> 从的默认设置中更改属性来重写此行为 <xref:System.Windows.Media.Stretch.Fill> 。 有关更多信息，请参见 <xref:System.Windows.Media.TileBrush.Stretch%2A> 属性。  
  
<a name="fillingareawithdrawingbrushexample"></a>
## <a name="example-paint-an-object-with-a-drawing"></a>示例：使用图形绘制对象  
 下面的示例显示如何使用三个椭圆形的图形绘制对象。 <xref:System.Windows.Media.GeometryDrawing>用于描述省略号。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>
## <a name="paint-an-area-with-a-visual"></a>使用视觉对象绘制区域  
 所有画笔的功能最多且功能强大， <xref:System.Windows.Media.VisualBrush> 可使用绘制一个区域 <xref:System.Windows.Media.Visual> 。 <xref:System.Windows.Media.Visual>是一种低级别图形类型，用作许多有用图形组件的上级。 例如， <xref:System.Windows.Window> 、 <xref:System.Windows.FrameworkElement> 和 <xref:System.Windows.Controls.Control> 类都是对象的类型 <xref:System.Windows.Media.Visual> 。 使用 <xref:System.Windows.Media.VisualBrush> ，可以绘制几乎任何图形对象的区域 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。  
  
> [!NOTE]
> 尽管 <xref:System.Windows.Media.VisualBrush> 是对象的一种类型 <xref:System.Windows.Freezable> ，但在 <xref:System.Windows.Media.VisualBrush.Visual%2A> 将其属性设置为之外的值时，不能将其冻结 (成为只读) `null` 。  
  
 可以通过两种方式来指定的 <xref:System.Windows.Media.VisualBrush.Visual%2A> 内容 <xref:System.Windows.Media.VisualBrush> 。  
  
- 创建一个新的 <xref:System.Windows.Media.Visual> ，并使用它来设置 <xref:System.Windows.Media.VisualBrush.Visual%2A> 的属性 <xref:System.Windows.Media.VisualBrush> 。 有关示例，请参阅后面的[示例：使用视觉对象绘制对象](#examplevisualbrush1)一节。  
  
- 使用现有的 <xref:System.Windows.Media.Visual> ，它创建目标的重复映像 <xref:System.Windows.Media.Visual> 。 然后，可以使用 <xref:System.Windows.Media.VisualBrush> 来创建有趣的效果，如反射和放大。 有关示例，请参阅[示例：创建反射](#examplevisualbrush2)一节。  
  
 当你为指定的新 <xref:System.Windows.Media.VisualBrush.Visual%2A> <xref:System.Windows.Media.VisualBrush> 并为 <xref:System.Windows.Media.Visual> <xref:System.Windows.UIElement> (如面板或控件) 时，布局系统将在及其子元素上运行（ <xref:System.Windows.UIElement> 当 <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> 属性设置为时） `true` 。 不过，该根 <xref:System.Windows.UIElement> 实质上与系统的其余部分隔离：样式，而外部布局不能渗透此边界。 因此，您应显式指定根的大小 <xref:System.Windows.UIElement> ，因为它的唯一父级为， <xref:System.Windows.Media.VisualBrush> 因此它无法自动调整自身的大小。 有关 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 中的布局的更多信息，请参阅[布局](../advanced/layout.md)。  
  
 与 <xref:System.Windows.Media.ImageBrush> 和一样  <xref:System.Windows.Media.DrawingBrush> ，会 <xref:System.Windows.Media.VisualBrush> 拉伸其内容来填充输出区域。 可以通过 <xref:System.Windows.Media.TileBrush.Stretch%2A> 从的默认设置中更改属性来重写此行为 <xref:System.Windows.Media.Stretch.Fill> 。 有关更多信息，请参见 <xref:System.Windows.Media.TileBrush.Stretch%2A> 属性。  
  
<a name="examplevisualbrush1"></a>
## <a name="example-paint-an-object-with-a-visual"></a>示例：使用视觉对象绘制对象  
 在下面的示例中，许多控件和面板用于绘制矩形。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>
## <a name="example-create-a-reflection"></a>示例：创建反射  
 前面的示例演示了如何创建新 <xref:System.Windows.Media.Visual> 的以用作背景。 你还可以使用 <xref:System.Windows.Media.VisualBrush> 来显示现有视觉对象; 此功能使你能够生成有趣的视觉效果，例如反射和放大。 下面的示例使用 <xref:System.Windows.Media.VisualBrush> 创建 <xref:System.Windows.Controls.Border> 包含多个元素的的反射。 下图显示了此示例生成的输出。  
  
 ![反射的 Visual 对象](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
反射的 Visual 对象  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 有关显示如何放大屏幕部分以及如何创建反射的更多示例，请参阅 [VisualBrush 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)。  
  
<a name="tilebrush"></a>
## <a name="tilebrush-features"></a>TileBrush 功能  
 <xref:System.Windows.Media.ImageBrush>、 <xref:System.Windows.Media.DrawingBrush> 和 <xref:System.Windows.Media.VisualBrush> 是对象的类型 <xref:System.Windows.Media.TileBrush> 。 <xref:System.Windows.Media.TileBrush> 通过对象，您可以很好地控制如何使用图像、绘图或视觉对象绘制区域。 例如，不使用单个拉伸图像绘制区域，而是使用创建图案的一系列平铺图像绘制区域。  
  
 <xref:System.Windows.Media.TileBrush>有三个主要组件：内容、磁贴和输出区域。  
  
 ![TileBrush 组成部分](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
具有单个图块的 TileBrush 的组成部分  
  
 ![已平铺的 TileBrush 组件](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
使用多个平铺的 TileBrush 组件  
  
 有关对象的平铺功能的详细信息 <xref:System.Windows.Media.TileBrush> ，请参阅 [TileBrush 概述](tilebrush-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [TileBrush 概述](tilebrush-overview.md)
- [WPF 画笔概述](wpf-brushes-overview.md)
- [图像处理概述](imaging-overview.md)
- [Drawing 对象概述](drawing-objects-overview.md)
- [不透明蒙板概述](opacity-masks-overview.md)
- [WPF 图形呈现疑难解答](wpf-graphics-rendering-overview.md)
- [ImageBrush 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [VisualBrush 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
