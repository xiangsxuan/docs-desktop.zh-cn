---
title: 如何：变换画笔
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972766"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="4c22b-102">如何：变换画笔</span><span class="sxs-lookup"><span data-stu-id="4c22b-102">How to: Transform a Brush</span></span>
<span data-ttu-id="4c22b-103">此示例演示如何 <xref:System.Windows.Media.Brush> 使用两个转换属性来转换对象： <xref:System.Windows.Media.Brush.RelativeTransform%2A> 和 <xref:System.Windows.Media.Brush.Transform%2A> 。</span><span class="sxs-lookup"><span data-stu-id="4c22b-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="4c22b-104">下面的示例使用将的 <xref:System.Windows.Media.RotateTransform> 内容旋转 <xref:System.Windows.Media.ImageBrush> 45 度。</span><span class="sxs-lookup"><span data-stu-id="4c22b-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="4c22b-105">下图显示了 <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.RotateTransform> ，其中包含应用于属性的， <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.Brush.RelativeTransform%2A> 以及应用于属性的 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.Brush.Transform%2A> 。</span><span class="sxs-lookup"><span data-stu-id="4c22b-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="4c22b-106">![画笔的 RelativeTransform 和 Transform 设置](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="4c22b-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c22b-107">示例</span><span class="sxs-lookup"><span data-stu-id="4c22b-107">Example</span></span>  
 <span data-ttu-id="4c22b-108">第一个示例将应用 <xref:System.Windows.Media.RotateTransform> 到的 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性 <xref:System.Windows.Media.ImageBrush> 。</span><span class="sxs-lookup"><span data-stu-id="4c22b-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="4c22b-109"><xref:System.Windows.Media.RotateTransform.CenterX%2A>对象的和 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 属性都 <xref:System.Windows.Media.RotateTransform> 设置为0.5，这是此内容中心点的相对坐标。</span><span class="sxs-lookup"><span data-stu-id="4c22b-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="4c22b-110">因此， <xref:System.Windows.Media.ImageBrush> 内容会围绕中心旋转。</span><span class="sxs-lookup"><span data-stu-id="4c22b-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="4c22b-111">第二个示例还将应用 <xref:System.Windows.Media.RotateTransform> 到， <xref:System.Windows.Media.ImageBrush> 但此示例使用属性， <xref:System.Windows.Media.Brush.Transform%2A> 而不是 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="4c22b-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="4c22b-112">为了围绕画笔中心旋转画笔，此示例将对象的 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 和 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 属性设置 <xref:System.Windows.Media.RotateTransform> 为绝对坐标。</span><span class="sxs-lookup"><span data-stu-id="4c22b-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="4c22b-113">因为画笔绘制了一个 175x90 像素的矩形，所以该矩形的中心点为 (87.5, 45)。</span><span class="sxs-lookup"><span data-stu-id="4c22b-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="4c22b-114">有关和属性的工作方式的说明 <xref:System.Windows.Media.Brush.RelativeTransform%2A> <xref:System.Windows.Media.Brush.Transform%2A> ，请参阅 [画笔转换概述](brush-transformation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4c22b-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="4c22b-115">有关完整示例，请参阅[画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。</span><span class="sxs-lookup"><span data-stu-id="4c22b-115">For the complete sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="4c22b-116">有关画笔的详细信息，请参阅[使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4c22b-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c22b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c22b-117">See also</span></span>

- [<span data-ttu-id="4c22b-118">Brush 变换概述</span><span class="sxs-lookup"><span data-stu-id="4c22b-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="4c22b-119">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="4c22b-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="4c22b-120">转换概述</span><span class="sxs-lookup"><span data-stu-id="4c22b-120">Transforms Overview</span></span>](transforms-overview.md)
