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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973757"
---
# <a name="how-to-paint-an-area-with-a-video"></a>如何：使用视频绘制区域
此示例演示如何使用媒体绘制区域。 使用媒体绘制区域的一种方法是将 <xref:System.Windows.Controls.MediaElement> 与一起使用 <xref:System.Windows.Media.VisualBrush> 。 使用 <xref:System.Windows.Controls.MediaElement> 加载和播放媒体，然后使用它来设置 <xref:System.Windows.Media.VisualBrush.Visual%2A> 的属性 <xref:System.Windows.Media.VisualBrush> 。 然后，你可以使用 <xref:System.Windows.Media.VisualBrush> 来使用已加载的媒体来绘制区域。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Controls.MediaElement> 和 <xref:System.Windows.Media.VisualBrush> 来绘制 <xref:System.Windows.Controls.TextBlock.Foreground%2A> <xref:System.Windows.Controls.TextBlock> 具有视频的控件的。 此示例将 <xref:System.Windows.Controls.MediaElement.IsMuted%2A> 的属性设置 <xref:System.Windows.Controls.MediaElement> 为， `true` 以便它不会生成任何声音。  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a>示例  
 由于 <xref:System.Windows.Media.VisualBrush> 继承自 <xref:System.Windows.Media.TileBrush> 类，因此它提供多个平铺模式。 通过将的 <xref:System.Windows.Media.TileBrush.TileMode%2A> 属性设置 <xref:System.Windows.Media.VisualBrush> 为 <xref:System.Windows.Media.TileMode.Tile> ，并将其 <xref:System.Windows.Media.TileBrush.Viewport%2A> 属性设置为一个小于要绘制的区域的值，你可以创建一个平铺模式。  
  
 下面的示例与前面的示例相同，不同之处在于 <xref:System.Windows.Media.VisualBrush> 从视频生成模式。  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 有关如何向应用程序添加内容文件（例如媒体文件）的信息，请参阅 [WPF 应用程序资源、内容和数据文件](../app-development/wpf-application-resource-content-and-data-files.md)。 添加媒体文件时，必须将其添加为内容文件，而不是资源文件。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.VisualBrush>
- [使用图像、图形和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
- [TileBrush 概述](tilebrush-overview.md)
- [多媒体概述](multimedia-overview.md)
