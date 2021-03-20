---
title: 位图效果概述
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 6147e4aedc9160db25f8f5f3506854b12287be24
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668612"
---
# <a name="bitmap-effects-overview"></a><span data-ttu-id="3c771-102">位图效果概述</span><span class="sxs-lookup"><span data-stu-id="3c771-102">Bitmap Effects Overview</span></span>

<span data-ttu-id="3c771-103">使用位图效果，设计人员和开发人员可以将视觉效果应用于 (WPF) 内容所呈现的 Windows Presentation Foundation。</span><span class="sxs-lookup"><span data-stu-id="3c771-103">Bitmap effects enable designers and developers to apply visual effects to rendered Windows Presentation Foundation (WPF) content.</span></span> <span data-ttu-id="3c771-104">例如，位图效果允许您轻松地将 <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 效果或模糊效果应用于图像或按钮。</span><span class="sxs-lookup"><span data-stu-id="3c771-104">For example, bitmap effects allow you to easily apply a <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> effect or a blur effect to an image or a button.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3c771-105">在 .NET Framework 4 或更高版本中， <xref:System.Windows.Media.Effects.BitmapEffect> 类已过时。</span><span class="sxs-lookup"><span data-stu-id="3c771-105">In the .NET Framework 4 or later, the <xref:System.Windows.Media.Effects.BitmapEffect> class is obsolete.</span></span> <span data-ttu-id="3c771-106">如果尝试使用 <xref:System.Windows.Media.Effects.BitmapEffect> 类，您将收到过时的异常。</span><span class="sxs-lookup"><span data-stu-id="3c771-106">If you try to use the <xref:System.Windows.Media.Effects.BitmapEffect> class, you will get an obsolete exception.</span></span> <span data-ttu-id="3c771-107">类的非过时替代方法 <xref:System.Windows.Media.Effects.BitmapEffect> 为 <xref:System.Windows.Media.Effects.Effect> 类。</span><span class="sxs-lookup"><span data-stu-id="3c771-107">The non-obsolete alternative to the <xref:System.Windows.Media.Effects.BitmapEffect> class is the <xref:System.Windows.Media.Effects.Effect> class.</span></span> <span data-ttu-id="3c771-108">在大多数情况下， <xref:System.Windows.Media.Effects.Effect> 类的速度要快得多。</span><span class="sxs-lookup"><span data-stu-id="3c771-108">In most situations, the <xref:System.Windows.Media.Effects.Effect> class is significantly faster.</span></span>  

<a name="wpf_effects"></a>

## <a name="wpf-bitmap-effects"></a><span data-ttu-id="3c771-109">WPF 位图效果</span><span class="sxs-lookup"><span data-stu-id="3c771-109">WPF Bitmap Effects</span></span>  

 <span data-ttu-id="3c771-110">位图效果 (<xref:System.Windows.Media.Effects.BitmapEffect> 对象) 是简单像素处理操作。</span><span class="sxs-lookup"><span data-stu-id="3c771-110">Bitmap effects (<xref:System.Windows.Media.Effects.BitmapEffect> object) are simple pixel processing operations.</span></span> <span data-ttu-id="3c771-111">位图效果采用 <xref:System.Windows.Media.Imaging.BitmapSource> 作为输入，并 <xref:System.Windows.Media.Imaging.BitmapSource> 在应用效果后生成新效果，如模糊或投影。</span><span class="sxs-lookup"><span data-stu-id="3c771-111">A bitmap effect takes a <xref:System.Windows.Media.Imaging.BitmapSource> as an input and produces a new <xref:System.Windows.Media.Imaging.BitmapSource> after applying the effect, such as a blur or drop shadow.</span></span> <span data-ttu-id="3c771-112">每个位图效果都公开了可控制筛选属性的属性， <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> 例如 <xref:System.Windows.Media.Effects.BlurBitmapEffect> 。</span><span class="sxs-lookup"><span data-stu-id="3c771-112">Each bitmap effect exposes properties that can control the filtering properties, such as <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> of <xref:System.Windows.Media.Effects.BlurBitmapEffect>.</span></span>  
  
 <span data-ttu-id="3c771-113">作为一种特殊情况，在中 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，可以将效果设置为活动 <xref:System.Windows.Media.Visual> 对象（如或）的属性 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="3c771-113">As a special case, in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], effects can be set as properties on live <xref:System.Windows.Media.Visual> objects, such as a <xref:System.Windows.Controls.Button> or <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="3c771-114">像素处理在运行时应用并呈现。</span><span class="sxs-lookup"><span data-stu-id="3c771-114">The pixel processing is applied and rendered at run-time.</span></span> <span data-ttu-id="3c771-115">在这种情况下，在呈现时，将 <xref:System.Windows.Media.Visual> 自动转换为其等效的， <xref:System.Windows.Media.Imaging.BitmapSource> 并作为输入送进 <xref:System.Windows.Media.Effects.BitmapEffect> 。</span><span class="sxs-lookup"><span data-stu-id="3c771-115">In this case, at the time of rendering, a <xref:System.Windows.Media.Visual> is automatically converted to its <xref:System.Windows.Media.Imaging.BitmapSource> equivalent and is fed as input to the <xref:System.Windows.Media.Effects.BitmapEffect>.</span></span> <span data-ttu-id="3c771-116">输出替换 <xref:System.Windows.Media.Visual> 对象的默认呈现行为。</span><span class="sxs-lookup"><span data-stu-id="3c771-116">The output replaces the <xref:System.Windows.Media.Visual> object's default rendering behavior.</span></span> <span data-ttu-id="3c771-117">这就是为什么 <xref:System.Windows.Media.Effects.BitmapEffect> 对象强制仅在软件中呈现视觉对象的原因，即，在应用效果时不会对视觉对象进行硬件加速。</span><span class="sxs-lookup"><span data-stu-id="3c771-117">This is why <xref:System.Windows.Media.Effects.BitmapEffect> objects force visuals to render in software only i.e. no hardware acceleration on visuals when effects are applied.</span></span>  
  
