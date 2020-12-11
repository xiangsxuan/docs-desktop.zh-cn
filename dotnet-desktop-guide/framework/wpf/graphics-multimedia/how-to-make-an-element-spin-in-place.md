---
title: 如何：使元素就地旋转
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974096"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="838b3-102">如何：使元素就地旋转</span><span class="sxs-lookup"><span data-stu-id="838b3-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="838b3-103">此示例演示如何使用和来使元素旋转 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.Animation.DoubleAnimation> 。</span><span class="sxs-lookup"><span data-stu-id="838b3-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="838b3-104">下面的示例将应用于该 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.UIElement.RenderTransform%2A> 元素的属性。</span><span class="sxs-lookup"><span data-stu-id="838b3-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="838b3-105">该示例使用对的进行 <xref:System.Windows.Media.Animation.DoubleAnimation> 动画处理 <xref:System.Windows.Media.RotateTransform.Angle%2A> <xref:System.Windows.Media.RotateTransform> 。</span><span class="sxs-lookup"><span data-stu-id="838b3-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="838b3-106">为了使元素就地旋转，此示例将 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 元素的属性设置为 (0.5，0.5) 点。</span><span class="sxs-lookup"><span data-stu-id="838b3-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="838b3-107">示例</span><span class="sxs-lookup"><span data-stu-id="838b3-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="838b3-108">有关包含更多转换示例的完整示例，请参阅 [2D 转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。</span><span class="sxs-lookup"><span data-stu-id="838b3-108">For the complete sample, which includes more transformation examples, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="838b3-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="838b3-109">See also</span></span>

- [<span data-ttu-id="838b3-110">动画概述</span><span class="sxs-lookup"><span data-stu-id="838b3-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="838b3-111">转换概述</span><span class="sxs-lookup"><span data-stu-id="838b3-111">Transforms Overview</span></span>](transforms-overview.md)
