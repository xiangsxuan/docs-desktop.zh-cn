---
title: 如何：使用 RectangleGeometry 定义矩形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 146ca7017ee38ad5c1065e59662ac441e7bfbfe2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973311"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a><span data-ttu-id="cfb96-102">如何：使用 RectangleGeometry 定义矩形</span><span class="sxs-lookup"><span data-stu-id="cfb96-102">How to: Define a Rectangle Using a RectangleGeometry</span></span>
<span data-ttu-id="cfb96-103">此示例说明如何使用 <xref:System.Windows.Media.RectangleGeometry> 类来描述矩形。</span><span class="sxs-lookup"><span data-stu-id="cfb96-103">This example describes how to use the <xref:System.Windows.Media.RectangleGeometry> class to describe a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfb96-104">示例</span><span class="sxs-lookup"><span data-stu-id="cfb96-104">Example</span></span>  
 <span data-ttu-id="cfb96-105">下面的示例演示如何创建和呈现 <xref:System.Windows.Media.RectangleGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="cfb96-105">The following example shows how to create and render a <xref:System.Windows.Media.RectangleGeometry>.</span></span>  <span data-ttu-id="cfb96-106">矩形的相对位置和尺寸由 <xref:System.Windows.Rect> 结构定义。</span><span class="sxs-lookup"><span data-stu-id="cfb96-106">The relative position and the dimensions of the rectangle are defined by a <xref:System.Windows.Rect> structure.</span></span> <span data-ttu-id="cfb96-107">相对位置是 `50,50` ，高度和宽度均 `25` 创建正方形。</span><span class="sxs-lookup"><span data-stu-id="cfb96-107">The relative position is `50,50` and the height and the width are both `25` creating a square.</span></span> <span data-ttu-id="cfb96-108">使用画笔绘制矩形的内部 <xref:System.Windows.Media.Brushes.LemonChiffon%2A> ，并使用粗细为的笔画绘制其轮廓 <xref:System.Windows.Media.Brushes.Black%2A> `1` 。</span><span class="sxs-lookup"><span data-stu-id="cfb96-108">The rectangle's interior is painted with a <xref:System.Windows.Media.Brushes.LemonChiffon%2A> brush and its outline is painted with a <xref:System.Windows.Media.Brushes.Black%2A> stroke with a thickness of `1`.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 <span data-ttu-id="cfb96-109">![一个 RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span><span class="sxs-lookup"><span data-stu-id="cfb96-109">![A RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span></span>  
<span data-ttu-id="cfb96-110">RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="cfb96-110">RectangleGeometry</span></span>  
  
 <span data-ttu-id="cfb96-111">虽然此示例使用了一个 <xref:System.Windows.Shapes.Path> 元素来呈现 <xref:System.Windows.Media.RectangleGeometry> ，但有许多其他使用对象的方法 <xref:System.Windows.Media.RectangleGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="cfb96-111">Although this example used a <xref:System.Windows.Shapes.Path> element to render the <xref:System.Windows.Media.RectangleGeometry>, there are many other ways to use <xref:System.Windows.Media.RectangleGeometry> objects.</span></span> <span data-ttu-id="cfb96-112">例如， <xref:System.Windows.Media.RectangleGeometry> 可用于指定的 <xref:System.Windows.UIElement.Clip%2A> 或的 <xref:System.Windows.UIElement> <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> <xref:System.Windows.Media.GeometryDrawing> 。</span><span class="sxs-lookup"><span data-stu-id="cfb96-112">For example, a <xref:System.Windows.Media.RectangleGeometry> can be used to specify the <xref:System.Windows.UIElement.Clip%2A> of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> of a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="cfb96-113">其他简单的 geometry 类包括 <xref:System.Windows.Media.LineGeometry> 和 <xref:System.Windows.Media.EllipseGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="cfb96-113">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="cfb96-114">还可以使用或创建这些几何图形以及更复杂的几何图形 <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="cfb96-114">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb96-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="cfb96-115">See also</span></span>

- [<span data-ttu-id="cfb96-116">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="cfb96-116">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="cfb96-117">创建复合形状</span><span class="sxs-lookup"><span data-stu-id="cfb96-117">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="cfb96-118">使用 PathGeometry 创建形状</span><span class="sxs-lookup"><span data-stu-id="cfb96-118">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
