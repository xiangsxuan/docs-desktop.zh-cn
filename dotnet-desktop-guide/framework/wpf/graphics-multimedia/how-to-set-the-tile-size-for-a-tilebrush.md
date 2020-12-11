---
title: 如何：为 TileBrush 设置平铺大小
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971012"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="efb29-102">如何：为 TileBrush 设置平铺大小</span><span class="sxs-lookup"><span data-stu-id="efb29-102">How to: Set the Tile Size for a TileBrush</span></span>

<span data-ttu-id="efb29-103">此示例演示如何设置的磁贴大小 <xref:System.Windows.Media.TileBrush> 。</span><span class="sxs-lookup"><span data-stu-id="efb29-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="efb29-104">默认情况下， <xref:System.Windows.Media.TileBrush> 会生成单个磁贴，以完全填充要绘制的区域。</span><span class="sxs-lookup"><span data-stu-id="efb29-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="efb29-105">您可以通过设置和属性来重写此行为 <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 。</span><span class="sxs-lookup"><span data-stu-id="efb29-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>

<span data-ttu-id="efb29-106"><xref:System.Windows.Media.TileBrush.Viewport%2A>属性指定的磁贴大小 <xref:System.Windows.Media.TileBrush> 。</span><span class="sxs-lookup"><span data-stu-id="efb29-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="efb29-107">默认情况下，属性的值 <xref:System.Windows.Media.TileBrush.Viewport%2A> 相对于正在绘制的区域的大小。</span><span class="sxs-lookup"><span data-stu-id="efb29-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="efb29-108">若要使 <xref:System.Windows.Media.TileBrush.Viewport%2A> 属性指定绝对磁贴大小，请将 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 属性设置为 <xref:System.Windows.Media.BrushMappingMode.Absolute> 。</span><span class="sxs-lookup"><span data-stu-id="efb29-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>

## <a name="example"></a><span data-ttu-id="efb29-109">示例</span><span class="sxs-lookup"><span data-stu-id="efb29-109">Example</span></span>

<span data-ttu-id="efb29-110">下面的示例使用 <xref:System.Windows.Media.ImageBrush> 一种类型的 <xref:System.Windows.Media.TileBrush> ，用图块绘制矩形。</span><span class="sxs-lookup"><span data-stu-id="efb29-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="efb29-111">该示例将每个图块的) 的输出区域 (的输出区域的50% 设置为50%。</span><span class="sxs-lookup"><span data-stu-id="efb29-111">The example sets each tile to 50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="efb29-112">因此，将用四个投影图像绘制该矩形。</span><span class="sxs-lookup"><span data-stu-id="efb29-112">As a result, the rectangle is painted with four projections of the image.</span></span>

<span data-ttu-id="efb29-113">下图显示了该示例生成的输出：</span><span class="sxs-lookup"><span data-stu-id="efb29-113">The following illustration shows the output that the example produces:</span></span>

![带有四个樱桃的矩形，演示如何使用图像画笔进行平铺。](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

<span data-ttu-id="efb29-115">下一个示例创建一个 <xref:System.Windows.Media.ImageBrush> ，将其设置为，并将其设置为 <xref:System.Windows.Media.TileBrush.Viewport%2A> `0,0,25,25` <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute> ，并使用它来绘制另一个矩形。</span><span class="sxs-lookup"><span data-stu-id="efb29-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="efb29-116">因此，画笔会生成一个宽度为 25 像素、高度为 25 像素的平铺。</span><span class="sxs-lookup"><span data-stu-id="efb29-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>

<span data-ttu-id="efb29-117">下图显示了该示例生成的输出：</span><span class="sxs-lookup"><span data-stu-id="efb29-117">The following illustration shows the output that the example produces:</span></span>

![一个矩形，其中包含48樱桃，其中演示了带视区的平铺 TileBrush。](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

<span data-ttu-id="efb29-119">以上几个示例摘自一个更大的示例。</span><span class="sxs-lookup"><span data-stu-id="efb29-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="efb29-120">有关完整示例，请参阅 [System.windows.media.imagebrush> 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)。</span><span class="sxs-lookup"><span data-stu-id="efb29-120">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>

<span data-ttu-id="efb29-121">虽然此示例使用 <xref:System.Windows.Media.ImageBrush> 类，但 <xref:System.Windows.Media.TileBrush.Viewport%2A> 和属性的行为与 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 其他对象的行为相同 <xref:System.Windows.Media.TileBrush> ，即对于 <xref:System.Windows.Media.DrawingBrush> 和 <xref:System.Windows.Media.VisualBrush> 。</span><span class="sxs-lookup"><span data-stu-id="efb29-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="efb29-122">有关 <xref:System.Windows.Media.ImageBrush> 和其他对象的详细信息 <xref:System.Windows.Media.TileBrush> ，请参阅 [利用图像、绘图和视觉](painting-with-images-drawings-and-visuals.md)对象进行绘制。</span><span class="sxs-lookup"><span data-stu-id="efb29-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="efb29-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efb29-123">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="efb29-124">使用图像、图形和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="efb29-124">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="efb29-125">使用 TileBrush 创建不同的平铺图案</span><span class="sxs-lookup"><span data-stu-id="efb29-125">Create Different Tile Patterns with a TileBrush</span></span>](how-to-create-different-tile-patterns-with-a-tilebrush.md)
