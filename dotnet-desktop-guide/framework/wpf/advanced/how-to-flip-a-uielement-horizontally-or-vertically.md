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
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="164b3-102">如何：水平或垂直翻转 UIElement</span><span class="sxs-lookup"><span data-stu-id="164b3-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="164b3-103">此示例演示如何使用 <xref:System.Windows.Media.ScaleTransform> 来 <xref:System.Windows.UIElement> 水平或垂直翻转。</span><span class="sxs-lookup"><span data-stu-id="164b3-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="164b3-104">在此示例中， <xref:System.Windows.Controls.Button> <xref:System.Windows.UIElement> 通过将应用 <xref:System.Windows.Media.ScaleTransform> 到其属性来翻转) 类型 (的控件 <xref:System.Windows.UIElement.RenderTransform%2A> 。</span><span class="sxs-lookup"><span data-stu-id="164b3-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="164b3-105">示例</span><span class="sxs-lookup"><span data-stu-id="164b3-105">Example</span></span>  
 <span data-ttu-id="164b3-106">下图显示了要翻转的按钮。</span><span class="sxs-lookup"><span data-stu-id="164b3-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="164b3-107">![无转换的按钮](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="164b3-107">![A button with no transform](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="164b3-108">要翻转的 UIElement</span><span class="sxs-lookup"><span data-stu-id="164b3-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="164b3-109">下面显示了用于创建按钮的代码。</span><span class="sxs-lookup"><span data-stu-id="164b3-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="164b3-110">示例</span><span class="sxs-lookup"><span data-stu-id="164b3-110">Example</span></span>  
 <span data-ttu-id="164b3-111">若要水平翻转按钮，请创建一个 <xref:System.Windows.Media.ScaleTransform> 并将其 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 属性设置为-1。</span><span class="sxs-lookup"><span data-stu-id="164b3-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="164b3-112">将应用 <xref:System.Windows.Media.ScaleTransform> 到按钮的 <xref:System.Windows.UIElement.RenderTransform%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="164b3-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="164b3-113">![围绕 &#40;0，0&#41;水平翻转的按钮 ](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="164b3-113">![A button flipped horizontally about &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="164b3-114">应用 System.windows.media.scaletransform> 后的按钮</span><span class="sxs-lookup"><span data-stu-id="164b3-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="164b3-115">示例</span><span class="sxs-lookup"><span data-stu-id="164b3-115">Example</span></span>  
 <span data-ttu-id="164b3-116">如前面的插图所示，按钮已翻转，但也被移动。</span><span class="sxs-lookup"><span data-stu-id="164b3-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="164b3-117">这是因为按钮从左上角翻转。</span><span class="sxs-lookup"><span data-stu-id="164b3-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="164b3-118">若要就地翻转按钮，需要将应用 <xref:System.Windows.Media.ScaleTransform> 到其中心，而不是应用于角。</span><span class="sxs-lookup"><span data-stu-id="164b3-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="164b3-119">向按钮中心应用的一种简单方法 <xref:System.Windows.Media.ScaleTransform> 是将按钮的 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 属性设置为0.5、0.5。</span><span class="sxs-lookup"><span data-stu-id="164b3-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="164b3-120">![围绕中心水平翻转的按钮](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="164b3-120">![A button flipped horizontally about its center](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="164b3-121">System.windows.uielement.rendertransformorigin 为0.5，0.5 的按钮</span><span class="sxs-lookup"><span data-stu-id="164b3-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="164b3-122">示例</span><span class="sxs-lookup"><span data-stu-id="164b3-122">Example</span></span>  
 <span data-ttu-id="164b3-123">若要垂直翻转按钮，请设置 <xref:System.Windows.Media.ScaleTransform> 对象的 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 属性而不是其 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="164b3-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="164b3-124">![围绕中心垂直翻转的按钮](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="164b3-124">![A button flipped vertically about its center](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="164b3-125">垂直翻转按钮</span><span class="sxs-lookup"><span data-stu-id="164b3-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="164b3-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="164b3-126">See also</span></span>

- [<span data-ttu-id="164b3-127">转换概述</span><span class="sxs-lookup"><span data-stu-id="164b3-127">Transforms Overview</span></span>](../graphics-multimedia/transforms-overview.md)
