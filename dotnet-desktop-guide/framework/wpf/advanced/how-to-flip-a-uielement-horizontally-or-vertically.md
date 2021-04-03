---
title: 如何：水平或垂直翻转 UIElement
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 6b3da322493d17e4f8e36a35b9a0e40fdc9dc685
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973474"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a>如何：水平或垂直翻转 UIElement
此示例演示如何使用 <xref:System.Windows.Media.ScaleTransform> 来 <xref:System.Windows.UIElement> 水平或垂直翻转。 在此示例中， <xref:System.Windows.Controls.Button> <xref:System.Windows.UIElement> 通过将应用 <xref:System.Windows.Media.ScaleTransform> 到其属性来翻转) 类型 (的控件 <xref:System.Windows.UIElement.RenderTransform%2A> 。  
  
## <a name="example"></a>示例  
 下图显示了要翻转的按钮。  
  
 ![无转换的按钮](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")  
要翻转的 UIElement  
  
 下面显示了用于创建按钮的代码。  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a>示例  
 若要水平翻转按钮，请创建一个 <xref:System.Windows.Media.ScaleTransform> 并将其 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 属性设置为-1。 将应用 <xref:System.Windows.Media.ScaleTransform> 到按钮的 <xref:System.Windows.UIElement.RenderTransform%2A> 属性。  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 ![围绕 &#40;0，0&#41;水平翻转的按钮 ](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")  
应用 System.windows.media.scaletransform> 后的按钮  
  
## <a name="example"></a>示例  
 如前面的插图所示，按钮已翻转，但也被移动。 这是因为按钮从左上角翻转。 若要就地翻转按钮，需要将应用 <xref:System.Windows.Media.ScaleTransform> 到其中心，而不是应用于角。 向按钮中心应用的一种简单方法 <xref:System.Windows.Media.ScaleTransform> 是将按钮的 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 属性设置为0.5、0.5。  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 ![围绕中心水平翻转的按钮](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")  
System.windows.uielement.rendertransformorigin 为0.5，0.5 的按钮  
  
## <a name="example"></a>示例  
 若要垂直翻转按钮，请设置 <xref:System.Windows.Media.ScaleTransform> 对象的 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 属性而不是其 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 属性。  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 ![围绕中心垂直翻转的按钮](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")  
垂直翻转按钮  
  
## <a name="see-also"></a>另请参阅

- [转换概述](../graphics-multimedia/transforms-overview.md)
