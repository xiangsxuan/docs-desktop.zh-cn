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
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>如何：保持背景图像的长宽比
此示例演示如何使用的 <xref:System.Windows.Media.TileBrush.Stretch%2A> 属性 <xref:System.Windows.Media.ImageBrush> 来保持图像的纵横比。  
  
 默认情况下，当你使用 <xref:System.Windows.Media.ImageBrush> 绘制区域时，它的内容将拉伸以完全填充输出区域。 当输出区域和图像的纵横比不同时，图像就会因拉伸而失真。  
  
 若要使 <xref:System.Windows.Media.ImageBrush> 保持图像的纵横比，请将属性设置 <xref:System.Windows.Media.TileBrush.Stretch%2A> 为 <xref:System.Windows.Media.Stretch.Uniform> 或 <xref:System.Windows.Media.Stretch.UniformToFill> 。  
  
## <a name="example"></a>示例  
 下面的示例使用两个 <xref:System.Windows.Media.ImageBrush> 对象来绘制两个矩形。 每个矩形都为 300x150 像素，每个矩形都包含一个像素为 300x300 的图像。 <xref:System.Windows.Media.TileBrush.Stretch%2A>第一个画笔的属性设置为 <xref:System.Windows.Media.Stretch.Uniform> ， <xref:System.Windows.Media.TileBrush.Stretch%2A> 第二个画笔的属性设置为 <xref:System.Windows.Media.Stretch.UniformToFill> 。  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 下图显示了第一个画笔的输出，该画笔的 <xref:System.Windows.Media.TileBrush.Stretch%2A> 设置为 <xref:System.Windows.Media.Stretch.Uniform> 。  
  
 ![具有 Uniform 拉伸的 ImageBrush](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 下图显示了第二个画笔的输出，该画笔的 <xref:System.Windows.Media.TileBrush.Stretch%2A> 设置为 <xref:System.Windows.Media.Stretch.UniformToFill> 。  
  
 ![具有 UniformToFill 拉伸的 ImageBrush](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 请注意，对于 <xref:System.Windows.Media.TileBrush.Stretch%2A> 和，属性的行为与其他对象的行为相同 <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> 。 有关 <xref:System.Windows.Media.ImageBrush> 和其他对象的详细信息 <xref:System.Windows.Media.TileBrush> ，请参阅 [利用图像、绘图和视觉](painting-with-images-drawings-and-visuals.md)对象进行绘制。  
  
 另请注意，尽管 <xref:System.Windows.Media.TileBrush.Stretch%2A> 属性似乎指定了 <xref:System.Windows.Media.TileBrush> 内容如何拉伸以适合其输出区域，但它实际上指定了内容如何 <xref:System.Windows.Media.TileBrush> 拉伸以填充其基本图块。 有关详细信息，请参阅 <xref:System.Windows.Media.TileBrush>。  
  
 此代码示例是为类提供的更大示例的一部分 <xref:System.Windows.Media.ImageBrush> 。 有关完整示例，请参阅 [System.windows.media.imagebrush> 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.TileBrush>
- [使用图像、图形和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
