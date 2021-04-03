---
title: 如何：对 FrameworkElement 的大小进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
ms.openlocfilehash: d1995deec5ab2c9bf405911af43b4d242d599119
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971927"
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a><span data-ttu-id="f74e7-102">如何：对 FrameworkElement 的大小进行动画处理</span><span class="sxs-lookup"><span data-stu-id="f74e7-102">How to: Animate the Size of a FrameworkElement</span></span>
<span data-ttu-id="f74e7-103">若要对的大小进行动画处理 <xref:System.Windows.FrameworkElement> ，可以对其和属性进行动画处理， <xref:System.Windows.FrameworkElement.Width%2A> 也可以 <xref:System.Windows.FrameworkElement.Height%2A> 使用动画 <xref:System.Windows.Media.ScaleTransform> 。</span><span class="sxs-lookup"><span data-stu-id="f74e7-103">To animate the size of a <xref:System.Windows.FrameworkElement>, you can either animate its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties or use an animated <xref:System.Windows.Media.ScaleTransform>.</span></span>  
  
 <span data-ttu-id="f74e7-104">在下面的示例中，使用这两种方法对两个按钮的大小进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="f74e7-104">In the following example animates the size of two buttons using these two approaches.</span></span> <span data-ttu-id="f74e7-105">通过对一个按钮的属性进行动画处理来调整其大小 <xref:System.Windows.FrameworkElement.Width%2A> ，并通过 <xref:System.Windows.Media.ScaleTransform> 对应用于其属性的应用进行动画处理，从而调整 <xref:System.Windows.UIElement.RenderTransform%2A></span><span class="sxs-lookup"><span data-stu-id="f74e7-105">One button is resized by animating its <xref:System.Windows.FrameworkElement.Width%2A> property and another is resized by animating a <xref:System.Windows.Media.ScaleTransform> applied to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span> <span data-ttu-id="f74e7-106">每个按钮都包含一些文本。</span><span class="sxs-lookup"><span data-stu-id="f74e7-106">Each button contains some text.</span></span> <span data-ttu-id="f74e7-107">最初，这两个按钮中的文本在外观上都是相同的，但在调整按钮的大小时，第二个按钮中的文本会变为扭曲。</span><span class="sxs-lookup"><span data-stu-id="f74e7-107">Initially, the text appears the same in both buttons, but as the buttons are resized, the text in the second button becomes distorted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f74e7-108">示例</span><span class="sxs-lookup"><span data-stu-id="f74e7-108">Example</span></span>  
 [!code-xaml[transformanimations_snip#1](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 <span data-ttu-id="f74e7-109">转换元素时，将转换整个元素及其内容。</span><span class="sxs-lookup"><span data-stu-id="f74e7-109">When you transform an element, the entire element and its contents are transformed.</span></span> <span data-ttu-id="f74e7-110">当直接更改元素的大小时，如第一个按钮时，元素的内容不会调整大小，除非它们的大小和位置取决于其父元素的大小。</span><span class="sxs-lookup"><span data-stu-id="f74e7-110">When you directly alter the size of an element, as in the case of the first button, the element's contents are not resized unless their size and position depend on the size of their parent element.</span></span>  
  
 <span data-ttu-id="f74e7-111">通过对元素的属性应用动态转换来对该元素的大小进行动画处理 <xref:System.Windows.UIElement.RenderTransform%2A> 可提供比动态和直接动画更好的性能 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> ，因为 <xref:System.Windows.UIElement.RenderTransform%2A> 属性不会触发布局处理过程。</span><span class="sxs-lookup"><span data-stu-id="f74e7-111">Animating the size of an element by applying an animated transform to its <xref:System.Windows.UIElement.RenderTransform%2A> property provides better performance than animated its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> directly, because the <xref:System.Windows.UIElement.RenderTransform%2A> property does not trigger a layout pass.</span></span>  
  
 <span data-ttu-id="f74e7-112">有关对属性进行动画处理的详细信息，请参阅 [动画概述](../graphics-multimedia/animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f74e7-112">For more information about animating properties, see the [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="f74e7-113">有关转换的详细信息，请参阅 [转换概述](../graphics-multimedia/transforms-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f74e7-113">For more information about transforms, see the [Transforms Overview](../graphics-multimedia/transforms-overview.md).</span></span>
