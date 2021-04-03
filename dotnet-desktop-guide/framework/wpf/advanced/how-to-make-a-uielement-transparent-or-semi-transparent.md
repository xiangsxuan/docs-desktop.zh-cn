---
title: 如何：使 UIElement 呈现为透明或半透明
ms.date: 03/30/2017
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
ms.openlocfilehash: 1de9a7e11fee241ecb71242e9808e77b7e5e63b0
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971817"
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a><span data-ttu-id="3b7ff-102">如何：使 UIElement 呈现为透明或半透明</span><span class="sxs-lookup"><span data-stu-id="3b7ff-102">How to: Make a UIElement Transparent or Semi-Transparent</span></span>
<span data-ttu-id="3b7ff-103">此示例演示如何使 <xref:System.Windows.UIElement> 透明或半透明。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-103">This example shows how to make a <xref:System.Windows.UIElement> transparent or semi-transparent.</span></span> <span data-ttu-id="3b7ff-104">若要使元素透明或半透明，请设置其 <xref:System.Windows.UIElement.Opacity%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-104">To make an element transparent or semi-transparent, you set its <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="3b7ff-105">值 `0.0` 使元素完全透明，而值则 `1.0` 使元素完全不透明。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-105">A value of `0.0` makes the element completely transparent, while a value of `1.0` makes the element completely opaque.</span></span> <span data-ttu-id="3b7ff-106">如果值为 `0.5` ，则使元素50% 不透明，依此类推。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-106">A value of `0.5` makes the element 50% opaque, and so on.</span></span> <span data-ttu-id="3b7ff-107"><xref:System.Windows.UIElement.Opacity%2A>默认情况下，元素的设置为 `1.0` 。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-107">An element's <xref:System.Windows.UIElement.Opacity%2A> is set to `1.0` by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b7ff-108">示例</span><span class="sxs-lookup"><span data-stu-id="3b7ff-108">Example</span></span>  
 <span data-ttu-id="3b7ff-109">下面的示例将按钮的设置 <xref:System.Windows.UIElement.Opacity%2A> 为 `0.25` ，使其及其内容 (在这种情况下，该按钮的文本) 25% 不透明。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-109">The following example sets the <xref:System.Windows.UIElement.Opacity%2A> of a button to `0.25`, making it and its contents (in this case, the button's text) 25% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 <span data-ttu-id="3b7ff-110">如果元素的内容具有其自己的 <xref:System.Windows.UIElement.Opacity%2A> 设置，则这些值将与包含元素相乘 <xref:System.Windows.UIElement.Opacity%2A> 。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-110">If an element's contents have their own <xref:System.Windows.UIElement.Opacity%2A> settings, those values are multiplied against the containing elements <xref:System.Windows.UIElement.Opacity%2A>.</span></span>  
  
 <span data-ttu-id="3b7ff-111">下面的示例将按钮的设置 <xref:System.Windows.UIElement.Opacity%2A> 为 `0.25` ，并将 <xref:System.Windows.UIElement.Opacity%2A> <xref:System.Windows.Controls.Image> 包含在中的控件的设置为 `0.5` 。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-111">The following example sets a button's <xref:System.Windows.UIElement.Opacity%2A> to `0.25`, and the <xref:System.Windows.UIElement.Opacity%2A> of an <xref:System.Windows.Controls.Image> control contained with in the button to `0.5`.</span></span> <span data-ttu-id="3b7ff-112">因此，图像显示12.5% 不透明： 0.25 \* 0.5 = 0.125。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-112">As a result, the image appears 12.5% opaque: 0.25 \* 0.5 = 0.125.</span></span>  
  
 [!code-xaml[brushsamples_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 <span data-ttu-id="3b7ff-113">控制元素不透明度的另一种方法是设置绘制元素的的不透明度 <xref:System.Windows.Media.Brush> 。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-113">Another way to control the opacity of an element is to set the opacity of the <xref:System.Windows.Media.Brush> that paints the element.</span></span> <span data-ttu-id="3b7ff-114">利用此方法，您可以有选择地改变元素部分的不透明度，并通过使用元素的属性提供性能优势 <xref:System.Windows.UIElement.Opacity%2A> 。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-114">This approach enables you to selectively alter the opacity of portions of an element, and provides performance benefits over using the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="3b7ff-115">下面的示例设置 <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.SolidColorBrush> 用于绘制按钮的的，其 <xref:System.Windows.Controls.Control.Background%2A> 设置为 `0.25` 。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-115">The following example sets the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush> used to paint the button's <xref:System.Windows.Controls.Control.Background%2A> is set to `0.25`.</span></span> <span data-ttu-id="3b7ff-116">因此，画笔的背景为25% 不透明，但其内容 (按钮的文本) 仍然为100% 不透明。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-116">As a result, the brush's background is 25% opaque, but its contents (the button's text) remain 100% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 <span data-ttu-id="3b7ff-117">您还可以控制画笔内各个颜色的不透明度。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-117">You may also control the opacity of individual colors within a brush.</span></span> <span data-ttu-id="3b7ff-118">有关颜色和画笔的详细信息，请参阅 [用纯色和渐变进行绘制概述](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-118">For more information about colors and brushes, see [Painting with Solid Colors and Gradients Overview](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span> <span data-ttu-id="3b7ff-119">有关演示如何对元素的不透明度进行动画处理的示例，请参阅对 [元素或画笔的不透明度进行动画处理](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md)。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-119">For an example showing how to animate an element's opacity, see [Animate the Opacity of an Element or Brush](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span></span>