- <span data-ttu-id="3c771-118"><xref:System.Windows.Media.Effects.BlurBitmapEffect> 模拟显得不到焦点的对象。</span><span class="sxs-lookup"><span data-stu-id="3c771-118"><xref:System.Windows.Media.Effects.BlurBitmapEffect> simulates an object that appears out-of-focus.</span></span>  
  
- <span data-ttu-id="3c771-119"><xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> 围绕对象的外围创建颜色光环。</span><span class="sxs-lookup"><span data-stu-id="3c771-119"><xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> creates a halo of color around the perimeter of an object.</span></span>  
  
- <span data-ttu-id="3c771-120"><xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 创建对象后面的阴影。</span><span class="sxs-lookup"><span data-stu-id="3c771-120"><xref:System.Windows.Media.Effects.DropShadowBitmapEffect> creates a shadow behind an object.</span></span>  
  
- <span data-ttu-id="3c771-121"><xref:System.Windows.Media.Effects.BevelBitmapEffect> 创建凹凸效果，根据指定的曲线提升图像表面。</span><span class="sxs-lookup"><span data-stu-id="3c771-121"><xref:System.Windows.Media.Effects.BevelBitmapEffect> creates a bevel which raises the surface of an image according to a specified curve.</span></span>  
  
- <span data-ttu-id="3c771-122"><xref:System.Windows.Media.Effects.EmbossBitmapEffect> 创建的凹凸映射 <xref:System.Windows.Media.Visual> ，以使其从人工光源获得深度和纹理的印象。</span><span class="sxs-lookup"><span data-stu-id="3c771-122"><xref:System.Windows.Media.Effects.EmbossBitmapEffect> creates a bump mapping of a <xref:System.Windows.Media.Visual> to give the impression of depth and texture from an artificial light source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c771-123">WPF 位图效果在软件模式下呈现。</span><span class="sxs-lookup"><span data-stu-id="3c771-123">WPF bitmap effects are rendered in software mode.</span></span> <span data-ttu-id="3c771-124">应用效果的任何对象也都将以软件形式呈现。</span><span class="sxs-lookup"><span data-stu-id="3c771-124">Any object that applies an effect will also be rendered in software.</span></span> <span data-ttu-id="3c771-125">在大型视觉对象上使用位图效果或对位图效果的属性进行动画处理时，性能的下降幅度最大。</span><span class="sxs-lookup"><span data-stu-id="3c771-125">Performance is degraded the most when using Bitmap effects on large visuals or animating properties of a Bitmap effect.</span></span> <span data-ttu-id="3c771-126">这并不表示完全不应该以这种方式使用位图效果，而是应谨慎使用，并进行全面测试以确保用户得到预期的体验。</span><span class="sxs-lookup"><span data-stu-id="3c771-126">This is not to say that you should not use Bitmap effects in this way at all, but you should use caution and test thoroughly to ensure that your users are getting the experience you expect.</span></span>  
> [!NOTE]
> <span data-ttu-id="3c771-127">WPF 位图效果不支持部分信任的执行。</span><span class="sxs-lookup"><span data-stu-id="3c771-127">WPF bitmap effects do not support partial trust execution.</span></span> <span data-ttu-id="3c771-128">应用程序必须具有完全信任权限才能使用位图效果。</span><span class="sxs-lookup"><span data-stu-id="3c771-128">An application must have full trust permissions to use bitmap effects.</span></span>  
  
