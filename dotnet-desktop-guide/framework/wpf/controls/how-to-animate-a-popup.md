---
title: 如何：对 Popup 进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: b70d9c4cb1bca26a6c77d3a7c50add517ca8ef92
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973373"
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="a0460-102">如何：对 Popup 进行动画处理</span><span class="sxs-lookup"><span data-stu-id="a0460-102">How to: Animate a Popup</span></span>
<span data-ttu-id="a0460-103">此示例演示了用于对控件进行动画处理的两种方式 <xref:System.Windows.Controls.Primitives.Popup> 。</span><span class="sxs-lookup"><span data-stu-id="a0460-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0460-104">示例</span><span class="sxs-lookup"><span data-stu-id="a0460-104">Example</span></span>  
 <span data-ttu-id="a0460-105">下面的示例将 <xref:System.Windows.Controls.Primitives.PopupAnimation> 属性设置为的值 <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide> ，这会导致 <xref:System.Windows.Controls.Primitives.Popup> 出现 "滑入"。</span><span class="sxs-lookup"><span data-stu-id="a0460-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="a0460-106">为了旋转 <xref:System.Windows.Controls.Primitives.Popup> ，此示例将分配 <xref:System.Windows.Media.RotateTransform> 给 <xref:System.Windows.UIElement.RenderTransform%2A> 的属性，该属性是的 <xref:System.Windows.Controls.Canvas> 子元素 <xref:System.Windows.Controls.Primitives.Popup> 。</span><span class="sxs-lookup"><span data-stu-id="a0460-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="a0460-107">为了使转换正常工作，该示例必须将属性设置 <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> 为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="a0460-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="a0460-108">此外， <xref:System.Windows.FrameworkElement.Margin%2A> 内容上的 <xref:System.Windows.Controls.Canvas> 必须指定足够的空间 <xref:System.Windows.Controls.Primitives.Popup> 来进行旋转。</span><span class="sxs-lookup"><span data-stu-id="a0460-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="a0460-109">下面的示例演示如何在 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 单击时发生事件，并 <xref:System.Windows.Controls.Button> 触发 <xref:System.Windows.Media.Animation.Storyboard> 启动动画的。</span><span class="sxs-lookup"><span data-stu-id="a0460-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="a0460-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0460-110">See also</span></span>

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="a0460-111">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="a0460-111">How-to Topics</span></span>](popup-how-to-topics.md)
- [<span data-ttu-id="a0460-112">Popup 概述</span><span class="sxs-lookup"><span data-stu-id="a0460-112">Popup Overview</span></span>](popup-overview.md)
