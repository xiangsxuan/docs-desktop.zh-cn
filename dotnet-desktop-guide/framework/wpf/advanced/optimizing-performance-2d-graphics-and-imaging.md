---
title: 优化性能：二维图形和图像处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], performance
- drawing [WPF], optimizing performance
- imaging [WPF], optimizing performance
- shapes [WPF], optimizing performance
- 2D graphics [WPF]
- images [WPF], optimizing performance
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
ms.openlocfilehash: c6a595be9ff982a1f48e3d1ed193f6b4465c4e50
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666883"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>优化性能：二维图形和图像处理
[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供了多种可按应用程序要求进行优化的二维图形和图像处理功能。 本主题提供有关这些方面性能优化的信息。  

<a name="Drawing_and_Shapes"></a>
## <a name="drawing-and-shapes"></a>绘图和形状  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 同时提供 <xref:System.Windows.Media.Drawing> 和 <xref:System.Windows.Shapes.Shape> 对象来表示图形绘制内容。 但是， <xref:System.Windows.Media.Drawing> 对象比对象更简单， <xref:System.Windows.Shapes.Shape> 并提供更好的性能特征。  
  
 <xref:System.Windows.Shapes.Shape>允许您在屏幕上绘制图形形状。 由于它们是从类派生的 <xref:System.Windows.FrameworkElement> ，因此 <xref:System.Windows.Shapes.Shape> 可以在面板和大多数控件内使用对象。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 为图形和绘制服务提供多层访问。 在顶层， <xref:System.Windows.Shapes.Shape> 对象易于使用，并提供许多有用的功能，如布局和事件处理。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供了许多现成可用的形状对象。 所有形状对象均从 <xref:System.Windows.Shapes.Shape> 类继承。 可用形状对象包括 <xref:System.Windows.Shapes.Ellipse> 、 <xref:System.Windows.Shapes.Line> 、 <xref:System.Windows.Shapes.Path> 、 <xref:System.Windows.Shapes.Polygon> 、 <xref:System.Windows.Shapes.Polyline> 和 <xref:System.Windows.Shapes.Rectangle> 。  
  
 <xref:System.Windows.Media.Drawing> 另一方面，对象不是从类派生的， <xref:System.Windows.FrameworkElement> 并且提供了用于呈现形状、图像和文本的较轻量实现。  
  
 有四种类型的 <xref:System.Windows.Media.Drawing> 对象：  
  
- <xref:System.Windows.Media.GeometryDrawing> 绘制形状。  
  
- <xref:System.Windows.Media.ImageDrawing> 绘制图像。  
  
- <xref:System.Windows.Media.GlyphRunDrawing> 绘制文本。  
  
- <xref:System.Windows.Media.DrawingGroup> 绘制其他绘图。 使用图形组将其他图形合并到单个复合图形。  
  
 <xref:System.Windows.Media.GeometryDrawing>对象用于呈现几何图形内容。 <xref:System.Windows.Media.Geometry>派生自该类的类和具体类（如 <xref:System.Windows.Media.CombinedGeometry> 、 <xref:System.Windows.Media.EllipseGeometry> 和 <xref:System.Windows.Media.PathGeometry> ）提供了一种方式来呈现2d 图形和提供命中测试和剪裁支持。 几何对象可用于定义控件的区域或定义应用于图像的剪裁区域等。 几何对象可以是简单区域（例如矩形和圆形），或者是由两个或多个几何对象创建的复合区域。 可以通过组合派生的对象（如、和）来创建更复杂的几何区域 <xref:System.Windows.Media.PathSegment> <xref:System.Windows.Media.ArcSegment> <xref:System.Windows.Media.BezierSegment> <xref:System.Windows.Media.QuadraticBezierSegment> 。  
  
 在图面上， <xref:System.Windows.Media.Geometry> 类和 <xref:System.Windows.Shapes.Shape> 类是类似的。 两者均用于2D 图形的呈现，它们都具有派生自它们的相似具体类，例如 <xref:System.Windows.Media.EllipseGeometry> 和 <xref:System.Windows.Shapes.Ellipse> 。 但是，这两个类集之间存在重大区别。 对于一个类， <xref:System.Windows.Media.Geometry> 该类缺少类的某些功能 <xref:System.Windows.Shapes.Shape> ，例如能够自行绘制功能。 若要绘制几何对象，必须使用另一个类（例如 DrawingContext、Drawing 或 Path（值得注意的是 Path 是一个 Shape））来执行绘制操作。 填充、笔划和笔划粗细等呈现属性位于绘制 geometry 对象的类上，而 shape 对象则包含这些属性。 考虑这种差异的一种方法是，geometry 对象定义一个区域（例如一个圆），而形状对象定义一个区域，定义该区域的填充方式，并参与布局系统。  
  
 由于 <xref:System.Windows.Shapes.Shape> 对象派生自 <xref:System.Windows.FrameworkElement> 类，因此使用它们可能会增加应用程序中的内存消耗。 如果你确实不需要 <xref:System.Windows.FrameworkElement> 图形内容的功能，请考虑使用较轻量的 <xref:System.Windows.Media.Drawing> 对象。  
  
 有关对象的详细信息 <xref:System.Windows.Media.Drawing> ，请参阅 [绘图对象概述](../graphics-multimedia/drawing-objects-overview.md)。  
  
<a name="StreamGeometry_Objects"></a>
## <a name="streamgeometry-objects"></a>StreamGeometry 对象  
 <xref:System.Windows.Media.StreamGeometry>对象是 <xref:System.Windows.Media.PathGeometry> 用于创建几何形状的轻型替代项。 <xref:System.Windows.Media.StreamGeometry>需要描述复杂几何时使用。 <xref:System.Windows.Media.StreamGeometry> 针对处理多个对象进行了优化 <xref:System.Windows.Media.PathGeometry> ，与使用多个单独的对象相比，其性能更佳 <xref:System.Windows.Media.PathGeometry> 。  
  
 下面的示例使用特性语法在中创建一个 <xref:System.Windows.Media.StreamGeometry> 三角形 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 有关对象的详细信息 <xref:System.Windows.Media.StreamGeometry> ，请参阅 [使用 System.windows.media.streamgeometry> 创建形状](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md)。  
  
<a name="DrawingVisual_Objects"></a>
## <a name="drawingvisual-objects"></a>DrawingVisual 对象  
 <xref:System.Windows.Media.DrawingVisual>对象是一个轻量绘图类，用于呈现形状、图像或文本。 此类之所以为轻量类是因为它不提供布局或事件处理，从而性能得以提升。 因此，绘图非常适用于背景和剪贴画。 有关详细信息，请参阅[使用 DrawingVisual 对象](../graphics-multimedia/using-drawingvisual-objects.md)。  
  
<a name="Images"></a>
## <a name="images"></a>映像  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 与早期版本的 Windows 中的映像功能相比，映像提供了显著改进。 图像处理功能（如在公共控件上显示位图或使用图像）主要由 Microsoft Windows 图形设备接口 (GDI) 或 Microsoft Windows GDI + 应用程序编程接口 (API) 来处理。 这些 Api 提供了基线映像功能，但缺乏功能，如支持编解码器扩展性和高保真图像支持。 WPF 映像 Api 已经过重新设计，以克服 GDI 和 GDI + 的缺点，并提供一组新的 Api，用于在应用程序中显示和使用图像。  
  
 使用图像时，为使性能更佳，请考虑以下建议：  
  
- 如果应用程序要求显示缩略图，请考虑创建一个缩略版图像。 默认情况下，[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 会加载图像并将其解码到最大尺寸。 如果仅需要缩略版本图像，[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 会先将图像解码为完整尺寸，然后将其缩放为缩略图大小，这个过程是多余的。 若要避免此多余的过程，可请求 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 将图像解码到缩略图大小，或者请求 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 加载缩略图大小的图像。  
  
- 请务必将图像解码到所需大小而不是默认大小。 如上所述，请求 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 将图像解码为所需大小而不是默认的最大尺寸。 这样不仅会减小应用程序的工作集，还会减慢其执行速度。  
  
- 如果可能，请将多个图像合并到单个图像中，例如由多个图像构成的胶卷条。  
  
- 有关详细信息，请参阅 [图像概述](../graphics-multimedia/imaging-overview.md)。  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 当对任何位图的刻度进行动画处理时，默认的高质量图像重新采样算法有时会消耗足够的系统资源来导致帧速率下降，从而有效地导致动画变慢。 通过将 <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> 对象的属性设置 <xref:System.Windows.Media.RenderOptions> 为 <xref:System.Windows.Media.BitmapScalingMode.LowQuality> ，可以在缩放位图时创建更流畅的动画。 <xref:System.Windows.Media.BitmapScalingMode.LowQuality> 模式指示在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 处理图像时，呈现引擎从质量优化算法切换到速度优化算法。  
  
 下面的示例演示如何设置 <xref:System.Windows.Media.BitmapScalingMode> 图像对象的。  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 默认情况下，不 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 会缓存对象的呈现内容 <xref:System.Windows.Media.TileBrush> ，例如 <xref:System.Windows.Media.DrawingBrush> 和 <xref:System.Windows.Media.VisualBrush> 。 在场景中的内容或使用不会改变的静态方案中， <xref:System.Windows.Media.TileBrush> 这有意义，因为它可节省视频内存。 如果以 <xref:System.Windows.Media.TileBrush> 非静态方式使用静态内容（例如，当静态 <xref:System.Windows.Media.DrawingBrush> 或 <xref:System.Windows.Media.VisualBrush> 映射到旋转三维对象的图面时），则此方法不会有多大意义。 的默认行为 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 是为每个帧重新呈现的全部内容 <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> ，即使内容不变，也是如此。  
  
 通过将 <xref:System.Windows.Media.RenderOptions.CachingHint%2A> 对象的属性设置 <xref:System.Windows.Media.RenderOptions> 为 <xref:System.Windows.Media.CachingHint.Cache> ，可以使用平铺画笔对象的缓存版本来提高性能。  
  
 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A>和 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> 属性值是相对大小的值，用于确定当 <xref:System.Windows.Media.TileBrush> 对象因刻度的变化而应重新生成的时间。 例如，通过将属性设置 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> 为2.0， <xref:System.Windows.Media.TileBrush> 只需在其大小超过当前缓存大小的两倍时重新生成缓存。  
  
 下面的示例演示如何将缓存提示选项用于 <xref:System.Windows.Media.DrawingBrush> 。  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>请参阅

- [优化 WPF 应用程序性能](optimizing-wpf-application-performance.md)
- [规划应用程序性能](planning-for-application-performance.md)
- [利用硬件](optimizing-performance-taking-advantage-of-hardware.md)
- [布局和示例](optimizing-performance-layout-and-design.md)
- [对象行为](optimizing-performance-object-behavior.md)
- [应用程序资源](optimizing-performance-application-resources.md)
- [文本](optimizing-performance-text.md)
- [数据绑定](optimizing-performance-data-binding.md)
- [其他性能建议](optimizing-performance-other-recommendations.md)
- [动画提示和技巧](../graphics-multimedia/animation-tips-and-tricks.md)
