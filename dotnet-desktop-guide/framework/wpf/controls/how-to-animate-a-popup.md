---
title: 如何：对 Popup 进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: b70d9c4cb1bca26a6c77d3a7c50add517ca8ef92
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973373"
---
# <a name="how-to-animate-a-popup"></a>如何：对 Popup 进行动画处理
此示例演示了用于对控件进行动画处理的两种方式 <xref:System.Windows.Controls.Primitives.Popup> 。  
  
## <a name="example"></a>示例  
 下面的示例将 <xref:System.Windows.Controls.Primitives.PopupAnimation> 属性设置为的值 <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide> ，这会导致 <xref:System.Windows.Controls.Primitives.Popup> 出现 "滑入"。  
  
 为了旋转 <xref:System.Windows.Controls.Primitives.Popup> ，此示例将分配 <xref:System.Windows.Media.RotateTransform> 给 <xref:System.Windows.UIElement.RenderTransform%2A> 的属性，该属性是的 <xref:System.Windows.Controls.Canvas> 子元素 <xref:System.Windows.Controls.Primitives.Popup> 。  
  
 为了使转换正常工作，该示例必须将属性设置 <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> 为 `true` 。 此外， <xref:System.Windows.FrameworkElement.Margin%2A> 内容上的 <xref:System.Windows.Controls.Canvas> 必须指定足够的空间 <xref:System.Windows.Controls.Primitives.Popup> 来进行旋转。  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 下面的示例演示如何在 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 单击时发生事件，并 <xref:System.Windows.Controls.Button> 触发 <xref:System.Windows.Media.Animation.Storyboard> 启动动画的。  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [操作指南主题](popup-how-to-topics.md)
- [Popup 概述](popup-overview.md)
