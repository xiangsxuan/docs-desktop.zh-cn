---
title: 如何：将绘图用作图像源
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: d4b91a6495e1c54400d5fbfe43b6311d908565a7
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971000"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a>如何：将绘图用作图像源
此示例演示如何使用 <xref:System.Windows.Media.Drawing> 作为 <xref:System.Windows.Controls.Image.Source%2A> 控件的 <xref:System.Windows.Controls.Image> 。 若要在 <xref:System.Windows.Media.Drawing> <xref:System.Windows.Controls.Image> 控件中显示，请使用 <xref:System.Windows.Media.DrawingImage> 作为 <xref:System.Windows.Controls.Image> 控件的， <xref:System.Windows.Controls.Image.Source%2A> 并将 <xref:System.Windows.Media.DrawingImage> 对象的 <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> 属性设置为要显示的绘图。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.DrawingImage> 和 <xref:System.Windows.Controls.Image> 控件来显示 <xref:System.Windows.Media.GeometryDrawing> 。 该示例产生下面的输出：  
  
 ![两个椭圆形的 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
一个 DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Freezable.Freeze%2A>
- [使用 ImageDrawing 绘制图像](how-to-draw-an-image-using-imagedrawing.md)
- [Drawing 对象概述](drawing-objects-overview.md)
- [Freezable 对象概述](../advanced/freezable-objects-overview.md)
- [PresentationOptions:Freeze 特性](../advanced/presentationoptions-freeze-attribute.md)
