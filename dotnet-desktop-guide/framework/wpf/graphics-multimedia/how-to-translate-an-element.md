---
title: 如何：平移元素
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972762"
---
# <a name="how-to-translate-an-element"></a>如何：平移元素
此示例演示如何使用转换 (移动) 元素 <xref:System.Windows.Media.TranslateTransform> 。  
  
 <xref:System.Windows.Media.TranslateTransform>类对于在不支持绝对定位的面板内移动元素特别有用。 例如，通过将应用 <xref:System.Windows.Media.TranslateTransform> 于元素的 <xref:System.Windows.UIElement.RenderTransform%2A> 属性，可以在或中移动元素 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.DockPanel> 。  
  
 使用 <xref:System.Windows.Media.TranslateTransform.X%2A> 的属性 <xref:System.Windows.Media.TranslateTransform> 来指定沿 x 轴移动元素的量（以像素为单位）。 使用 <xref:System.Windows.Media.TranslateTransform.Y%2A> 属性来指定沿 y 轴移动元素的量（以像素为单位）。 最后，将应用于该 <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.UIElement.RenderTransform%2A> 元素的属性。  
  
 下面的示例使用将 <xref:System.Windows.Media.TranslateTransform> 元素50像素向右移动，将50像素向下移动。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 有关完整示例，请参阅 [2D 转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。  
  
## <a name="see-also"></a>请参阅

- [转换概述](transforms-overview.md)
