---
title: 如何：保持背景图像的长宽比
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: b467fcd353994faef19b5a997e03d6582789eac1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970848"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a><span data-ttu-id="fc58a-102">如何：保持背景图像的长宽比</span><span class="sxs-lookup"><span data-stu-id="fc58a-102">How to: Preserve the Aspect Ratio of an Image Used as a Background</span></span>
<span data-ttu-id="fc58a-103">此示例演示如何使用的 <xref:System.Windows.Media.TileBrush.Stretch%2A> 属性 <xref:System.Windows.Media.ImageBrush> 来保持图像的纵横比。</span><span class="sxs-lookup"><span data-stu-id="fc58a-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of an <xref:System.Windows.Media.ImageBrush> in order to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="fc58a-104">默认情况下，当你使用 <xref:System.Windows.Media.ImageBrush> 绘制区域时，它的内容将拉伸以完全填充输出区域。</span><span class="sxs-lookup"><span data-stu-id="fc58a-104">By default, when you use an <xref:System.Windows.Media.ImageBrush> to paint an area, its content stretches to completely fill the output area.</span></span> <span data-ttu-id="fc58a-105">当输出区域和图像的纵横比不同时，图像就会因拉伸而失真。</span><span class="sxs-lookup"><span data-stu-id="fc58a-105">When the output area and the image have different aspect ratios, the image is distorted by this stretching.</span></span>  
  
 <span data-ttu-id="fc58a-106">若要使 <xref:System.Windows.Media.ImageBrush> 保持图像的纵横比，请将属性设置 <xref:System.Windows.Media.TileBrush.Stretch%2A> 为 <xref:System.Windows.Media.Stretch.Uniform> 或 <xref:System.Windows.Media.Stretch.UniformToFill> 。</span><span class="sxs-lookup"><span data-stu-id="fc58a-106">To make an <xref:System.Windows.Media.ImageBrush> preserve the aspect ratio of its image, set the <xref:System.Windows.Media.TileBrush.Stretch%2A> property to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc58a-107">示例</span><span class="sxs-lookup"><span data-stu-id="fc58a-107">Example</span></span>  
 <span data-ttu-id="fc58a-108">下面的示例使用两个 <xref:System.Windows.Media.ImageBrush> 对象来绘制两个矩形。</span><span class="sxs-lookup"><span data-stu-id="fc58a-108">The following example uses two <xref:System.Windows.Media.ImageBrush> objects to paint two rectangles.</span></span> <span data-ttu-id="fc58a-109">每个矩形都为 300x150 像素，每个矩形都包含一个像素为 300x300 的图像。</span><span class="sxs-lookup"><span data-stu-id="fc58a-109">Each rectangle is 300 by 150 pixels and each contains a 300 by 300 pixel image.</span></span> <span data-ttu-id="fc58a-110"><xref:System.Windows.Media.TileBrush.Stretch%2A>第一个画笔的属性设置为 <xref:System.Windows.Media.Stretch.Uniform> ， <xref:System.Windows.Media.TileBrush.Stretch%2A> 第二个画笔的属性设置为 <xref:System.Windows.Media.Stretch.UniformToFill> 。</span><span class="sxs-lookup"><span data-stu-id="fc58a-110">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the first brush is set to <xref:System.Windows.Media.Stretch.Uniform>, and the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the second brush is set to <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 <span data-ttu-id="fc58a-111">下图显示了第一个画笔的输出，该画笔的 <xref:System.Windows.Media.TileBrush.Stretch%2A> 设置为 <xref:System.Windows.Media.Stretch.Uniform> 。</span><span class="sxs-lookup"><span data-stu-id="fc58a-111">The following illustration shows the output of the first brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.Uniform>.</span></span>  
  
 <span data-ttu-id="fc58a-112">![具有 Uniform 拉伸的 ImageBrush](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span><span class="sxs-lookup"><span data-stu-id="fc58a-112">![ImageBrush with Uniform stretching](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span></span>  
  
 <span data-ttu-id="fc58a-113">下图显示了第二个画笔的输出，该画笔的 <xref:System.Windows.Media.TileBrush.Stretch%2A> 设置为 <xref:System.Windows.Media.Stretch.UniformToFill> 。</span><span class="sxs-lookup"><span data-stu-id="fc58a-113">The next illustration shows the output of the second brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 <span data-ttu-id="fc58a-114">![具有 UniformToFill 拉伸的 ImageBrush](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span><span class="sxs-lookup"><span data-stu-id="fc58a-114">![ImageBrush with UniformToFill stretching](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span></span>  
  
 <span data-ttu-id="fc58a-115">请注意，对于 <xref:System.Windows.Media.TileBrush.Stretch%2A> 和，属性的行为与其他对象的行为相同 <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> 。</span><span class="sxs-lookup"><span data-stu-id="fc58a-115">Note that the <xref:System.Windows.Media.TileBrush.Stretch%2A> property behaves identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="fc58a-116">有关 <xref:System.Windows.Media.ImageBrush> 和其他对象的详细信息 <xref:System.Windows.Media.TileBrush> ，请参阅 [利用图像、绘图和视觉](painting-with-images-drawings-and-visuals.md)对象进行绘制。</span><span class="sxs-lookup"><span data-stu-id="fc58a-116">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="fc58a-117">另请注意，尽管 <xref:System.Windows.Media.TileBrush.Stretch%2A> 属性似乎指定了 <xref:System.Windows.Media.TileBrush> 内容如何拉伸以适合其输出区域，但它实际上指定了内容如何 <xref:System.Windows.Media.TileBrush> 拉伸以填充其基本图块。</span><span class="sxs-lookup"><span data-stu-id="fc58a-117">Note also that, although the <xref:System.Windows.Media.TileBrush.Stretch%2A> property appears to specify how the <xref:System.Windows.Media.TileBrush> content stretches to fit its output area, it actually specifies how the <xref:System.Windows.Media.TileBrush> content stretches to fill its base tile.</span></span> <span data-ttu-id="fc58a-118">有关详细信息，请参阅 <xref:System.Windows.Media.TileBrush>。</span><span class="sxs-lookup"><span data-stu-id="fc58a-118">For more information, see <xref:System.Windows.Media.TileBrush>.</span></span>  
  
 <span data-ttu-id="fc58a-119">此代码示例是为类提供的更大示例的一部分 <xref:System.Windows.Media.ImageBrush> 。</span><span class="sxs-lookup"><span data-stu-id="fc58a-119">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="fc58a-120">有关完整示例，请参阅 [System.windows.media.imagebrush> 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)。</span><span class="sxs-lookup"><span data-stu-id="fc58a-120">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc58a-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc58a-121">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="fc58a-122">使用图像、图形和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="fc58a-122">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
