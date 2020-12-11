---
title: 如何：使用视频绘制区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: be09d1310847cd7214ea795a704c25d994f07b7a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973757"
---
# <a name="how-to-paint-an-area-with-a-video"></a><span data-ttu-id="884dd-102">如何：使用视频绘制区域</span><span class="sxs-lookup"><span data-stu-id="884dd-102">How to: Paint an Area with a Video</span></span>
<span data-ttu-id="884dd-103">此示例演示如何使用媒体绘制区域。</span><span class="sxs-lookup"><span data-stu-id="884dd-103">This example shows how to paint an area with media.</span></span> <span data-ttu-id="884dd-104">使用媒体绘制区域的一种方法是将 <xref:System.Windows.Controls.MediaElement> 与一起使用 <xref:System.Windows.Media.VisualBrush> 。</span><span class="sxs-lookup"><span data-stu-id="884dd-104">One way to paint an area with media is to use a <xref:System.Windows.Controls.MediaElement> together with a <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="884dd-105">使用 <xref:System.Windows.Controls.MediaElement> 加载和播放媒体，然后使用它来设置 <xref:System.Windows.Media.VisualBrush.Visual%2A> 的属性 <xref:System.Windows.Media.VisualBrush> 。</span><span class="sxs-lookup"><span data-stu-id="884dd-105">Use the <xref:System.Windows.Controls.MediaElement> to load and play the media, and then use it to set the <xref:System.Windows.Media.VisualBrush.Visual%2A> property of the <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="884dd-106">然后，你可以使用 <xref:System.Windows.Media.VisualBrush> 来使用已加载的媒体来绘制区域。</span><span class="sxs-lookup"><span data-stu-id="884dd-106">You can then use the <xref:System.Windows.Media.VisualBrush> to paint an area with the loaded media.</span></span>  
  
## <a name="example"></a><span data-ttu-id="884dd-107">示例</span><span class="sxs-lookup"><span data-stu-id="884dd-107">Example</span></span>  
 <span data-ttu-id="884dd-108">下面的示例使用 <xref:System.Windows.Controls.MediaElement> 和 <xref:System.Windows.Media.VisualBrush> 来绘制 <xref:System.Windows.Controls.TextBlock.Foreground%2A> <xref:System.Windows.Controls.TextBlock> 具有视频的控件的。</span><span class="sxs-lookup"><span data-stu-id="884dd-108">The following example uses a <xref:System.Windows.Controls.MediaElement> and a <xref:System.Windows.Media.VisualBrush> to paint the <xref:System.Windows.Controls.TextBlock.Foreground%2A> of a <xref:System.Windows.Controls.TextBlock> control with video.</span></span> <span data-ttu-id="884dd-109">此示例将 <xref:System.Windows.Controls.MediaElement.IsMuted%2A> 的属性设置 <xref:System.Windows.Controls.MediaElement> 为， `true` 以便它不会生成任何声音。</span><span class="sxs-lookup"><span data-stu-id="884dd-109">This example sets the <xref:System.Windows.Controls.MediaElement.IsMuted%2A> property of the <xref:System.Windows.Controls.MediaElement> to `true` so that it produces no sound.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a><span data-ttu-id="884dd-110">示例</span><span class="sxs-lookup"><span data-stu-id="884dd-110">Example</span></span>  
 <span data-ttu-id="884dd-111">由于 <xref:System.Windows.Media.VisualBrush> 继承自 <xref:System.Windows.Media.TileBrush> 类，因此它提供多个平铺模式。</span><span class="sxs-lookup"><span data-stu-id="884dd-111">Because <xref:System.Windows.Media.VisualBrush> inherits from the <xref:System.Windows.Media.TileBrush> class, it provides several tiling modes.</span></span> <span data-ttu-id="884dd-112">通过将的 <xref:System.Windows.Media.TileBrush.TileMode%2A> 属性设置 <xref:System.Windows.Media.VisualBrush> 为 <xref:System.Windows.Media.TileMode.Tile> ，并将其 <xref:System.Windows.Media.TileBrush.Viewport%2A> 属性设置为一个小于要绘制的区域的值，你可以创建一个平铺模式。</span><span class="sxs-lookup"><span data-stu-id="884dd-112">By setting the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.VisualBrush> to <xref:System.Windows.Media.TileMode.Tile> and by setting its <xref:System.Windows.Media.TileBrush.Viewport%2A> property to a value smaller than the area that you are painting, you can create a tiled pattern.</span></span>  
  
 <span data-ttu-id="884dd-113">下面的示例与前面的示例相同，不同之处在于 <xref:System.Windows.Media.VisualBrush> 从视频生成模式。</span><span class="sxs-lookup"><span data-stu-id="884dd-113">The following example is identical to the previous example, except that the <xref:System.Windows.Media.VisualBrush> generates a pattern from the video.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 <span data-ttu-id="884dd-114">有关如何向应用程序添加内容文件（例如媒体文件）的信息，请参阅 [WPF 应用程序资源、内容和数据文件](../app-development/wpf-application-resource-content-and-data-files.md)。</span><span class="sxs-lookup"><span data-stu-id="884dd-114">For information about how to add a content file, such as a media file, to your application, see [WPF Application Resource, Content, and Data Files](../app-development/wpf-application-resource-content-and-data-files.md).</span></span> <span data-ttu-id="884dd-115">添加媒体文件时，必须将其添加为内容文件，而不是资源文件。</span><span class="sxs-lookup"><span data-stu-id="884dd-115">When you add a media file, you must add it as a content file, not as a resource file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="884dd-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="884dd-116">See also</span></span>

- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="884dd-117">使用图像、图形和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="884dd-117">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="884dd-118">TileBrush 概述</span><span class="sxs-lookup"><span data-stu-id="884dd-118">TileBrush Overview</span></span>](tilebrush-overview.md)
- [<span data-ttu-id="884dd-119">多媒体概述</span><span class="sxs-lookup"><span data-stu-id="884dd-119">Multimedia Overview</span></span>](multimedia-overview.md)