<a name="applyeffects"></a>

## <a name="how-to-apply-an-effect"></a><span data-ttu-id="3c771-129">如何应用效果</span><span class="sxs-lookup"><span data-stu-id="3c771-129">How to Apply an Effect</span></span>  

 <span data-ttu-id="3c771-130"><xref:System.Windows.Media.Effects.BitmapEffect> 是上的一个属性 <xref:System.Windows.Media.Visual> 。</span><span class="sxs-lookup"><span data-stu-id="3c771-130"><xref:System.Windows.Media.Effects.BitmapEffect> is a property on <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="3c771-131">因此，将效果应用于视觉对象（如 <xref:System.Windows.Controls.Button> 、 <xref:System.Windows.Controls.Image> 、 <xref:System.Windows.Media.DrawingVisual> 或 <xref:System.Windows.UIElement> ）与设置属性一样简单。</span><span class="sxs-lookup"><span data-stu-id="3c771-131">Therefore applying effects to Visuals, such as a <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>, or <xref:System.Windows.UIElement>, is as easy as setting a property.</span></span> <span data-ttu-id="3c771-132"><xref:System.Windows.UIElement.BitmapEffect%2A> 可以设置为单个对象， <xref:System.Windows.Media.Effects.BitmapEffect> 也可以使用对象链接多个效果 <xref:System.Windows.Media.Effects.BitmapEffectGroup> 。</span><span class="sxs-lookup"><span data-stu-id="3c771-132"><xref:System.Windows.UIElement.BitmapEffect%2A> can be set to a single <xref:System.Windows.Media.Effects.BitmapEffect> object or multiple effects can be chained by using the <xref:System.Windows.Media.Effects.BitmapEffectGroup> object.</span></span>  
  
 <span data-ttu-id="3c771-133">下面的示例演示如何 <xref:System.Windows.Media.Effects.BitmapEffect> 在中应用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="3c771-133">The following example demonstrates how to apply a <xref:System.Windows.Media.Effects.BitmapEffect> in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 <span data-ttu-id="3c771-134">下面的示例演示如何 <xref:System.Windows.Media.Effects.BitmapEffect> 在代码中应用。</span><span class="sxs-lookup"><span data-stu-id="3c771-134">The following example demonstrates how to apply a <xref:System.Windows.Media.Effects.BitmapEffect> in code.</span></span>  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> <span data-ttu-id="3c771-135">当 <xref:System.Windows.Media.Effects.BitmapEffect> 应用于布局容器（如或）时，会将 <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Canvas> 效果应用到元素或视觉对象的可视化树，包括其所有子元素。</span><span class="sxs-lookup"><span data-stu-id="3c771-135">When a <xref:System.Windows.Media.Effects.BitmapEffect> is applied to a layout container, such as <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.Canvas>, the effect is applied to the visual tree of the element or visual, including all of its child elements.</span></span>  
  
<a name="customeffects"></a>

## <a name="creating-custom-effects"></a><span data-ttu-id="3c771-136">创建自定义效果</span><span class="sxs-lookup"><span data-stu-id="3c771-136">Creating Custom Effects</span></span>  

 <span data-ttu-id="3c771-137">WPF 还提供非托管接口，以创建可在托管 WPF 应用程序中使用的自定义效果。</span><span class="sxs-lookup"><span data-stu-id="3c771-137">WPF also provides unmanaged interfaces to create custom effects that can be used in managed WPF applications.</span></span> <span data-ttu-id="3c771-138">有关创建自定义位图效果的其他参考资料，请参阅[非托管 WPF 位图效果](/previous-versions/windows/desktop/wibe/-wibe-lh)文档。</span><span class="sxs-lookup"><span data-stu-id="3c771-138">For additional reference material for creating custom bitmap effects, see the [Unmanaged WPF Bitmap Effect](/previous-versions/windows/desktop/wibe/-wibe-lh) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c771-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c771-139">See also</span></span>

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [<span data-ttu-id="3c771-140">非托管 WPF 位图效果</span><span class="sxs-lookup"><span data-stu-id="3c771-140">Unmanaged WPF Bitmap Effect</span></span>](/previous-versions/windows/desktop/wibe/-wibe-lh)
- [<span data-ttu-id="3c771-141">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="3c771-141">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="3c771-142">安全性</span><span class="sxs-lookup"><span data-stu-id="3c771-142">Security</span></span>](../security-wpf.md)
- [<span data-ttu-id="3c771-143">WPF 图形呈现疑难解答</span><span class="sxs-lookup"><span data-stu-id="3c771-143">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="3c771-144">二维图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="3c771-144">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
