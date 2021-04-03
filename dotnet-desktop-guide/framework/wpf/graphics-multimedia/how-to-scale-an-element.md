---
title: 如何：缩放元素
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973216"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="2b037-102">如何：缩放元素</span><span class="sxs-lookup"><span data-stu-id="2b037-102">How to: Scale an Element</span></span>
<span data-ttu-id="2b037-103">此示例演示如何使用 <xref:System.Windows.Media.ScaleTransform> 缩放元素。</span><span class="sxs-lookup"><span data-stu-id="2b037-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="2b037-104">使用 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 和 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 属性，按指定的因子调整元素的大小。</span><span class="sxs-lookup"><span data-stu-id="2b037-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="2b037-105">例如，如果 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 值为1.5，则将元素拉伸到其原始宽度的150%。</span><span class="sxs-lookup"><span data-stu-id="2b037-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="2b037-106"><xref:System.Windows.Media.ScaleTransform.ScaleY%2A>值0.5 将元素的高度缩减50%。</span><span class="sxs-lookup"><span data-stu-id="2b037-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="2b037-107">使用 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 和 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 属性来指定缩放操作的中心点。</span><span class="sxs-lookup"><span data-stu-id="2b037-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="2b037-108">默认情况下，在 <xref:System.Windows.Media.ScaleTransform> (0，0) 点居中，这对应于矩形的左上角。</span><span class="sxs-lookup"><span data-stu-id="2b037-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="2b037-109">这会使元素移动并使其显得更大，因为当应用时 <xref:System.Windows.Media.Transform> ，将更改对象所在的坐标空间。</span><span class="sxs-lookup"><span data-stu-id="2b037-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="2b037-110">下面的示例使用将 <xref:System.Windows.Media.ScaleTransform> 50 50 的大小加倍 <xref:System.Windows.Shapes.Rectangle> 。</span><span class="sxs-lookup"><span data-stu-id="2b037-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="2b037-111">的 <xref:System.Windows.Media.ScaleTransform> 值为 0 (和的默认) <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 。</span><span class="sxs-lookup"><span data-stu-id="2b037-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b037-112">示例</span><span class="sxs-lookup"><span data-stu-id="2b037-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="2b037-113">通常情况下，将 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 和设置 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 为缩放的对象中心： (<xref:System.Windows.FrameworkElement.Width%2A> /2， <xref:System.Windows.FrameworkElement.Height%2A> /2) 。</span><span class="sxs-lookup"><span data-stu-id="2b037-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="2b037-114">下面的示例演示另一种 <xref:System.Windows.Shapes.Rectangle> 大小为两倍的; 但是， <xref:System.Windows.Media.ScaleTransform> 对于 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 和 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> （对应于矩形的中心），此值的值为25。</span><span class="sxs-lookup"><span data-stu-id="2b037-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="2b037-115">下图显示了这两个操作之间的差异 <xref:System.Windows.Media.ScaleTransform> 。</span><span class="sxs-lookup"><span data-stu-id="2b037-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="2b037-116">虚线显示的是矩形在缩放之前的大小和位置。</span><span class="sxs-lookup"><span data-stu-id="2b037-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="2b037-117">![以不同中心点进行的 2 倍缩放](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="2b037-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="2b037-118">两个具有相同 ScaleX 和 ScaleY 值但中心不同的 ScaleTransform 操作</span><span class="sxs-lookup"><span data-stu-id="2b037-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="2b037-119">有关完整示例，请参阅 [2D 转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。</span><span class="sxs-lookup"><span data-stu-id="2b037-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b037-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b037-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="2b037-121">转换概述</span><span class="sxs-lookup"><span data-stu-id="2b037-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="2b037-122">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="2b037-122">How-to Topics</span></span>](transformations-how-to-topics.md)
