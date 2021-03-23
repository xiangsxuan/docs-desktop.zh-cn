---
title: 图形和多媒体
description: 发现 Windows Presentation Foundation (WPF) 的媒体功能。 向应用程序添加图形、过渡效果、声音和视频。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- media [WPF], features
- video effects [WPF]
- sound effects [WPF]
- animation [WPF], features
- graphics features [WPF]
- transition effects [WPF]
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
ms.openlocfilehash: 1528d865ff7f76471c27f9db61eff13f118575b6
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668506"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="d2a1f-104">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="d2a1f-104">Graphics and Multimedia</span></span>

<a name="introduction"></a>
<span data-ttu-id="d2a1f-105">[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 为多媒体、矢量图形、动画和内容复合提供支持，使开发者可以轻松生成有趣的用户界面和内容。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-105">[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="d2a1f-106">使用 Visual Studio，可以创建矢量图形或复杂动画，并将媒体集成到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-106">Using Visual Studio, you can create vector graphics or complex animations and integrate media into your applications.</span></span>

<span data-ttu-id="d2a1f-107">本主题介绍 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 的图形、动画和媒体功能，可用于向应用程序添加图形、转换效果、声音和视频。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-107">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>

> [!NOTE]
> <span data-ttu-id="d2a1f-108">强烈建议不要在 Windows 服务中使用 WPF 类型。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-108">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="d2a1f-109">如果尝试在 Windows 服务中使用 WPF 类型，该服务可能无法按预期工作。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-109">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="d2a1f-110">WPF 4 中的图形和多媒体新增功能</span><span class="sxs-lookup"><span data-stu-id="d2a1f-110">What's New with Graphics and Multimedia in WPF 4</span></span>

<span data-ttu-id="d2a1f-111">进行了与图形和动画相关的多项更改。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-111">Several changes have been made related to graphics and animations.</span></span>

- <span data-ttu-id="d2a1f-112">布局舍入</span><span class="sxs-lookup"><span data-stu-id="d2a1f-112">Layout Rounding</span></span>

  <span data-ttu-id="d2a1f-113">当对象边缘落在像素设备中间位置时，与 DPI 无关的图形系统可以创建呈现项目，如模糊或半透明边缘。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-113">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="d2a1f-114">WPF 的以前版本包含像素捕捉以帮助处理这种情况。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-114">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="d2a1f-115">Silverlight 2 引入了布局舍入，这是移动元素以使边缘落在整个像素边界上的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-115">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="d2a1f-116">WPF 现在支持在 <xref:System.Windows.FrameworkElement> 上使用 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> 附加属性进行布局舍入。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-116">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>

- <span data-ttu-id="d2a1f-117">缓存复合</span><span class="sxs-lookup"><span data-stu-id="d2a1f-117">Cached Composition</span></span>

  <span data-ttu-id="d2a1f-118">通过使用新的 <xref:System.Windows.Media.BitmapCache> 和 <xref:System.Windows.Media.BitmapCacheBrush> 类，可以将可视化树的复杂部分缓存为位图，并大大缩短呈现时间。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-118">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="d2a1f-119">位图仍然能够响应用户输入（如鼠标单击），并且可以像任何画笔一样将其绘制到其他元素上。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-119">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>

- <span data-ttu-id="d2a1f-120">像素着色器 3 支持</span><span class="sxs-lookup"><span data-stu-id="d2a1f-120">Pixel Shader 3 Support</span></span>

  <span data-ttu-id="d2a1f-121">WPF 4 基于 WPF 3.5 SP1 中引入的 <xref:System.Windows.Media.Effects.ShaderEffect> 支持而生成，允许应用程序使用像素着色器 (PS) 版本 3.0 写入效果。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-121">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="d2a1f-122">PS 3.0 着色器模型比 PS 2.0 更复杂，从而允许在支持的硬件上使用更多效果。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-122">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>

- <span data-ttu-id="d2a1f-123">缓动函数</span><span class="sxs-lookup"><span data-stu-id="d2a1f-123">Easing Functions</span></span>

  <span data-ttu-id="d2a1f-124">可以使用缓动函数增强动画，从而提供对动画行为的额外控制。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-124">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="d2a1f-125">例如，可以将 <xref:System.Windows.Media.Animation.ElasticEase> 应用到动画，以提供类似弹簧的行为。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-125">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="d2a1f-126">有关详细信息，请参阅 <xref:System.Windows.Media.Animation> 命名空间中的缓动类型。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-126">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a><span data-ttu-id="d2a1f-127">图形和呈现</span><span class="sxs-lookup"><span data-stu-id="d2a1f-127">Graphics and Rendering</span></span>

<span data-ttu-id="d2a1f-128">WPF 引入了对高质量 2D 图形的支持。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-128">WPF includes support for high quality 2D graphics.</span></span> <span data-ttu-id="d2a1f-129">功能包括画笔、几何、图像、形状和转换。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-129">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="d2a1f-130">有关详细信息，请参阅[图形](graphics.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-130">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="d2a1f-131">图形元素的呈现基于 <xref:System.Windows.Media.Visual> 类。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-131">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="d2a1f-132">屏幕上的视觉对象的结构由可视化树描述。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-132">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="d2a1f-133">有关详细信息，请参阅 [WPF 图形呈现概述](wpf-graphics-rendering-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-133">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="d2a1f-134">2D 形状</span><span class="sxs-lookup"><span data-stu-id="d2a1f-134">2D Shapes</span></span>

<span data-ttu-id="d2a1f-135">WPF 提供常用矢量绘制的 2D 形状库，如下图中所示的矩形和椭圆形。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-135">WPF provides a library of commonly used, vector-drawn 2D shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>

![显示椭圆形和矩形的关系图。](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

<span data-ttu-id="d2a1f-137">这些内部 WPF 形状不仅仅是形状：它们是可编程的元素，用于实现常见控件的许多预期功能，包括键盘和鼠标输入。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-137">These intrinsic WPF shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="d2a1f-138">下面的示例演示如何处理因单击 <xref:System.Windows.Shapes.Ellipse> 元素而引发的 <xref:System.Windows.UIElement.MouseUp> 事件。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-138">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>

```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="Window1" >
  <Ellipse Fill="LightBlue" MouseUp="ellipseButton_MouseUp" />
</Window>
```

```csharp
public partial class Window1  : Window
{
    void ellipseButton_MouseUp(object sender, MouseButtonEventArgs e)
    {
        MessageBox.Show("You clicked the ellipse!");
    }
}
```

```vb
Partial Public Class Window1
    Inherits Window
    Private Sub ellipseButton_MouseUp(ByVal sender As Object, ByVal e As MouseButtonEventArgs)
        MessageBox.Show("You clicked the ellipse!")
    End Sub
End Class
```

<span data-ttu-id="d2a1f-139">下图显示前面的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 标记和代码隐藏的输出。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-139">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>

![一个消息框显示“你单击了椭圆形！”](./media/index/messagebox-text-output.png)

<span data-ttu-id="d2a1f-141">有关详细信息，请参阅 [WPF 中的形状和基本绘图概述](shapes-and-basic-drawing-in-wpf-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-141">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="d2a1f-142">有关介绍性示例，请参阅[形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-142">For an introductory sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="d2a1f-143">2D 几何图形</span><span class="sxs-lookup"><span data-stu-id="d2a1f-143">2D Geometries</span></span>

<span data-ttu-id="d2a1f-144">当 WPF 提供的 2D 形状不足时，可以使用对几何和路径的 WPF 支持来创建自己的形状。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-144">When the 2D shapes that WPF provides are not sufficient, you can use WPF support for geometries and paths to create your own.</span></span> <span data-ttu-id="d2a1f-145">下图显示如何使用几何创建形状作为图形画笔和剪裁其他 WPF 元素。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-145">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other WPF elements.</span></span>

![屏幕截图显示如何使用几何图形来创建形状。](./media/index/use-geometries-create-shapes.png)

<span data-ttu-id="d2a1f-147">有关详细信息，请参阅 [Geometry 概述](geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-147">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="d2a1f-148">有关介绍性示例，请参阅 [Geometry 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-148">For an introductory sample, see [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="d2a1f-149">2D 效果</span><span class="sxs-lookup"><span data-stu-id="d2a1f-149">2D Effects</span></span>

<span data-ttu-id="d2a1f-150">WPF 提供了 2D 类的库，可用于创建各种效果。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-150">WPF provides a library of 2D classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="d2a1f-151">借助 WPF 的 2D 呈现功能，可以绘制具有渐变、位图、绘图和视频的 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 元素，并且可以使用旋转、缩放和倾斜来操作它们。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-151">The 2D rendering capability of WPF provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="d2a1f-152">下图演提供了可使用 WPF 画笔实现的许多效果的示例。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-152">The following illustration gives an example of the many effects you can achieve by using WPF brushes.</span></span>

![插图显示了不同的 WPF 画笔和绘图元素。](./media/index/brushes-paint-elements.png)

<span data-ttu-id="d2a1f-154">有关详细信息，请参阅 [WPF 画笔概述](wpf-brushes-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-154">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="d2a1f-155">有关详细信息，请参阅[画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-155">For an introductory sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>

<a name="rendering"></a>

## <a name="3d-rendering"></a><span data-ttu-id="d2a1f-156">3D 呈现</span><span class="sxs-lookup"><span data-stu-id="d2a1f-156">3D Rendering</span></span>

<span data-ttu-id="d2a1f-157">WPF 提供一组 3D 呈现功能，这些功能与 WPF 中的 2D 图形支持集成，以便创建更精彩的布局、[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 和数据可视化。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-157">WPF provides a set of 3D rendering capabilities that integrate with 2D graphics support in WPF in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="d2a1f-158">另一方面，WPF 支持将 2D 图像呈现到 3D 形状的表面，下图演示了此功能。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-158">At one end of the spectrum, WPF enables you to render 2D images onto the surfaces of 3D shapes, which the following illustration demonstrates.</span></span>

![屏幕截图显示了具有不同纹理的 3D 形状的示例。](./media/index/visual-three-dimensional-shape.png)

<span data-ttu-id="d2a1f-160">有关详细信息，请参阅[三维图形概述](3-d-graphics-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-160">For more information, see [3D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="d2a1f-161">有关介绍性示例，请参阅 [3D 实体示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-161">For an introductory sample, see [3D Solids Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

<a name="animation"></a>

## <a name="animation"></a><span data-ttu-id="d2a1f-162">动画</span><span class="sxs-lookup"><span data-stu-id="d2a1f-162">Animation</span></span>

<span data-ttu-id="d2a1f-163">使用动画，可以让控件和元素变大、抖动、旋转和淡出，并创建有趣的转换等。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-163">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="d2a1f-164">由于 WPF 支持对大多数属性进行动画处理，因此，不仅可以对大多数 WPF 对象进行动画处理，还可以使用 WPF 对创建的自定义对象进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-164">Because WPF enables you to animate most properties, not only can you animate most WPF objects, you can also use WPF to animate custom objects that you create.</span></span>

![屏幕截图显示了具有动画效果的立方体。](./media/index/animate-custom-objects.png)

<span data-ttu-id="d2a1f-166">有关详细信息，请参阅 [动画概述](animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-166">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="d2a1f-167">有关介绍性示例，请参阅[动画示例库](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-167">For an introductory sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

<a name="media"></a>

## <a name="media"></a><span data-ttu-id="d2a1f-168">媒体</span><span class="sxs-lookup"><span data-stu-id="d2a1f-168">Media</span></span>

<span data-ttu-id="d2a1f-169">图像、视频和音频是传达信息和用户体验的富媒体方法。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-169">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>

### <a name="images"></a><span data-ttu-id="d2a1f-170">映像</span><span class="sxs-lookup"><span data-stu-id="d2a1f-170">Images</span></span>

<span data-ttu-id="d2a1f-171">图像（包括图标、背景甚至动画部分）是大部分应用程序的核心部分。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-171">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="d2a1f-172">由于经常需要使用图像，因此 WPF 公开以各种方式处理它们的功能。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-172">Because you frequently need to use images, WPF exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="d2a1f-173">下图显示其中一种方法。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-173">The following illustration shows just one of those ways.</span></span>

<span data-ttu-id="d2a1f-174">![样式设置示例屏幕截图](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="d2a1f-174">![Styling sample screenshot](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

<span data-ttu-id="d2a1f-175">有关详细信息，请参阅 [图像概述](imaging-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-175">For more information, see [Imaging Overview](imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="d2a1f-176">视频和音频</span><span class="sxs-lookup"><span data-stu-id="d2a1f-176">Video and Audio</span></span>

<span data-ttu-id="d2a1f-177">WPF 的图形功能的核心功能是为处理多媒体（包括视频和音频）提供本机支持。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-177">A core feature of the graphics capabilities of WPF is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="d2a1f-178">以下示例介绍如何将媒体播放器插入到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-178">The following example shows how to insert a media player into an application.</span></span>

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<span data-ttu-id="d2a1f-179"><xref:System.Windows.Controls.MediaElement> 能够播放视频和音频，并且可扩展，足以轻松创建自定义的 UI。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-179"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom UIs.</span></span>

<span data-ttu-id="d2a1f-180">有关详细信息，请参阅[多媒体概述](multimedia-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a1f-180">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d2a1f-181">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2a1f-181">See also</span></span>

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="d2a1f-182">二维图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="d2a1f-182">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="d2a1f-183">WPF 中的形状和基本图形概述</span><span class="sxs-lookup"><span data-stu-id="d2a1f-183">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="d2a1f-184">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="d2a1f-184">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="d2a1f-185">使用图像、图形和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="d2a1f-185">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="d2a1f-186">动画和计时帮助主题</span><span class="sxs-lookup"><span data-stu-id="d2a1f-186">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="d2a1f-187">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="d2a1f-187">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="d2a1f-188">多媒体概述</span><span class="sxs-lookup"><span data-stu-id="d2a1f-188">Multimedia Overview</span></span>](multimedia-overview.md)
