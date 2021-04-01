---
title: 如何：绘制带有线性渐变的区域
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 76c491632911c48db34d932ba3895278591378a5
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972078"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="913cb-102">如何：绘制带有线性渐变的区域</span><span class="sxs-lookup"><span data-stu-id="913cb-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="913cb-103">此示例演示如何使用 <xref:System.Windows.Media.LinearGradientBrush> 类绘制带有线性渐变的区域。</span><span class="sxs-lookup"><span data-stu-id="913cb-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="913cb-104">在下面的示例中，的将 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle> 使用从黄色到红色转换为蓝色到浅绿色的对角线性渐变进行绘制。</span><span class="sxs-lookup"><span data-stu-id="913cb-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="913cb-105">示例</span><span class="sxs-lookup"><span data-stu-id="913cb-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="913cb-106">下图显示了上一示例创建的渐变。</span><span class="sxs-lookup"><span data-stu-id="913cb-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="913cb-107">![对角线方向线性渐变](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="913cb-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="913cb-108">若要创建水平线性渐变，请将的 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 和更改 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> <xref:System.Windows.Media.LinearGradientBrush> 为 (0，0.5) 并 (1，0.5) 。</span><span class="sxs-lookup"><span data-stu-id="913cb-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="913cb-109">在下面的示例中， <xref:System.Windows.Shapes.Rectangle> 使用水平线性渐变绘制。</span><span class="sxs-lookup"><span data-stu-id="913cb-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="913cb-110">下图显示了上一示例创建的渐变。</span><span class="sxs-lookup"><span data-stu-id="913cb-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="913cb-111">![水平线性渐变](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="913cb-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="913cb-112">若要创建垂直线性渐变，请将 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> 的和更改 <xref:System.Windows.Media.LinearGradientBrush> 为 (0.5，0) 并 (0.5，1) 。</span><span class="sxs-lookup"><span data-stu-id="913cb-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="913cb-113">在下面的示例中， <xref:System.Windows.Shapes.Rectangle> 用垂直线性渐变绘制。</span><span class="sxs-lookup"><span data-stu-id="913cb-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="913cb-114">下图显示了上一示例创建的渐变。</span><span class="sxs-lookup"><span data-stu-id="913cb-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="913cb-115">![垂直线性渐变](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="913cb-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="913cb-116">本主题中的示例使用默认坐标系统来设置起始点和终结点。</span><span class="sxs-lookup"><span data-stu-id="913cb-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="913cb-117">默认坐标系与边界框相关：0指示边界框的0%，1指示边界框的100%。</span><span class="sxs-lookup"><span data-stu-id="913cb-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="913cb-118">您可以通过将属性设置为值来更改此坐标系统 <xref:System.Windows.Media.GradientBrush.MappingMode%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="913cb-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="913cb-119">绝对坐标系与范围框无关。</span><span class="sxs-lookup"><span data-stu-id="913cb-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="913cb-120">值直接在本地空间中解释。</span><span class="sxs-lookup"><span data-stu-id="913cb-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="913cb-121">有关其他示例，请参阅 [画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。</span><span class="sxs-lookup"><span data-stu-id="913cb-121">For additional examples, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="913cb-122">有关渐变和其他类型画笔的详细信息，请参阅 [采用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="913cb-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
