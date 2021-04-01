---
title: 如何：使用 TileBrush 创建不同的平铺模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: c1051b234961eee9ae740af2abac3d64c523656c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972837"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a><span data-ttu-id="c3da3-102">如何：使用 TileBrush 创建不同的平铺模式</span><span class="sxs-lookup"><span data-stu-id="c3da3-102">How to: Create Different Tile Patterns with a TileBrush</span></span>
<span data-ttu-id="c3da3-103">此示例演示如何使用 <xref:System.Windows.Media.TileBrush.TileMode%2A> 的属性 <xref:System.Windows.Media.TileBrush> 创建模式。</span><span class="sxs-lookup"><span data-stu-id="c3da3-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.TileBrush> to create a pattern.</span></span>  
  
 <span data-ttu-id="c3da3-104">使用 <xref:System.Windows.Media.TileBrush.TileMode%2A> 属性可以指定如何重复的内容 <xref:System.Windows.Media.TileBrush> ，即平铺以填充输出区域。</span><span class="sxs-lookup"><span data-stu-id="c3da3-104">The <xref:System.Windows.Media.TileBrush.TileMode%2A> property enables you to specify how the content of a <xref:System.Windows.Media.TileBrush> is repeated, that is, tiled to fill an output area.</span></span> <span data-ttu-id="c3da3-105">若要创建模式，请将设置 <xref:System.Windows.Media.TileBrush.TileMode%2A> 为 <xref:System.Windows.Media.TileMode.Tile> 、 <xref:System.Windows.Media.TileMode.FlipX> 、 <xref:System.Windows.Media.TileMode.FlipY> 或 <xref:System.Windows.Media.TileMode.FlipXY> 。</span><span class="sxs-lookup"><span data-stu-id="c3da3-105">To create a pattern, you set the <xref:System.Windows.Media.TileBrush.TileMode%2A> to <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, or <xref:System.Windows.Media.TileMode.FlipXY>.</span></span> <span data-ttu-id="c3da3-106">您还必须设置的， <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush> 使其小于您要绘制的区域; 否则，将只生成单个磁贴，而不考虑 <xref:System.Windows.Media.TileBrush.TileMode%2A> 您使用的设置。</span><span class="sxs-lookup"><span data-stu-id="c3da3-106">You must also set the <xref:System.Windows.Media.TileBrush.Viewport%2A> of the <xref:System.Windows.Media.TileBrush> so that it is smaller than the area that you are painting; otherwise, only a single tile is produced, regardless which <xref:System.Windows.Media.TileBrush.TileMode%2A> setting you use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3da3-107">示例</span><span class="sxs-lookup"><span data-stu-id="c3da3-107">Example</span></span>  
 <span data-ttu-id="c3da3-108">下面的示例创建五个 <xref:System.Windows.Media.DrawingBrush> 对象，为它们提供不同的 <xref:System.Windows.Media.TileBrush.TileMode%2A> 设置，并使用它们绘制五个矩形。</span><span class="sxs-lookup"><span data-stu-id="c3da3-108">The following example creates five <xref:System.Windows.Media.DrawingBrush> objects, gives them each a different <xref:System.Windows.Media.TileBrush.TileMode%2A> setting, and uses them to paint five rectangles.</span></span> <span data-ttu-id="c3da3-109">虽然此示例使用 <xref:System.Windows.Media.DrawingBrush> 类来演示 <xref:System.Windows.Media.TileBrush.TileMode%2A> 行为，但是 <xref:System.Windows.Media.TileBrush.TileMode%2A> 属性对于所有对象（即、和）都是相同的 <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.VisualBrush> <xref:System.Windows.Media.DrawingBrush> 。</span><span class="sxs-lookup"><span data-stu-id="c3da3-109">Although this example uses the <xref:System.Windows.Media.DrawingBrush> class to demonstrate <xref:System.Windows.Media.TileBrush.TileMode%2A> behavior, the <xref:System.Windows.Media.TileBrush.TileMode%2A> property works identically for all the <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, and <xref:System.Windows.Media.DrawingBrush>.</span></span>  
  
 <span data-ttu-id="c3da3-110">下图显示了此示例生成的输出。</span><span class="sxs-lookup"><span data-stu-id="c3da3-110">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="c3da3-111">![TileBrush 平铺示例输出](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span><span class="sxs-lookup"><span data-stu-id="c3da3-111">![TileBrush tiling example output](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span></span>  
<span data-ttu-id="c3da3-112">用 System.windows.media.tilemode> 属性创建的平铺模式</span><span class="sxs-lookup"><span data-stu-id="c3da3-112">Tile patterns created with the TileMode property</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="c3da3-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3da3-113">See also</span></span>

- [<span data-ttu-id="c3da3-114">设置 TileBrush 的平铺大小</span><span class="sxs-lookup"><span data-stu-id="c3da3-114">Set the Tile Size for a TileBrush</span></span>](how-to-set-the-tile-size-for-a-tilebrush.md)
- [<span data-ttu-id="c3da3-115">使用图像、图形和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="c3da3-115">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
