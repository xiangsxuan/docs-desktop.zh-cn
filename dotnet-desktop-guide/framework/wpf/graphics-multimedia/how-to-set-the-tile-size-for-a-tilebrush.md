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
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>如何：为 TileBrush 设置平铺大小

此示例演示如何设置的磁贴大小 <xref:System.Windows.Media.TileBrush> 。 默认情况下， <xref:System.Windows.Media.TileBrush> 会生成单个磁贴，以完全填充要绘制的区域。 您可以通过设置和属性来重写此行为 <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 。

<xref:System.Windows.Media.TileBrush.Viewport%2A>属性指定的磁贴大小 <xref:System.Windows.Media.TileBrush> 。 默认情况下，属性的值 <xref:System.Windows.Media.TileBrush.Viewport%2A> 相对于正在绘制的区域的大小。 若要使 <xref:System.Windows.Media.TileBrush.Viewport%2A> 属性指定绝对磁贴大小，请将 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 属性设置为 <xref:System.Windows.Media.BrushMappingMode.Absolute> 。

## <a name="example"></a>示例

下面的示例使用 <xref:System.Windows.Media.ImageBrush> 一种类型的 <xref:System.Windows.Media.TileBrush> ，用图块绘制矩形。 该示例将每个图块的) 的输出区域 (的输出区域的50% 设置为50%。 因此，将用四个投影图像绘制该矩形。

下图显示了该示例生成的输出：

![带有四个樱桃的矩形，演示如何使用图像画笔进行平铺。](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

下一个示例创建一个 <xref:System.Windows.Media.ImageBrush> ，将其设置为，并将其设置为 <xref:System.Windows.Media.TileBrush.Viewport%2A> `0,0,25,25` <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute> ，并使用它来绘制另一个矩形。 因此，画笔会生成一个宽度为 25 像素、高度为 25 像素的平铺。

下图显示了该示例生成的输出：

![一个矩形，其中包含48樱桃，其中演示了带视区的平铺 TileBrush。](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

以上几个示例摘自一个更大的示例。 有关完整示例，请参阅 [System.windows.media.imagebrush> 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)。

虽然此示例使用 <xref:System.Windows.Media.ImageBrush> 类，但 <xref:System.Windows.Media.TileBrush.Viewport%2A> 和属性的行为与 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 其他对象的行为相同 <xref:System.Windows.Media.TileBrush> ，即对于 <xref:System.Windows.Media.DrawingBrush> 和 <xref:System.Windows.Media.VisualBrush> 。 有关 <xref:System.Windows.Media.ImageBrush> 和其他对象的详细信息 <xref:System.Windows.Media.TileBrush> ，请参阅 [利用图像、绘图和视觉](painting-with-images-drawings-and-visuals.md)对象进行绘制。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.TileBrush>
- [使用图像、图形和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
- [使用 TileBrush 创建不同的平铺图案](how-to-create-different-tile-patterns-with-a-tilebrush.md)
