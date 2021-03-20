---
title: 变换概述
ms.date: 03/30/2017
helpviewer_keywords:
- transformations [WPF], about transformations
- classes [WPF], 2D transform
- transform classes [WPF], 2D
- 2D transform classes
- FrameworkElement objects [WPF], rotating
- FrameworkElement objects [WPF], skewing
- FrameworkElement objects [WPF], translating
- Transforms [WPF], about Transforms
- FrameworkElement objects [WPF], scaling
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
ms.openlocfilehash: c0332fb477c3081ea36fe7675aa11297b42e5c12
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666609"
---
# <a name="transforms-overview"></a>变换概述
本主题介绍如何使用 2D <xref:System.Windows.Media.Transform> 类来旋转、缩放、移动 (平移) 和倾斜 <xref:System.Windows.FrameworkElement> 对象。  

<a name="whatIsATransformSection"></a>
## <a name="what-is-a-transform"></a>什么是 Transform？  
 <xref:System.Windows.Media.Transform>定义如何将点从一个坐标空间映射或转换到另一个坐标空间。 这种映射通过转换进行描述 <xref:System.Windows.Media.Matrix> ，后者是包含三列值的三行的集合 <xref:System.Double> 。  
  
> [!NOTE]
> WPF) Windows Presentation Foundation (使用行主矩阵。 矢量表示为行矢量，而非列矢量。  
  
 下表显示了 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 矩阵的结构。  
  
### <a name="a-2d-transformation-matrix"></a>2D 变换矩阵  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> 默认值：1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> 默认值：0.0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> 默认值：0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> 默认值：1.0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> 默认值：0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> 默认值：0.0|1.0|  
  
 通过操作矩阵值，可以旋转、缩放、倾斜和移动（转换）对象。 例如，如果将第三行的第一列中的值更改 (<xref:System.Windows.Media.Matrix.OffsetX%2A> 该值) 为100，则可以使用它将对象100单位沿 x 轴移动。 如果将第二行第二列中的值更改为 3，可使用它来将对象的当前高度拉伸三倍。 如果同时更改这两个值，将使对象沿 x 轴移动 100 个单位，并将其高度拉伸 3 倍。 由于 Windows Presentation Foundation (WPF) 仅支持仿射转换，因此右侧列中的值始终为0，0，1。  
  
 尽管 Windows Presentation Foundation (WPF) 使你可以直接操作矩阵值，但它还提供了多个 <xref:System.Windows.Media.Transform> 类，使你能够在不知道基础矩阵结构的配置方式的情况下转换对象。 例如， <xref:System.Windows.Media.ScaleTransform> 通过类，您可以通过设置对象的和属性来缩放对象 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> ，而无需操作转换矩阵。 同样， <xref:System.Windows.Media.RotateTransform> 类使你可以通过仅设置对象的属性来旋转对象 <xref:System.Windows.Media.RotateTransform.Angle%2A> 。  
  
<a name="transformClassesSection"></a>
## <a name="transform-classes"></a>转换类  
 Windows Presentation Foundation (WPF) <xref:System.Windows.Media.Transform> 为常见转换操作提供了以下2d 类：  
  
|类|说明|示例|图示|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|按指定旋转元素 <xref:System.Windows.Media.RotateTransform.Angle%2A> 。|[旋转对象](how-to-rotate-an-object.md)|![旋转图](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|按指定的 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 和数量缩放元素 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 。|[缩放元素](how-to-scale-an-element.md)|![缩放图](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|按指定的 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 和量倾斜元素 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 。|[倾斜元素](how-to-skew-an-element.md)|![扭曲图](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|移动 (按指定的和量平移) <xref:System.Windows.Media.TranslateTransform.X%2A> 元素 <xref:System.Windows.Media.TranslateTransform.Y%2A> 。|[转换元素](how-to-translate-an-element.md)|![平移图](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 若要创建更复杂的转换，Windows Presentation Foundation (WPF) 提供以下两个类：  
  
|类|说明|示例|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|将多个 <xref:System.Windows.Media.TransformGroup> 对象组合成单个 <xref:System.Windows.Media.Transform> ，以便您可以将其应用于转换属性。|[向一个对象应用多个转换](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|创建其他类未提供的自定义转换 <xref:System.Windows.Media.Transform> 。 当你使用时 <xref:System.Windows.Media.MatrixTransform> ，你可以直接操作矩阵。|[使用 MatrixTransform 创建自定义转换](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 WPF) Windows Presentation Foundation (也提供三维转换。 有关更多信息，请参见 <xref:System.Windows.Media.Media3D.Transform3D> 类。  
  
<a name="transformationproperties"></a>
## <a name="common-transformation-properties"></a>常见转换属性  
 转换对象的一种方法是声明相应的 <xref:System.Windows.Media.Transform> 类型并将其应用于对象的转换属性。 对象类型不同，转换属性的类型也会不同。 下表列出了几个常用 Windows Presentation Foundation (WPF) 类型及其转换属性。  
  
|类型|转换属性|  
|----------|-------------------------------|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.Brush.Transform%2A>, <xref:System.Windows.Media.Brush.RelativeTransform%2A>|  
|<xref:System.Windows.Media.ContainerVisual>|<xref:System.Windows.Media.ContainerVisual.Transform%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|  
|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.UIElement.RenderTransform%2A>, <xref:System.Windows.FrameworkElement.LayoutTransform%2A>|  
|<xref:System.Windows.Media.Geometry>|<xref:System.Windows.Media.Geometry.Transform%2A>|  
|<xref:System.Windows.Media.TextEffect>|<xref:System.Windows.Media.TextEffect.Transform%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.RenderTransform%2A>|  
  
<a name="transformcenter"></a>
## <a name="transformations-and-coordinate-systems"></a>转换和坐标系  
 转换对象时，不只是转换对象，还会转换该对象所在的坐标空间。 默认情况下，转换基于目标对象坐标系的原点 (0,0) 居中。 唯一的例外情况是 <xref:System.Windows.Media.TranslateTransform> ： <xref:System.Windows.Media.TranslateTransform> 没有要设置的中心属性，因为翻译效果无论在何处居中都是相同的。  
  
 下面的示例使用 <xref:System.Windows.Media.RotateTransform> 来旋转 <xref:System.Windows.Shapes.Rectangle> 元素、类型 <xref:System.Windows.FrameworkElement> 、45度约于其默认中心 (0、0) 。 下图显示了旋转效果。  
  
 ![围绕 (0,0) 旋转 45 度的 FrameworkElement](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
围绕点 (0,0) 旋转 45 度的矩形元素  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 默认情况下，元素会围绕其左上角 (0, 0) 旋转。 <xref:System.Windows.Media.RotateTransform>、 <xref:System.Windows.Media.ScaleTransform> 和 <xref:System.Windows.Media.SkewTransform> 类提供 system.windows.media.rotatetransform.centerx 和 system.windows.media.rotatetransform.centery 属性，使您能够指定应用转换的点。  
  
 下一个示例还使用将 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Shapes.Rectangle> 元素旋转45度; 但是，这一次，设置了 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 和 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 属性，以便 <xref:System.Windows.Media.RotateTransform> 具有 (25，25) 的中心。 下图显示了旋转效果。  
  
 ![围绕 (25, 25) 旋转 45 度的几何](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
围绕点 (25, 25) 旋转 45 度矩形元素  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>
## <a name="transforming-a-frameworkelement"></a>转换 FrameworkElement  
 若要将转换应用于 <xref:System.Windows.FrameworkElement> ，请创建， <xref:System.Windows.Media.Transform> 并将其应用于该类提供的两个属性之一 <xref:System.Windows.FrameworkElement> ：  
  
- <xref:System.Windows.FrameworkElement.LayoutTransform%2A> –在布局处理过程之前应用的转换。 转换应用后，布局系统处理元素转换后的大小和位置。  
  
- <xref:System.Windows.UIElement.RenderTransform%2A> –修改元素外观但在布局处理过程完成后应用的转换。 通过使用 <xref:System.Windows.UIElement.RenderTransform%2A> 属性（而不是 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 属性），可以获得性能优势。  
  
 应使用哪个属性？ 由于它提供的性能优势，请尽可能使用 <xref:System.Windows.UIElement.RenderTransform%2A> 属性，尤其是使用动画 <xref:System.Windows.Media.Transform> 对象时。 <xref:System.Windows.FrameworkElement.LayoutTransform%2A>缩放、旋转或倾斜时使用属性，需要元素的父元素调整为元素的已转换大小。 请注意，当它们与属性一起使用时 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> ， <xref:System.Windows.Media.TranslateTransform> 对象看起来对元素不起作用。 这是因为布局系统将转换后的元素返回到其原始位置作为其处理的一部分。  
  
 有关 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 中布局的其他信息，请参阅[布局](../advanced/layout.md)概述。  
  
<a name="exampleRotateAnElement45degSection"></a>
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>示例：将 FrameworkElement 旋转 45 度  
 下面的示例使用将 <xref:System.Windows.Media.RotateTransform> 按钮顺时针旋转45度。 此按钮包含在 <xref:System.Windows.Controls.StackPanel> 有两个其他按钮的中。  
  
 默认情况下，对 <xref:System.Windows.Media.RotateTransform> 点的旋转 (0，0) 。 由于示例未指定中心点值，按钮将围绕点 (0, 0) 旋转，即其左上角。 <xref:System.Windows.Media.RotateTransform>适用于 <xref:System.Windows.UIElement.RenderTransform%2A> 属性。 下图显示转换的结果。  
  
 ![使用 RenderTransform 转换后的按钮](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
从左上角顺时针旋转 45 度  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 下一个示例还使用 <xref:System.Windows.Media.RotateTransform> 来顺时针旋转按钮45度，但它还将按钮的设置 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 为 (0.5，0.5) 。 属性的值与 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 按钮大小相关。 因此，该旋转应用到按钮的中心，而非左上角。 下图显示转换的结果。  
  
 ![围绕中心转换后的按钮](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
围绕中心顺时针旋转 45 度  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 下面的示例使用 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 属性而不是 <xref:System.Windows.UIElement.RenderTransform%2A> 属性来旋转按钮。  这将导致转换影响按钮的布局，从而触发布局系统的整个处理过程。 因此，按钮在旋转后重新定位，因为它的大小已更改。 下图显示转换的结果。  
  
 ![使用 LayoutTransform 转换后的按钮](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
用于旋转按钮的 LayoutTransform  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>
## <a name="animating-transformations"></a>对转换进行动画处理  
 由于它们继承自 <xref:System.Windows.Media.Animation.Animatable> 类，因此 <xref:System.Windows.Media.Transform> 可对类进行动画处理。 若要对进行动画处理 <xref:System.Windows.Media.Transform> ，请将兼容类型的动画应用于要进行动画处理的属性。  
  
 下面的示例将 <xref:System.Windows.Media.Animation.Storyboard> 和 <xref:System.Windows.Media.Animation.DoubleAnimation> 与一起使用， <xref:System.Windows.Media.RotateTransform> 以便 <xref:System.Windows.Controls.Button> 在单击时进行旋转。  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 有关完整示例，请参阅 [2D 转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。 有关动画的详细信息，请参阅[动画概述](animation-overview.md)。  
  
<a name="freezable_features"></a>
## <a name="freezable-features"></a>Freezable 功能  
 由于该类继承自 <xref:System.Windows.Freezable> 类，因此 <xref:System.Windows.Media.Transform> 该类提供若干特殊功能： <xref:System.Windows.Media.Transform> 对象可以声明为 [资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)、在多个对象之间共享、变为只读以提高性能、克隆以及使线程安全。 有关对象提供的不同功能的详细信息 <xref:System.Windows.Freezable> ，请参阅可 [冻结对象概述](../advanced/freezable-objects-overview.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [操作指南主题](transformations-how-to-topics.md)
- [2D 转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
