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
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="cfb3e-102">如何：创建反射</span><span class="sxs-lookup"><span data-stu-id="cfb3e-102">How to: Create a Reflection</span></span>
<span data-ttu-id="cfb3e-103">此示例演示如何使用 <xref:System.Windows.Media.VisualBrush> 创建反射。</span><span class="sxs-lookup"><span data-stu-id="cfb3e-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="cfb3e-104">由于 <xref:System.Windows.Media.VisualBrush> 可以显示现有视觉对象，因此可以使用此功能生成有趣的视觉效果，例如反射和放大。</span><span class="sxs-lookup"><span data-stu-id="cfb3e-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfb3e-105">示例</span><span class="sxs-lookup"><span data-stu-id="cfb3e-105">Example</span></span>  
 <span data-ttu-id="cfb3e-106">下面的示例使用 <xref:System.Windows.Media.VisualBrush> 创建 <xref:System.Windows.Controls.Border> 包含多个元素的的反射。</span><span class="sxs-lookup"><span data-stu-id="cfb3e-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="cfb3e-107">下图显示了此示例生成的输出。</span><span class="sxs-lookup"><span data-stu-id="cfb3e-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="cfb3e-108">![反射的 Visual 对象](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="cfb3e-108">![A reflected Visual object](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="cfb3e-109">反射的 Visual 对象</span><span class="sxs-lookup"><span data-stu-id="cfb3e-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="cfb3e-110">有关完整示例，包括演示如何放大屏幕的各个部分以及如何创建反射的示例，请参阅 [System.windows.media.visualbrush> 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)。</span><span class="sxs-lookup"><span data-stu-id="cfb3e-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb3e-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfb3e-111">See also</span></span>

- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="cfb3e-112">使用图像、图形和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="cfb3e-112">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
