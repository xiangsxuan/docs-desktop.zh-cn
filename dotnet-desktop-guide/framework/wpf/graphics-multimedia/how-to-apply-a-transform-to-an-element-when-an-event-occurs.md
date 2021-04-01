---
title: 如何：在事件发生时向元素应用变换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
ms.openlocfilehash: 8f04db274432c0e89c6839bef825976c8a2f853c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970854"
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a><span data-ttu-id="dd5bc-102">如何：在事件发生时向元素应用变换</span><span class="sxs-lookup"><span data-stu-id="dd5bc-102">How to: Apply a Transform to an Element When an Event Occurs</span></span>
<span data-ttu-id="dd5bc-103">此示例演示如何 <xref:System.Windows.Media.ScaleTransform> 在事件发生时应用。</span><span class="sxs-lookup"><span data-stu-id="dd5bc-103">This example shows how to apply a <xref:System.Windows.Media.ScaleTransform> when an event occurs.</span></span> <span data-ttu-id="dd5bc-104">此处说明的概念与用于应用其他类型的转换的概念相同。</span><span class="sxs-lookup"><span data-stu-id="dd5bc-104">The concept that is shown here is the same that you use for applying other types of transformations.</span></span> <span data-ttu-id="dd5bc-105">有关可用转换类型的详细信息，请参阅 <xref:System.Windows.Media.Transform> 类或 [转换概述](transforms-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="dd5bc-105">For more information about the available types of transformations, see the <xref:System.Windows.Media.Transform> class or [Transforms Overview](transforms-overview.md).</span></span>  
  
 <span data-ttu-id="dd5bc-106">可以通过以下两种方式之一向元素应用转换：</span><span class="sxs-lookup"><span data-stu-id="dd5bc-106">You can apply a transform to an element in either of these two ways:</span></span>  
  
- <span data-ttu-id="dd5bc-107">如果 *不* 希望转换影响布局，请使用 <xref:System.Windows.UIElement.RenderTransform%2A> 元素的属性。</span><span class="sxs-lookup"><span data-stu-id="dd5bc-107">If you do *not* want the transform to affect layout, use the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
- <span data-ttu-id="dd5bc-108">如果希望转换影响布局，请使用 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 元素的属性。</span><span class="sxs-lookup"><span data-stu-id="dd5bc-108">If you do want the transform to affect layout, use the <xref:System.Windows.FrameworkElement.LayoutTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="dd5bc-109">下面的示例将应用 <xref:System.Windows.Media.ScaleTransform> 到 <xref:System.Windows.UIElement.RenderTransform%2A> 按钮的属性。</span><span class="sxs-lookup"><span data-stu-id="dd5bc-109">The following example applies a <xref:System.Windows.Media.ScaleTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a button.</span></span> <span data-ttu-id="dd5bc-110">当鼠标移到按钮上时，的 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 和 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 属性将 <xref:System.Windows.Media.ScaleTransform> 设置为 `2` ，这将导致按钮变大。</span><span class="sxs-lookup"><span data-stu-id="dd5bc-110">When the mouse moves over the button, the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties of the <xref:System.Windows.Media.ScaleTransform> are set to `2`, which causes the button to become larger.</span></span> <span data-ttu-id="dd5bc-111">当鼠标移出按钮时，将 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 设置为 `1` ，这会使按钮返回到其原始大小。</span><span class="sxs-lookup"><span data-stu-id="dd5bc-111">When the mouse moves off the button, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> are set to `1`, which causes the button to return to its original size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd5bc-112">示例</span><span class="sxs-lookup"><span data-stu-id="dd5bc-112">Example</span></span>  
 [!code-xaml[ButtonTransform#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a><span data-ttu-id="dd5bc-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd5bc-113">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="dd5bc-114">转换概述</span><span class="sxs-lookup"><span data-stu-id="dd5bc-114">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="dd5bc-115">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="dd5bc-115">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="dd5bc-116">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="dd5bc-116">Routed Events Overview</span></span>](../advanced/routed-events-overview.md)
