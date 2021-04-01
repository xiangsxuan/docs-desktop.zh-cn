---
title: 如何：创建反射
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 8a5ed345c0aa25312bd74799264e1f66ab4554e0
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973760"
---
# <a name="how-to-create-a-reflection"></a>如何：创建反射
此示例演示如何使用 <xref:System.Windows.Media.VisualBrush> 创建反射。 由于 <xref:System.Windows.Media.VisualBrush> 可以显示现有视觉对象，因此可以使用此功能生成有趣的视觉效果，例如反射和放大。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.VisualBrush> 创建 <xref:System.Windows.Controls.Border> 包含多个元素的的反射。 下图显示了此示例生成的输出。  
  
 ![反射的 Visual 对象](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
反射的 Visual 对象  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 有关完整示例，包括演示如何放大屏幕的各个部分以及如何创建反射的示例，请参阅 [System.windows.media.visualbrush> 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.VisualBrush>
- [使用图像、图形和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
