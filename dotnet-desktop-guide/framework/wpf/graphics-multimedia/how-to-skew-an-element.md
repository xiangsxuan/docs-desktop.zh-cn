---
title: 如何：使元素扭曲
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971008"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="8dca2-102">如何：使元素扭曲</span><span class="sxs-lookup"><span data-stu-id="8dca2-102">How to: Skew an Element</span></span>
<span data-ttu-id="8dca2-103">此示例演示如何使用 <xref:System.Windows.Media.SkewTransform> 来倾斜元素。</span><span class="sxs-lookup"><span data-stu-id="8dca2-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="8dca2-104">扭曲（也称为修剪）是一种以非均匀方式拉伸坐标空间的转换。</span><span class="sxs-lookup"><span data-stu-id="8dca2-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="8dca2-105">的一个典型用途 <xref:System.Windows.Media.SkewTransform> 是在2d 对象中模拟3d 深度。</span><span class="sxs-lookup"><span data-stu-id="8dca2-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating 3D depth in 2D objects.</span></span>  
  
 <span data-ttu-id="8dca2-106">使用 <xref:System.Windows.Media.SkewTransform.CenterX%2A> 和 <xref:System.Windows.Media.SkewTransform.CenterY%2A> 属性来指定的中心点 <xref:System.Windows.Media.SkewTransform> 。</span><span class="sxs-lookup"><span data-stu-id="8dca2-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="8dca2-107">使用 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 和 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 属性来指定 x 轴和 y 轴的倾斜角度，并沿这些轴倾斜当前坐标系统。</span><span class="sxs-lookup"><span data-stu-id="8dca2-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="8dca2-108">若要预测斜切转换的效果，请考虑将 <xref:System.Windows.Media.SkewTransform.AngleX%2A> x 轴值与原始坐标系统相对倾斜。</span><span class="sxs-lookup"><span data-stu-id="8dca2-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="8dca2-109">因此，对于 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 30，y 轴将从原点旋转30度，并从该原点的 x 到30度之间倾斜值。</span><span class="sxs-lookup"><span data-stu-id="8dca2-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="8dca2-110">同样，值为30时， <xref:System.Windows.Media.SkewTransform.AngleY%2A> 从原点将形状的 y 值倾斜30度。</span><span class="sxs-lookup"><span data-stu-id="8dca2-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="8dca2-111">请注意，在 x 或 y 轴中将坐标系统转换（移动）30 度的效果并不相同。</span><span class="sxs-lookup"><span data-stu-id="8dca2-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="8dca2-112">下面的示例 <xref:System.Windows.Shapes.Rectangle> 从 (0，0) 的中心点向中应用45度的水平倾斜。</span><span class="sxs-lookup"><span data-stu-id="8dca2-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dca2-113">示例</span><span class="sxs-lookup"><span data-stu-id="8dca2-113">Example</span></span>  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="8dca2-114">下面的示例 <xref:System.Windows.Shapes.Rectangle> 从 (25，25) 的中心点向中应用45度的水平倾斜。</span><span class="sxs-lookup"><span data-stu-id="8dca2-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="8dca2-115">下面的示例 <xref:System.Windows.Shapes.Rectangle> 从 (25，25) 的中心点向中应用45度的垂直倾斜。</span><span class="sxs-lookup"><span data-stu-id="8dca2-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="8dca2-116">下图演示了此示例中使用的不同扭曲。</span><span class="sxs-lookup"><span data-stu-id="8dca2-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="8dca2-117">![SkewTransform 示例](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="8dca2-117">![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="8dca2-118">三个 SkewTransform 示例的图示</span><span class="sxs-lookup"><span data-stu-id="8dca2-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="8dca2-119">有关完整示例，请参阅 [2D 转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。</span><span class="sxs-lookup"><span data-stu-id="8dca2-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dca2-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8dca2-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [<span data-ttu-id="8dca2-121">转换概述</span><span class="sxs-lookup"><span data-stu-id="8dca2-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="8dca2-122">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="8dca2-122">How-to Topics</span></span>](transformations-how-to-topics.md)
