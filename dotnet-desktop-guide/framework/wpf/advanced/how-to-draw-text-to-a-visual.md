---
title: 如何：将文本绘制到 Visual 中
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: 654bfadb42f053b6dcf353d4423bddf281d69478
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973568"
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="ac076-102">如何：将文本绘制到 Visual 中</span><span class="sxs-lookup"><span data-stu-id="ac076-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="ac076-103">下面的示例演示如何使用对象将文本绘制到 <xref:System.Windows.Media.DrawingVisual> <xref:System.Windows.Media.DrawingContext> 。</span><span class="sxs-lookup"><span data-stu-id="ac076-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="ac076-104">通过调用对象的方法来返回一个绘图上下文 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> <xref:System.Windows.Media.DrawingVisual> 。</span><span class="sxs-lookup"><span data-stu-id="ac076-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="ac076-105">您可以在绘图上下文中绘制图形和文本。</span><span class="sxs-lookup"><span data-stu-id="ac076-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="ac076-106">若要在绘图上下文中绘制文本，请使用 <xref:System.Windows.Media.DrawingContext.DrawText%2A> 对象的方法 <xref:System.Windows.Media.DrawingContext> 。</span><span class="sxs-lookup"><span data-stu-id="ac076-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="ac076-107">完成将内容绘制到绘图上下文中后，调用 <xref:System.Windows.Media.DrawingContext.Close%2A> 方法关闭绘图上下文并保存内容。</span><span class="sxs-lookup"><span data-stu-id="ac076-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac076-108">示例</span><span class="sxs-lookup"><span data-stu-id="ac076-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="ac076-109">有关从中提取上述代码示例的完整代码示例，请参阅[使用 DrawingVisual 的命中测试示例](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual)。</span><span class="sxs-lookup"><span data-stu-id="ac076-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).</span></span>
