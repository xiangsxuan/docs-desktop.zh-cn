---
title: 如何：向文本应用变换
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: 867f39e3df8493014d8601530e91310c3bbbeeb5
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971921"
---
# <a name="how-to-apply-transforms-to-text"></a>如何：向文本应用变换
应用变换可以改变应用程序中文本的显示。 下面的示例使用不同类型的呈现转换来影响控件中文本的显示 <xref:System.Windows.Controls.TextBlock> 。  
  
## <a name="example"></a>示例  
 下面的示例演示了在 x-y 二维平面中文本围绕一个特定点进行旋转。  
  
 ![使用 RotateTransform 旋转的文本](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 下面的代码示例使用 <xref:System.Windows.Media.RotateTransform> 来旋转文本。 <xref:System.Windows.Media.RotateTransform.Angle%2A>值90将顺时针旋转元素90度。  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 下面的示例演示沿 X 轴放大 150% 得到第二行文本，沿 Y 轴放大 150% 得到第三行文本。  
  
 ![使用 ScaleTransform 缩放的文本](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg)
  
 下面的代码示例使用 <xref:System.Windows.Media.ScaleTransform> 从文本的原始大小进行缩放。  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
> 放大文本不同于增大文本字号。 字号的计算相互独立，以便针对不同字号提供最佳分辨率。 而缩放后的文本将按比例保持原始的文本大小。  
  
 以下示例演示沿 X 轴倾斜的文本。  
  
 ![使用 SkewTransform 扭曲的文本](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)

 下面的代码示例使用 <xref:System.Windows.Media.SkewTransform> 来倾斜文本。 扭曲（也称为倾斜）是一种以非均匀方式拉伸坐标空间的变换。 在本示例中，两个文本字符串沿 x 坐标扭曲了 -30° 和 30°。  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 下面的示例演示沿 x 轴和 y 轴平移或移动的文本。  
  
 ![使用 TranslateTransform 偏移的文本](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 下面的代码示例使用 <xref:System.Windows.Media.TranslateTransform> 来偏移文本。 在本示例中，主要文本下方略微偏移的文本副本营造出了阴影效果。  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
> <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>提供了一组丰富的功能，用于提供阴影效果。 有关详细信息，请参阅 [使用阴影创建文本](how-to-create-text-with-a-shadow.md)。  
  
## <a name="see-also"></a>另请参阅

- [向文本应用动画](how-to-apply-animations-to-text.md)
