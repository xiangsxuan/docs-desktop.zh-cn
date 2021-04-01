---
title: 如何：使元素就地旋转
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974096"
---
# <a name="how-to-make-an-element-spin-in-place"></a>如何：使元素就地旋转
此示例演示如何使用和来使元素旋转 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.Animation.DoubleAnimation> 。  
  
 下面的示例将应用于该 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.UIElement.RenderTransform%2A> 元素的属性。 该示例使用对的进行 <xref:System.Windows.Media.Animation.DoubleAnimation> 动画处理 <xref:System.Windows.Media.RotateTransform.Angle%2A> <xref:System.Windows.Media.RotateTransform> 。 为了使元素就地旋转，此示例将 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 元素的属性设置为 (0.5，0.5) 点。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 有关包含更多转换示例的完整示例，请参阅 [2D 转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。  
  
## <a name="see-also"></a>请参阅

- [动画概述](animation-overview.md)
- [转换概述](transforms-overview.md)
