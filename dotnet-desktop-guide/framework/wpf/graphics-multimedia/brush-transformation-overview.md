---
title: Brush 变换概述
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], transformation properties
- properties [WPF], transformation
- transformation properties of brushes [WPF]
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
ms.openlocfilehash: 7616e1620c0bd342e3c8bb776e8d72c038bd3cc6
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972806"
---
# <a name="brush-transformation-overview"></a>Brush 变换概述
画笔类提供两个转换属性： <xref:System.Windows.Media.Brush.Transform%2A> 和 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 。 使用这些属性，可以旋转、缩放、倾斜和转换画笔的内容。 本主题介绍这两个属性之间的区别，并提供有关它们的用法示例。  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>先决条件  
 若要了解本主题，应了解要转换的画笔的功能。 对于 <xref:System.Windows.Media.LinearGradientBrush> 和 <xref:System.Windows.Media.RadialGradientBrush> ，请参阅 [采用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)。 对于 <xref:System.Windows.Media.ImageBrush> 、 <xref:System.Windows.Media.DrawingBrush> 或 <xref:System.Windows.Media.VisualBrush> ，请参阅  [利用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。 还应当熟悉[转换概述](transforms-overview.md)中所述的 2D 转换。  
  
<a name="transformversusrelativetransform"></a>
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Transform 和 RelativeTransform 属性之间的区别  
 将转换应用于画笔的 <xref:System.Windows.Media.Brush.Transform%2A> 属性时，如果想要变换画笔内容的中心，则需要知道绘制区域的大小。 假设已绘制区域的宽度为 200 个与设备无关的像素，高度为 150。  如果你使用了 <xref:System.Windows.Media.RotateTransform> 来旋转画笔的输出45度，则应为 <xref:System.Windows.Media.RotateTransform> 100，并将指定为 <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> 75。  
  
 将转换应用于画笔的 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性时，该转换将应用于画笔，然后将其输出映射到绘制的区域。 以下列表介绍处理和转换画笔内容的顺序。  
  
1. 处理画笔的内容。 对于 <xref:System.Windows.Media.GradientBrush> ，这意味着要确定渐变区域。 对于 <xref:System.Windows.Media.TileBrush> ，会将 <xref:System.Windows.Media.TileBrush.Viewbox%2A> 映射到 <xref:System.Windows.Media.TileBrush.Viewport%2A> 。 这成为画笔的输出。  
  
2. 将画笔的输出投影到 1 x 1 的转换矩形上。  
  
3. 应用画笔的 <xref:System.Windows.Media.Brush.RelativeTransform%2A> （如果有）。  
  
4. 将转换后的输出投影到要绘制的区域上。  
  
5. 应用画笔的 <xref:System.Windows.Media.Transform> （如果有）。  
  
 由于在 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 画笔的输出映射到 1 x 1 矩形时应用，因此变换中心和偏移量值显示为相对。 例如，如果你使用将 <xref:System.Windows.Media.RotateTransform> 画笔的输出45度旋转到中心，则将为 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.RotateTransform.CenterX%2A> 0.5 和 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 0.5。  
  
 下图显示了使用和属性旋转了45度的几个画笔的输出 <xref:System.Windows.Media.Brush.RelativeTransform%2A> <xref:System.Windows.Media.Brush.Transform%2A> 。  
  
 ![RelativeTransform 和 Transform 属性](./media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>
## <a name="using-relativetransform-with-a-tilebrush"></a>将 RelativeTransform 用于 TileBrush  
 由于平铺画笔比其他画笔更复杂，因此应用 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 到一个画笔可能会产生意外的结果。 例如以下图像。  
  
 ![源图像](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 下面的示例使用 <xref:System.Windows.Media.ImageBrush> 绘制带有前面的图像的矩形区域。 它将应用于 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.ImageBrush> 对象的 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性，并将其属性设置 <xref:System.Windows.Media.TileBrush.Stretch%2A> 为 <xref:System.Windows.Media.Stretch.UniformToFill> ，这样，在拉伸以完全填充矩形时，它将保持图像的纵横比。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 该示例产生下面的输出：  
  
 ![变换后的输出](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 请注意，即使画笔的设置为，图像也会扭曲 <xref:System.Windows.Media.TileBrush.Stretch%2A> <xref:System.Windows.Media.Stretch.UniformToFill> 。 这是因为在画笔的映射到其后，将应用相对转换 <xref:System.Windows.Media.TileBrush.Viewbox%2A> <xref:System.Windows.Media.TileBrush.Viewport%2A> 。 以下列表介绍该过程的每个步骤：  
  
1. 投影画笔的内容 (<xref:System.Windows.Media.TileBrush.Viewbox%2A>) 其基本图块， (<xref:System.Windows.Media.TileBrush.Viewport%2A>) 使用画笔的 <xref:System.Windows.Media.TileBrush.Stretch%2A> 设置。  
  
     ![拉伸 Viewbox 以适合于视区](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2. 将基本图块投影到 1 x 1 的转换矩形上。  
  
     ![将视区映射到转换矩形](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3. 应用 <xref:System.Windows.Media.RotateTransform> 。  
  
     ![应用相对转换](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4. 将转换后的基本图块投影到要绘制的区域上。  
  
     ![将变换后的画笔投射到输出区域](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>
## <a name="example-rotate-an-imagebrush-45-degrees"></a>示例：将 ImageBrush 旋转 45 度  
 下面的示例将应用 <xref:System.Windows.Media.RotateTransform> 到的 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性 <xref:System.Windows.Media.ImageBrush> 。 <xref:System.Windows.Media.RotateTransform>对象的 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 和属性都 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 设置为0.5，即内容中心点的相对坐标。 因此，画笔的内容围绕其中心旋转。  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 下一个示例还将应用 <xref:System.Windows.Media.RotateTransform> 到 <xref:System.Windows.Media.ImageBrush> ，但使用 <xref:System.Windows.Media.Brush.Transform%2A> 属性而非 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性。 若要围绕画笔中心旋转画笔，则 <xref:System.Windows.Media.RotateTransform> 对象的 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 和 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 必须设置为绝对坐标。 由于画笔要绘制的矩形为 175 x 90 像素，因此它的中心点为 (87.5, 45)。  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 下图显示了不带转换的画笔、应用了此属性的转换 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 以及应用于属性的转换 <xref:System.Windows.Media.Brush.Transform%2A> 。  
  
 ![画笔的 RelativeTransform 和 Transform 设置](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 此示例摘自一个更大的示例。 有关完整示例，请参阅[画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。 有关画笔的详细信息，请参阅 [WPF 画笔概述](wpf-brushes-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)
- [使用图像、图形和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
- [转换概述](transforms-overview.md)
