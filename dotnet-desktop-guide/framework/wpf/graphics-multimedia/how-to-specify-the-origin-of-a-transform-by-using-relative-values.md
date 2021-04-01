---
title: 如何：使用相对值指定变换原点
ms.date: 03/30/2017
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
ms.openlocfilehash: 48b3b0df8dab8516873495a996074eae57ffe00f
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971003"
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a>如何：使用相对值指定变换原点
此示例演示如何使用相对值来指定应用于的的源 <xref:System.Windows.UIElement.RenderTransform%2A> <xref:System.Windows.FrameworkElement> 。  
  
 使用属性旋转、缩放或倾斜时 <xref:System.Windows.FrameworkElement> <xref:System.Windows.UIElement.RenderTransform%2A> ，默认设置会将变换应用到元素的左上角。 如果要从元素中心进行旋转、缩放或扭曲，则可以通过将转换中心设置为元素中心来进行补偿。 但是，该解决方案要求你知道元素的大小。 将转换应用到元素中心的一种更简单的方式是将其 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 属性设置为 (0.5，0.5) ，而不是在变换本身上设置中心值。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.RotateTransform> 来 <xref:System.Windows.Controls.Button> 顺时针旋转45度。 由于该示例未指定中心，按钮将围绕点 (0, 0)（即按钮的左上角）旋转。 <xref:System.Windows.Media.RotateTransform>适用于 <xref:System.Windows.UIElement.RenderTransform%2A> 属性。  
  
 下图显示了以下示例的转换结果。  
  
 ![使用 RenderTransform 转换后的按钮](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
使用 RenderTransform 属性顺时针旋转 45 度  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 下面的示例还使用 <xref:System.Windows.Media.RotateTransform> 以 <xref:System.Windows.Controls.Button> 顺时针旋转45度; 但是，此示例将按钮的设置 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 为 (0.5，0.5) 。 因此，将在按钮的中心（而不是其左上角）应用旋转。  
  
 下图显示了以下示例的转换结果。  
  
 ![围绕中心转换后的按钮](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
将 RenderTransform 属性与值为 (0.5, 0.5) 的 RenderTransformOrigin 结合使用以旋转 45 度  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 有关转换对象的详细信息 <xref:System.Windows.FrameworkElement> ，请参阅 [转换概述](transforms-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Transform>
- [转换概述](transforms-overview.md)
- [操作指南主题](transformations-how-to-topics.md)
