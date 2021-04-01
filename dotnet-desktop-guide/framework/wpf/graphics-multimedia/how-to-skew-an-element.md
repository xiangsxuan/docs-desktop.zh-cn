---
title: 如何：使元素扭曲
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971008"
---
# <a name="how-to-skew-an-element"></a>如何：使元素扭曲
此示例演示如何使用 <xref:System.Windows.Media.SkewTransform> 来倾斜元素。 扭曲（也称为修剪）是一种以非均匀方式拉伸坐标空间的转换。 的一个典型用途 <xref:System.Windows.Media.SkewTransform> 是在2d 对象中模拟3d 深度。  
  
 使用 <xref:System.Windows.Media.SkewTransform.CenterX%2A> 和 <xref:System.Windows.Media.SkewTransform.CenterY%2A> 属性来指定的中心点 <xref:System.Windows.Media.SkewTransform> 。  
  
 使用 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 和 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 属性来指定 x 轴和 y 轴的倾斜角度，并沿这些轴倾斜当前坐标系统。  
  
 若要预测斜切转换的效果，请考虑将 <xref:System.Windows.Media.SkewTransform.AngleX%2A> x 轴值与原始坐标系统相对倾斜。 因此，对于 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 30，y 轴将从原点旋转30度，并从该原点的 x 到30度之间倾斜值。 同样，值为30时， <xref:System.Windows.Media.SkewTransform.AngleY%2A> 从原点将形状的 y 值倾斜30度。 请注意，在 x 或 y 轴中将坐标系统转换（移动）30 度的效果并不相同。  
  
 下面的示例 <xref:System.Windows.Shapes.Rectangle> 从 (0，0) 的中心点向中应用45度的水平倾斜。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 下面的示例 <xref:System.Windows.Shapes.Rectangle> 从 (25，25) 的中心点向中应用45度的水平倾斜。  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 下面的示例 <xref:System.Windows.Shapes.Rectangle> 从 (25，25) 的中心点向中应用45度的垂直倾斜。  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 下图演示了此示例中使用的不同扭曲。  
  
 ![SkewTransform 示例](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
三个 SkewTransform 示例的图示  
  
 有关完整示例，请参阅 [2D 转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [转换概述](transforms-overview.md)
- [操作指南主题](transformations-how-to-topics.md)
