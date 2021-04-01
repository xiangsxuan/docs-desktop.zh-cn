---
title: 如何：旋转对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973174"
---
# <a name="how-to-rotate-an-object"></a>如何：旋转对象
此示例演示如何旋转对象。 该示例首先创建一个 <xref:System.Windows.Media.RotateTransform> ，然后 <xref:System.Windows.Media.RotateTransform.Angle%2A> 以度为单位指定它。  
  
 下面的示例将 <xref:System.Windows.Shapes.Polyline> 对象的左上角旋转到45度。  
  
## <a name="example"></a>示例  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <xref:System.Windows.Media.RotateTransform.CenterX%2A>的和 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 属性 <xref:System.Windows.Media.RotateTransform> 指定对象要旋转的点。 此中心点以要转换的元素的坐标空间表示。 默认情况下，将围绕着要转换的对象的左上角 (0,0) 进行旋转。  
  
 下一个示例将 <xref:System.Windows.Shapes.Polyline> 对象顺时针旋转45度 (25，50) 。  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 下图显示了将应用于 <xref:System.Windows.Media.Transform> 这两个对象的结果。  
  
 ![以不同中心点进行的 45 度旋转](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
两个对象以不同的旋转中心旋转 45 度  
  
 <xref:System.Windows.Shapes.Polyline>前面的示例中的是 <xref:System.Windows.UIElement> 。 当你将应用 <xref:System.Windows.Media.Transform> 到 <xref:System.Windows.UIElement.RenderTransform%2A> 的属性时 <xref:System.Windows.UIElement> ，可以使用 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 属性为应用到元素的每个指定源 <xref:System.Windows.Media.Transform> 。 由于 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 属性使用相对坐标，因此即使你不知道其大小，也可以将转换应用到元素的中心。 有关详细信息和示例，请参阅 [使用相对值指定转换原点](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)。  
  
 有关完整示例，请参阅 [2D 转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Transform>
- [转换概述](transforms-overview.md)
- [操作指南主题](transformations-how-to-topics.md)
