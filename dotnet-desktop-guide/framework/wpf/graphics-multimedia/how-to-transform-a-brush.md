---
title: 如何：变换画笔
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972766"
---
# <a name="how-to-transform-a-brush"></a>如何：变换画笔
此示例演示如何 <xref:System.Windows.Media.Brush> 使用两个转换属性来转换对象： <xref:System.Windows.Media.Brush.RelativeTransform%2A> 和 <xref:System.Windows.Media.Brush.Transform%2A> 。  
  
 下面的示例使用将的 <xref:System.Windows.Media.RotateTransform> 内容旋转 <xref:System.Windows.Media.ImageBrush> 45 度。  
  
 下图显示了 <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.RotateTransform> ，其中包含应用于属性的， <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.Brush.RelativeTransform%2A> 以及应用于属性的 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.Brush.Transform%2A> 。  
  
 ![画笔的 RelativeTransform 和 Transform 设置](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>示例  
 第一个示例将应用 <xref:System.Windows.Media.RotateTransform> 到的 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性 <xref:System.Windows.Media.ImageBrush> 。 <xref:System.Windows.Media.RotateTransform.CenterX%2A>对象的和 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 属性都 <xref:System.Windows.Media.RotateTransform> 设置为0.5，这是此内容中心点的相对坐标。 因此， <xref:System.Windows.Media.ImageBrush> 内容会围绕中心旋转。  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 第二个示例还将应用 <xref:System.Windows.Media.RotateTransform> 到， <xref:System.Windows.Media.ImageBrush> 但此示例使用属性， <xref:System.Windows.Media.Brush.Transform%2A> 而不是 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性。  
  
 为了围绕画笔中心旋转画笔，此示例将对象的 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 和 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 属性设置 <xref:System.Windows.Media.RotateTransform> 为绝对坐标。 因为画笔绘制了一个 175x90 像素的矩形，所以该矩形的中心点为 (87.5, 45)。  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 有关和属性的工作方式的说明 <xref:System.Windows.Media.Brush.RelativeTransform%2A> <xref:System.Windows.Media.Brush.Transform%2A> ，请参阅 [画笔转换概述](brush-transformation-overview.md)。  
  
 有关完整示例，请参阅[画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。 有关画笔的详细信息，请参阅[使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)。  
  
## <a name="see-also"></a>请参阅

- [Brush 变换概述](brush-transformation-overview.md)
- [使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)
- [转换概述](transforms-overview.md)
