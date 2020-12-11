---
title: 如何：平移元素
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972762"
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="a2a9a-102">如何：平移元素</span><span class="sxs-lookup"><span data-stu-id="a2a9a-102">How to: Translate an Element</span></span>
<span data-ttu-id="a2a9a-103">此示例演示如何使用转换 (移动) 元素 <xref:System.Windows.Media.TranslateTransform> 。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="a2a9a-104"><xref:System.Windows.Media.TranslateTransform>类对于在不支持绝对定位的面板内移动元素特别有用。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="a2a9a-105">例如，通过将应用 <xref:System.Windows.Media.TranslateTransform> 于元素的 <xref:System.Windows.UIElement.RenderTransform%2A> 属性，可以在或中移动元素 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.DockPanel> 。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="a2a9a-106">使用 <xref:System.Windows.Media.TranslateTransform.X%2A> 的属性 <xref:System.Windows.Media.TranslateTransform> 来指定沿 x 轴移动元素的量（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="a2a9a-107">使用 <xref:System.Windows.Media.TranslateTransform.Y%2A> 属性来指定沿 y 轴移动元素的量（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="a2a9a-108">最后，将应用于该 <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.UIElement.RenderTransform%2A> 元素的属性。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="a2a9a-109">下面的示例使用将 <xref:System.Windows.Media.TranslateTransform> 元素50像素向右移动，将50像素向下移动。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2a9a-110">示例</span><span class="sxs-lookup"><span data-stu-id="a2a9a-110">Example</span></span>  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="a2a9a-111">有关完整示例，请参阅 [2D 转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-111">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a9a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2a9a-112">See also</span></span>

- [<span data-ttu-id="a2a9a-113">转换概述</span><span class="sxs-lookup"><span data-stu-id="a2a9a-113">Transforms Overview</span></span>](transforms-overview.md)
