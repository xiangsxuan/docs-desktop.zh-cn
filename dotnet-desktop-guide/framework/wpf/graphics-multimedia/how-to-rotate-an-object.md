---
title: 如何：旋转对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973174"
---
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="c9431-102">如何：旋转对象</span><span class="sxs-lookup"><span data-stu-id="c9431-102">How to: Rotate an Object</span></span>
<span data-ttu-id="c9431-103">此示例演示如何旋转对象。</span><span class="sxs-lookup"><span data-stu-id="c9431-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="c9431-104">该示例首先创建一个 <xref:System.Windows.Media.RotateTransform> ，然后 <xref:System.Windows.Media.RotateTransform.Angle%2A> 以度为单位指定它。</span><span class="sxs-lookup"><span data-stu-id="c9431-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="c9431-105">下面的示例将 <xref:System.Windows.Shapes.Polyline> 对象的左上角旋转到45度。</span><span class="sxs-lookup"><span data-stu-id="c9431-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9431-106">示例</span><span class="sxs-lookup"><span data-stu-id="c9431-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="c9431-107"><xref:System.Windows.Media.RotateTransform.CenterX%2A>的和 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 属性 <xref:System.Windows.Media.RotateTransform> 指定对象要旋转的点。</span><span class="sxs-lookup"><span data-stu-id="c9431-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="c9431-108">此中心点以要转换的元素的坐标空间表示。</span><span class="sxs-lookup"><span data-stu-id="c9431-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="c9431-109">默认情况下，将围绕着要转换的对象的左上角 (0,0) 进行旋转。</span><span class="sxs-lookup"><span data-stu-id="c9431-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="c9431-110">下一个示例将 <xref:System.Windows.Shapes.Polyline> 对象顺时针旋转45度 (25，50) 。</span><span class="sxs-lookup"><span data-stu-id="c9431-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="c9431-111">下图显示了将应用于 <xref:System.Windows.Media.Transform> 这两个对象的结果。</span><span class="sxs-lookup"><span data-stu-id="c9431-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="c9431-112">![以不同中心点进行的 45 度旋转](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="c9431-112">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="c9431-113">两个对象以不同的旋转中心旋转 45 度</span><span class="sxs-lookup"><span data-stu-id="c9431-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="c9431-114"><xref:System.Windows.Shapes.Polyline>前面的示例中的是 <xref:System.Windows.UIElement> 。</span><span class="sxs-lookup"><span data-stu-id="c9431-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="c9431-115">当你将应用 <xref:System.Windows.Media.Transform> 到 <xref:System.Windows.UIElement.RenderTransform%2A> 的属性时 <xref:System.Windows.UIElement> ，可以使用 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 属性为应用到元素的每个指定源 <xref:System.Windows.Media.Transform> 。</span><span class="sxs-lookup"><span data-stu-id="c9431-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="c9431-116">由于 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 属性使用相对坐标，因此即使你不知道其大小，也可以将转换应用到元素的中心。</span><span class="sxs-lookup"><span data-stu-id="c9431-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="c9431-117">有关详细信息和示例，请参阅 [使用相对值指定转换原点](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)。</span><span class="sxs-lookup"><span data-stu-id="c9431-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="c9431-118">有关完整示例，请参阅 [2D 转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。</span><span class="sxs-lookup"><span data-stu-id="c9431-118">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9431-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9431-119">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="c9431-120">转换概述</span><span class="sxs-lookup"><span data-stu-id="c9431-120">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="c9431-121">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="c9431-121">How-to Topics</span></span>](transformations-how-to-topics.md)
